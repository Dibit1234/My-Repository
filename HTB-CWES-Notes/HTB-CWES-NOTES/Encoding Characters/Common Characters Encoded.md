| Character                | URL Encoding | Hex (ASCII) | Base64 | HTML Entity | Python Escape | Notes / Other                      |
| ------------------------ | ------------ | ----------- | ------ | ----------- | ------------- | ---------------------------------- |
| Space                    | `%20`        | `0x20`      | `IA==` | `&#32;`     | `\x20`        | `+` in URL query strings           |
| Exclamation `!`          | `%21`        | `0x21`      | `IQ==` | `&#33;`     | `\x21`        | Used in shell or regex             |
| Double Quote `"`         | `%22`        | `0x22`      | `Ig==` | `&quot;`    | `\"`          | Important in HTML/JS strings       |
| Hash `#`                 | `%23`        | `0x23`      | `Iw==` | `&#35;`     | `\x23`        | Fragment in URLs                   |
| Dollar `$`               | `%24`        | `0x24`      | `JA==` | `&#36;`     | `\x24`        | Shell variable symbol              |
| Percent `%`              | `%25`        | `0x25`      | `JQ==` | `&#37;`     | `\x25`        | Used in URL encoding itself        |
| Ampersand `&`            | `%26`        | `0x26`      | `Jg==` | `&amp;`     | `\x26`        | Query string separator             |
| Single Quote `'`         | `%27`        | `0x27`      | `Jw==` | `&#39;`     | `\'`          | SQL / JS injection sensitive       |
| Left Parenthesis `(`     | `%28`        | `0x28`      | `KA==` | `&#40;`     | `\x28`        | Function calls, grouping           |
| Right Parenthesis `)`    | `%29`        | `0x29`      | `KQ==` | `&#41;`     | `\x29`        | Function calls, grouping           |
| Asterisk `*`             | `%2A`        | `0x2A`      | `Kg==` | `&#42;`     | `\x2A`        | Wildcard in shell or regex         |
| Plus `+`                 | `%2B`        | `0x2B`      | `Kw==` | `&#43;`     | `\x2B`        | Space replacement in query strings |
| Comma `,`                | `%2C`        | `0x2C`      | `LA==` | `&#44;`     | `\x2C`        | CSV or argument separator          |
| Minus `-`                | `%2D`        | `0x2D`      | `LQ==` | `&#45;`     | `\x2D`        | Shell, regex, numbers              |
| Period `.`               | `%2E`        | `0x2E`      | `Lg==` | `&#46;`     | `\x2E`        | File paths, decimal point          |
| Slash `/`                | `%2F`        | `0x2F`      | `Lw==` | `&#47;`     | `\/`          | Path separator                     |
| Colon `:`                | `%3A`        | `0x3A`      | `Og==` | `&#58;`     | `\x3A`        | Time, URLs                         |
| Semicolon `;`            | `%3B`        | `0x3B`      | `Ow==` | `&#59;`     | `\x3B`        | Command separator in shell         |
| Less Than `<`            | `%3C`        | `0x3C`      | `PA==` | `&lt;`      | `\x3C`        | HTML / XML tag start               |
| Greater Than `>`         | `%3E`        | `0x3E`      | `Pg==` | `&gt;`      | `\x3E`        | HTML / XML tag end                 |
| Question Mark `?`        | `%3F`        | `0x3F`      | `Pw==` | `&#63;`     | `\x3F`        | URL query start                    |
| At `@`                   | `%40`        | `0x40`      | `QA==` | `&#64;`     | `\x40`        | Email or shell symbol              |
| Backslash `\`            | `%5C`        | `0x5C`      | `XA==` | `&#92;`     | `\\`          | Escape character                   |
| Caret `^`                | `%5E`        | `0x5E`      | `Xg==` | `&#94;`     | `\x5E`        | Regex / shell                      |
| Underscore `_`           | `%5F`        | `0x5F`      | `_w==` | `&#95;`     | `\x5F`        | Variable naming                    |
| Grave / Backtick `` ` `` | `%60`        | `0x60`      | `YA==` | `&#96;`     | `\x60`        | Command substitution in shell      |
| Pipe `                   | `            | `%7C`       | `0x7C` | `fA==`      | `&#124;`      | `\x7C`                             |
| Tilde `~`                | `%7E`        | `0x7E`      | `fg==` | `&#126;`    | `\x7E`        | Home dir, shell                    |