
**Decoding Base64**
```shell-session
echo -n dXNlcj1odGItc3RkbnQ7cm9sZT11c2Vy | base64 -d
```

**Encoding Base 64**
```shell-session
echo -n 'user=htb-stdnt;role=admin' | base64
```

**Decoding Hex**
```shell-session
echo 757365723d6874622d7374646e743b726f6c653d75736572 | xxd -r -p
```

**Encoding Hex**
```shell-session
echo -n "user=test;role=admin" | xxd -p
```
