- **FFUF** – Parameter, directory & value fuzzing  
    [https://github.com/ffuf/ffuf](https://github.com/ffuf/ffuf)

ffuf -u "http://TARGET/?FUZZ=test" \
  -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt

**Add to Enumerate**
-fs INSERT NUMBER


**WEAK PARAMETER DISCOVERY**
python xsstrike.py -u "http://154.57.164.65:30369/?fullname=test&username=test&password=test&email=test%40test.com"


    
- **Arjun** – Hidden HTTP parameter discovery  
    [https://github.com/s0md3v/Arjun](https://github.com/s0md3v/Arjun)
    
- **ParamSpider** – Parameter mining from URLs  
    https://github.com/devanshbatham/ParamSpider]


**FUZZING FILTERING**
https://academy.hackthebox.com/module/280/section/3133