
**Medusa**
**Download**
```shell-session
sudo apt-get -y update
```
```shell-session
sudo apt-get -y install medusa
```

**Syntax**
```shell-session
medusa [target_options] [credential_options] -M module [module_options]
```

- Perform additional checks for empty passwords (`-e n`) and passwords matching the username (`-e s`).


**Hydra**

**-s PORT**

**Basic Auth Command**
```shell-session
hydra -l USERNAME -P 2023-200_most_used_passwords.txt IP http-get / -s PORT
```

