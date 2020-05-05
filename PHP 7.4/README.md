## PHP 7.4 most interesting features
* [Typed properties](#typed-properties)
* [Arrow functions](#arrow-functions)

## Typed properties
Class properties now support type declarations.
```php
class User {
    public int $id;
    public string $name;
}
```
## Arrow functions
Arrow functions provide a shorthand syntax for defining functions with implicit by-value scope binding.
```php
$y = 1;
 
$fn1 = fn($x) => $x + $y;

// equivalent to using $y by value:
$fn2 = function ($x) use ($y) {
    return $x + $y;
};

var_dump($fn1(3)); // output: int(4)

// Another example

$factor = 10;
$nums = array_map(fn($n) => $n * $factor, [1, 2, 3, 4]);
print_r($nums); // Output: [10, 20, 30, 40]
```