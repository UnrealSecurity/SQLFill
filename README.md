# SQLFill
SQLFill prevents SQL injection attacks by properly escaping user input. You basically create a template and then give it some variables to use. This data that will be inserted into the query string will be properly escaped to prevent potential SQL injection attacks. Currently the three placeholder characters are `$` (no quotes), `?` (single quotes) and `&` (no quotes & no brackets) and they produce different output for strings, arrays (of strings) and 2d arrays (of strings).
- [PHP](https://github.com/UnrealSecurity/SQLFill/tree/main/sqlfill/php)

| Symbol 	| Data 	| Result 	|
|-:	|-	|-	|
| & 	| `'a'` 	| `a` 	|
|  	| `['a', 'b']` 	| `a, b` 	|
| $ 	| `'a'` 	| `a` 	|
|  	| `['a', 'b']` 	| `(a, b)` 	|
| ? 	| `'a'` 	| `'a'` 	|
|  	| `['a', 'b']` 	| `('a', 'b')` 	|
|  	| `[['a', 'b'], ['a', 'b']]` 	| `('a', 'b'), ('a', 'b')` 	|
