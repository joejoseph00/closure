Opis Closure
====================
[![Build Status](https://travis-ci.org/opis/closure.png)](https://travis-ci.org/opis/closure)
[![Latest Stable Version](https://poser.pugx.org/opis/closure/v/stable.png)](https://packagist.org/packages/opis/closure)
[![Latest Unstable Version](https://poser.pugx.org/opis/closure/v/unstable.png)](https://packagist.org/packages/opis/closure)
[![License](https://poser.pugx.org/opis/closure/license.png)](https://packagist.org/packages/opis/closure)

Serializable closures
---------------------
**Opis Closure** is a library that aims to overcome PHP's limitations regarding closure
serialization by providing a wrapper that will make all closures serializable. 

**The library's key features:**

- Serialize any closure
- Serialize arbitrary objects
- Doesn't use `eval` for closure serialization or unserialization
- Works with any PHP version that has support for closures
- Supports PHP 7.0 syntax
- Handles all variables referenced/imported in `use()` and automatically wraps all referenced/imported closures for
proper serialization
- Handles recursive closures
- Handles magic constants like `__FILE__`, `__DIR__`, `__LINE__`, `__NAMESPACE__`, `__CLASS__`,
`__TRAIT__`, `__METHOD__` and `__FUNCTION__`.
- Automatically resolves all class names, function names and constant names used inside the closure
- Track closure's residing source by using the `#trackme` directive
- Simple and very fast parser
- Any error or exception, that might occur when executing an unserialized closure, can be caught and treated properly
- You can serialize/unserialize any closure unlimited times, even those previously unserialized
(this is possible because `eval()` is not used for unserialization)
- Handles static closures
- Supports cryptographically signed closures
- Provides a reflector that can give you information about the serialized closure
- Provides an analyzer for *SuperClosure* library
- Automatically detects when the scope and/or the bound object of a closure needs to be serialized
in order for the closure to work after deserialization


### License

**Opis Closure** is licensed under the [MIT License (MIT)](http://opensource.org/licenses/MIT). 

### Requirements

* PHP 5.4.* or higher

### Migrating from 2.x

The support for PHP 5.3 was dropped. You can continue using the `2.x` version of **Opis Colibri** if your project needs
to support PHP 5.3, otherwise migrating to version `3.x` is simply a matter of updating your `composer.json` file
(assuming your not using one of the removed classes - see [CHANGELOG](https://github.com/opis/closure/blob/master/CHANGELOG.md)).

### Installation

This library is available on [Packagist](https://packagist.org/packages/opis/closure) and can be installed using [Composer](http://getcomposer.org).

```json
{
    "require": {
        "opis/closure": "3.0.*@dev"
    }
}
```

If you are unable to use [Composer](http://getcomposer.org) you can download the
[tar.gz](https://github.com/opis/closure/archive/3.0.tar.gz) or the [zip](https://github.com/opis/closure/archive/3.0.zip)
archive file, extract the content of the archive and include de `autoload.php` file into your project. 

```php

require_once 'path/to/opis/closure-3.0/autoload.php';

```

### SuperClosure support

**Opis Closure** is shipped with an analyzer(`Opis\Closure\Analyzer`) which 
aims to provide *Opis Closure*'s parsing precision and speed to [SuperClosure](https://github.com/jeremeamia/super_closure).

### Documentation

Examples and documentation can be found [here](http://www.opis.io/closure)
