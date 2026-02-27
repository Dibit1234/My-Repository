1. Reconnaissance:
	1. whois
	2. curl -i
		1. robots.txt
		2. sitemap.xml
		3. Check html: ctrl U / C
	3. Ensure hostnames are resolvable: sudo nano /etc/hosts
	4. Directory brute force:
		1. ffuf -u website:port/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt
			1. try small wordlist, move to bigger ones if nothing found. Some include: raft-large-directories.txt and directory-list-2.3-medium.txt
	5. Subdomain Brute force 
		1. gobuster vhost -u website:port -w /usr/share/seclists/Discovery/DNS/fierce-hostlist.txt -t 100 --append-domain
			1. Switch to larger wordlist: subdomains-top1million-110000.txt. Change to -t 500
			2. If subdomains are found, add to /etc/hosts
	6. Spider / Crawl the website
		1. python3 ReconSpider.py http://subdomain.website.port



**ENSURE STEPS ARE REPEATED WHEN HITTING A WALL.**
i.e. Directory and Subdomain recursion.

2. 