
**Virtual Host**

Ensure domain is listed in hosts file
```shell-session
echo "IP test.com" | sudo tee -a /etc/hosts
```


```shell-session
gobuster vhost -u http://test.com:81 -w /usr/share/seclists/Discovery/Web-Content/common.txt --append-domain
```


**Subdomain**
```shell-session
gobuster dns -d test.com -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt
```


**FUZZING FILTERING**
https://academy.hackthebox.com/module/280/section/3133