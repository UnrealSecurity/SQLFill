# SQLFill
SQLFill prevents SQL injection attacks by properly escaping user input. You basically create a template and then give it some variables to use. This data that will be inserted into the query string and will be properly escaped to prevent potential SQL injection attacks. Currently the two placeholder characters are `$` (no quotes) and `?` (single quotes) and they produce different output for strings, arrays (of strings) and 2d arrays (of strings).
- [PHP](https://github.com/UnrealSecurity/SQLFill/tree/main/sqlfill/php)
