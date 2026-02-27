
**Some PHP functions**
`include_once()`, `require()`, `require_once()`, `file_get_contents()`, `include()`
```php
if (isset($_GET['language'])) {
    include($_GET['language']);
}
```
 
**NodeJs**
`readfile()`, `render()`
```javascript
    fs.readFile(path.join(__dirname, req.query.language), function (err, data) {
```

**Java**
`include()`, `import()`
```jsp
    <jsp:include file="<%= request.getParameter('language') %>" />
```

.NET
`Response.WriteFile()`, `@Html.Partial()`
```cs
<% Response.WriteFile("<% HttpContext.Request.Query['language'] %>"); %> 
```
```cs
<!--#include file="<% HttpContext.Request.Query['language'] %>"-->
```

**Check for RFI (Remote File Inclusion)**
**Example:**
```shell-session
php://filter/read=convert.base64-encode/resource=../../../../etc/php/7.4/apache2/php.ini"
```

Check for permissions in config files:
```shell-session
echo 'BASE64STRING' | base64 -d | grep allow_url_include
```


| **Function**                 | **Read Content** | **Execute** | **Remote URL** |
| ---------------------------- | :--------------: | :---------: | :------------: |
| **PHP**                      |                  |             |                |
| `include()`/`include_once()` |        ✅         |      ✅      |       ✅        |
| `require()`/`require_once()` |        ✅         |      ✅      |       ❌        |
| `file_get_contents()`        |        ✅         |      ❌      |       ✅        |
| `fopen()`/`file()`           |        ✅         |      ❌      |       ❌        |
| **NodeJS**                   |                  |             |                |
| `fs.readFile()`              |        ✅         |      ❌      |       ❌        |
| `fs.sendFile()`              |        ✅         |      ❌      |       ❌        |
| `res.render()`               |        ✅         |      ✅      |       ❌        |
| **Java**                     |                  |             |                |
| `include`                    |        ✅         |      ❌      |       ❌        |
| `import`                     |        ✅         |      ✅      |       ✅        |
| **.NET**                     |                  |             |                |
| `@Html.Partial()`            |        ✅         |      ❌      |       ❌        |
| `@Html.RemotePartial()`      |        ✅         |      ❌      |       ✅        |
| `Response.WriteFile()`       |        ✅         |      ❌      |       ❌        |
| `include`                    |        ✅         |      ✅      |       ✅        |
