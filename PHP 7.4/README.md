## PHP 7.4 most interesting features
* [Typed properties](#typed-properties)
* [Arrow functions](#arrow-functions)
* [Limited return type covariance and argument type contravariance](#limited-return-type-covariance-and-argument-type-contravariance)
* [Null coalescing assignment operator](#null-coalescing-assignment-operator)

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
## Limited return type covariance and argument type contravariance
```php
class A {}
class B extends A {}

class Producer {
    public function method(): A {}
}
class ChildProducer extends Producer {
    public function method(): B {}
}
```
## Null coalescing assignment operator
Coalesce equal or `??=` operator is an assignment operator. If the left parameter is null, assigns the value of the right parameter to the left one. If the value is not null, nothing is done.
```php
$array['key'] ??= computeDefault();

// is roughly equivalent to
if (!isset($array['key'])) {
    $array['key'] = computeDefault();
}
```

## Reference
* **Modern PHP 7.4 Features** ([php.net](https://www.php.net/manual/en/migration74.new-features.php))