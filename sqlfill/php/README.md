Example 1
```php
<?php

    require_once 'sqlfill/php/sqlfill.php';
    $sql = new SQLFill($host, $user, $pass, $dbname, $port);

    $result = $sql->fill('SELECT * FROM $', 'offices')->query(); /* --> SQLFillResult */
    while ($row = $result->fetch()) {
        $name = $row['Name'];
        echo "$name<br />";
    }

?>
```

Example 2
```php
<?php

    require_once 'sqlfill/php/sqlfill.php';
    $sql = new SQLFill($host, $user, $pass, $dbname);

    $table  = 'Customers';
    $fields = ['CustomerName', 'ContactName', 'Address', 'City', 'PostalCode', 'Country'];
    $values = [
        ['Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'],
        ['Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway']
    ];

    $result = $sql->fill('INSERT INTO $ $ VALUES ?', $table, $fields, $values)->query(); /* --> SQLFillResult */

?>
```
