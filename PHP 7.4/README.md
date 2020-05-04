## PHP 7.4 most interesting features
* [Typed properties](#typed-properties)
* [Arrow functions](#arrow-functions)

### Typed properties
Class properties now support type declarations.
```php
class User {
    public int $id;
    public string $name;
}
```
### Arrow functions
Arrow functions provide a shorthand syntax for defining functions with implicit by-value scope binding.