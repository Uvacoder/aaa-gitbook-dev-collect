# PHP

|  |  |
| :--- | :--- |
| [PHP is a great language](https://gomakethings.com/php-is-a-great-language/) | 6/14/2021 |
| [date documentation](https://www.php.net/manual/en/function.date.php) | 12/10/2019 |

### Display contents of variable

```php
//browser will display all contents of that $menu
var_dump($menu);
```

### Arrays

{% code title="Arrays" %}
```php
//first way to write an array
$array[0] = "first item"
$array[1] = "second item"
$array[2] = "third item"

//second way to write an array
$array = array(
    0 => "first item",
    1 => "second item",
    2 => "third item"
    );
```
{% endcode %}

### Cookie

```php
<?php
setcookie(cookie_name, cookie_value, [expiry_time], [cookie_path], [domain], [secure], [httponly]);
?>
```

|  |  |
| :--- | :--- |
| asort | This function is used to sort the array using the values. |
| &lt;&lt;&lt;EOT | acronym for `end of text`, string delimiter |
| ksort | This function is used to sort the array using the key. |
| [print\_r](https://www.php.net/manual/en/function.print-r.php) | Prints human-readable information about a variable |
| var\_dump | browser will display all contents of that variable |

