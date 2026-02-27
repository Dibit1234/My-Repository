**Indicator for SSI**
/page.shtml

**Syntax for a directive:**
```ssi
<!--#name param1="value1" param2="value" -->
```


**Prints all environment variables**
```ssi
<!--#printenv -->
```

**Changes the configuration**
```ssi
<!--#config errmsg="Error!" -->
```

**Prints the value given in VAR**
```ssi
<!--#echo var="DOCUMENT_NAME" var="DATE_LOCAL" -->
```

**Executes a command**
```ssi
<!--#exec cmd="whoami" -->
```

**Includes a file in the web root directory**
```ssi
<!--#include virtual="index.html" -->
```
