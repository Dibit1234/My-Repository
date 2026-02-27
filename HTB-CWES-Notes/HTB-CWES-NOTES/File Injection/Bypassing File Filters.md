
**IF NO SUCCESSS COMBINE WITH HTTB VERB TAMPERING**

- Remove client side validation: CTRL SHIFT C

- Bypass using burp

- Bypass Blacklists FUZZING
	- Common:
		- https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/web-extensions.txt
	- PHP:
		- https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Upload%20Insecure%20Files/Extension%20PHP/extensions.lst
	- .NET
		- https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Upload%20Insecure%20Files/Extension%20ASP
- Check for double and reverse double injections
	- i.e. hi.jpg.php and hi.php.jpg


Manipulate Content and MIME types to bypass filters:



**Get Content Type Word List**

```shell-session
wget https://raw.githubusercontent.com/danielmiessler/SecLists/refs/heads/master/Discovery/Web-Content/web-all-content-types.txt
```

```shell-session
cat web-all-content-types.txt | grep 'image/' > image-content-types.txt
```


Content Type:
![[Pasted image 20260211161052.jpg]]

MIME (first few bytes of content) Type:
![[Pasted image 20260211161057.jpg]]
