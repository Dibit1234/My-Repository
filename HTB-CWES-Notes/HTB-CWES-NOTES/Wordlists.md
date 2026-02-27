
**Default Credentials**
CIRT.net

**Copying Wordlists**
```shell-session
curl -LO LINKTOWORDLIST
```

**Username Anarchy - Username generation**
```shell-session
sudo apt install ruby -y
```
```shell-session
git clone https://github.com/urbanadventurer/username-anarchy.git
```

**Example command**
```shell-session
./username-anarchy Jane Smith > jane_smith_usernames.txt
```

**Generate Personalized Passwords**
```shell-session
sudo apt install cupp -y
```
```shell-session
cupp -i
```


**Filtering Word Lists**

- Minimum Length: 6 characters
- Must Include:
    - At least one uppercase letter
    - At least one lowercase letter
    - At least one number
    - At least two special characters (from the set `!@#$%^&*`)

**Alter this command where necessary**
```shell-session
grep -E '^.{6,}$' example.txt | grep -E '[A-Z]' | grep -E '[a-z]' | grep -E '[0-9]' | grep -E '([!@#$%^&*].*){2,}' > example-filtered.txt
```


**Passwords**

| Size   | List            | Approx Entries | Local Path                                                                |
| ------ | --------------- | -------------- | ------------------------------------------------------------------------- |
| Tiny   | Top 10          | 10             | `/usr/share/SecLists/Passwords/Common-Credentials/top-10.txt`             |
| Small  | Top 100         | 100            | `/usr/share/SecLists/Passwords/Common-Credentials/top-100.txt`            |
| Small  | Top 1000        | 1,000          | `/usr/share/SecLists/Passwords/Common-Credentials/top-1000.txt`           |
| Medium | 10k Most Common | 10,000         | `/usr/share/SecLists/Passwords/Common-Credentials/10k-most-common.txt`    |
| Medium | xato-net-10k    | 10,000         | `/usr/share/SecLists/Passwords/xato-net-10-million-passwords-10000.txt`   |
| Large  | xato-net-100k   | 100,000        | `/usr/share/SecLists/Passwords/xato-net-10-million-passwords-100000.txt`  |
| Large  | xato-net-1M     | 1,000,000      | `/usr/share/SecLists/Passwords/xato-net-10-million-passwords-1000000.txt` |

**Usernames**

| Size   | List                   | Approx Entries | Local Path                                                        |
| ------ | ---------------------- | -------------- | ----------------------------------------------------------------- |
| Tiny   | Shortlist              | ~20            | `/usr/share/SecLists/Usernames/top-usernames-shortlist.txt`       |
| Small  | cirt-default-usernames | ~800           | `/usr/share/SecLists/Usernames/cirt-default-usernames.txt`        |
| Medium | names.txt              | ~10k           | `/usr/share/SecLists/Usernames/Names/names.txt`                   |
| Large  | xato-net-10M usernames | 10M            | `/usr/share/SecLists/Usernames/xato-net-10-million-usernames.txt` |

**Directory / Web Content Discovery**

| Size   | List                                   | Approx Entries | Local Path                                                                         |
| ------ | -------------------------------------- | -------------- | ---------------------------------------------------------------------------------- |
| Small  | common.txt                             | ~4k            | `/usr/share/SecLists/Discovery/Web-Content/common.txt`                             |
| Small  | directory-list-lowercase-2.3-small.txt | ~8k            | `/usr/share/SecLists/Discovery/Web-Content/directory-list-lowercase-2.3-small.txt` |
| Medium | directory-list-2.3-medium.txt          | ~220k          | `/usr/share/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt`          |
| Medium | raft-medium-directories.txt            | ~30k           | `/usr/share/SecLists/Discovery/Web-Content/raft-medium-directories.txt`            |
| Large  | directory-list-2.3-big.txt             | ~870k          | `/usr/share/SecLists/Discovery/Web-Content/directory-list-2.3-big.txt`             |
| Large  | raft-large-directories.txt             | ~600k+         | `/usr/share/SecLists/Discovery/Web-Content/raft-large-directories.txt`             |

**Fuzzing Wordlists**

|Size|List|Use Case|Local Path|
|---|---|---|---|
|Small|fuzz.txt|Basic fuzzing|`/usr/share/SecLists/Fuzzing/fuzz.txt`|
|Small|special-chars.txt|Special char testing|`/usr/share/SecLists/Fuzzing/special-chars.txt`|
|Medium|LFI-Jhaddix.txt|LFI testing|`/usr/share/SecLists/Fuzzing/LFI/LFI-Jhaddix.txt`|
|Medium|command-injection.txt|Command injection|`/usr/share/SecLists/Fuzzing/Command-Injection/command-injection.txt`|
|Large|all-attacks.txt|Large mixed fuzz list|`/usr/share/SecLists/Fuzzing/` (multiple lists)|

SQL Injection Wordlists

| Size   | List             | Approx Entries | Local Path                                          |
| ------ | ---------------- | -------------- | --------------------------------------------------- |
| Small  | quick-SQLi.txt   | ~50            | `/usr/share/SecLists/Fuzzing/SQLi/quick-SQLi.txt`   |
| Medium | Generic-SQLi.txt | ~1k            | `/usr/share/SecLists/Fuzzing/SQLi/Generic-SQLi.txt` |
| Medium | SQLi-Union.txt   | ~hundreds      | `/usr/share/SecLists/Fuzzing/SQLi/`                 |
| Large  | Full SQLi folder | 1k+            | `/usr/share/SecLists/Fuzzing/SQLi/`                 |

**Subdomain Enumeration**

| Size   | List                              | Approx Entries | Local Path                                                            |
| ------ | --------------------------------- | -------------- | --------------------------------------------------------------------- |
| Small  | subdomains-top1million-5000.txt   | 5k             | `/usr/share/SecLists/Discovery/DNS/subdomains-top1million-5000.txt`   |
| Medium | subdomains-top1million-20000.txt  | 20k            | `/usr/share/SecLists/Discovery/DNS/subdomains-top1million-20000.txt`  |
| Large  | subdomains-top1million-110000.txt | 110k           | `/usr/share/SecLists/Discovery/DNS/subdomains-top1million-110000.txt` |
