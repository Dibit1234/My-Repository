
**Webfuzz API**
```shell-session
git clone https://github.com/PandaSt0rm/webfuzz_api.git
cd webfuzz_api
pip3 install -r requirements.txt
```


**Run Command**
```shell-session
python3 api_fuzzer.py http://IP:PORT
```

**Only Successful Commands**
```shell-session
python3 api_fuzzer.py | grep "200"
```

