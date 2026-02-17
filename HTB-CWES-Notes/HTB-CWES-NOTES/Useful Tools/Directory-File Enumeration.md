- **Gobuster** – Fast directory & vhost brute-forcing
    `sudo apt-get install gobuster`
    
	`gobuster dir -u https://example.com -w wordlist.txt -t 50

/usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt


- **Feroxbuster** – Recursive, modern directory fuzzing  
    [https://github.com/epi052/feroxbuster](https://github.com/epi052/feroxbuster)
    
- **Dirsearch** – Python-based directory brute-forcer  
    https://github.com/maurosoria/dirsearch

FFuF
ffuf -u https://example.com/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt