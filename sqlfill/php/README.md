## Example 1
Code:
```php
<?php

    require_once 'sqlfill/php/sqlfill.php';
    $sql = new SQLFill($host, $user, $pass, $dbname, $port = 3306);

    $table  = 'Customers';
    $fields = ['CustomerName', 'ContactName', 'Address', 'City', 'PostalCode', 'Country'];
    $values = [
        ['Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'],
        ['Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway']
    ];

    $result = $sql->fill('INSERT INTO $ $ VALUES ?', $table, $fields, $values)->query(); /* --> SQLFillResult */

?>
```
SQL query:
```sql
INSERT INTO Customers (CustomerName,ContactName,Address,City,PostalCode,Country) VALUES ('Cardinal','Tom B. Erichsen','Skagen 21','Stavanger','4006','Norway'),('Cardinal','Tom B. Erichsen','Skagen 21','Stavanger','4006','Norway')
```

## Example 2
Code:
```php
<?php

    require_once 'sqlfill/php/sqlfill.php';
    $sql = new SQLFill($host, $user, $pass, $dbname, $port = 3306);

    $result = $sql->fill('SELECT & FROM $ WHERE Country = ?', 
        ['FirstName', 'LastName'], 'Customers', 'FI')->query(); /* --> SQLFillResult */

?>
```
SQL query:
```sql
SELECT FirstName, LastName FROM Customers WHERE Country = 'FI'
```
