## Laravel 5 Helpers for Non-Laravel Projects

This project takes the useful [Laravel helper functions](http://laravel.com/docs/5.4/helpers) and allows you to use them in Non-Laravel projects.

All dependencies have been extracted out to a single helpers file. No need to import half of Symphony and Laravel to make these work.

## Setup

In your `composer.json`:

```json
{
    "repositories": [{
        "type": "vcs",
        "url": "https://github.com/invokemedia/laravel-helpers"
    }],
    "require": {
        "invokemedia/laravel-helpers": "master"
    }
}
```

## Documentation

* [Arrays](#arrays)
    * [append_config](#append_config)
    * [array_add](#array_add)
    * [array_build](#array_build)
    * [array_divide](#array_divide)
    * [array_dot](#array_dot)
    * [array_except](#array_except)
    * [array_fetch](#array_fetch)
    * [array_first](#array_first)
    * [array_last](#array_last)
    * [array_flatten](#array_flatten)
    * [array_forgot](#array_forgot)
    * [array_get](#array_get)
    * [array_has](#array_has)
    * [array_only](#array_only)
    * [array_pluck](#array_pluck)
    * [array_prepend](#array_prepend)
    * [array_pull](#array_pull)
    * [array_set](#array_set)
    * [array_where](#array_where)
    * [array_wrap](#array_wrap)
    * [head](#head)
    * [last](#last)
* [Strings](#strings)
    * [ascii](#ascii)
    * [camel_case](#camel_case)
    * [charsArray](#charsArray)
    * [ends_with](#ends_with)
    * [preg_replace_sub](#preg_replace_sub)
    * [snake_case](#snake_case)
    * [starts_with](#starts_with)
    * [str_contains](#str_contains)
    * [str_finish](#str_finish)
    * [str_is](#str_is)
    * [str_limit](#str_limit)
    * [str_random](#str_random)
    * [str_replace_array](#str_replace_array)
    * [str_slug](#str_slug)
    * [studly_case](#studly_case)
    * [title_case](#title_case)
* [Classes](#classes)
    * [class_basename](#class_basename)
    * [class_uses_recursive](#class_uses_recursive)
    * [trait_uses_recursive](#trait_uses_recursive)
* [Misc.](#misc)
    * [data_get](#data_get)
    * [e](#e)
    * [object_get](#object_get)
    * [value](#value)
    * [with](#with)

## Arrays

### append_config

```php
/**
	 * Assign high numeric IDs to a config item to force appending.
	 *
	 * @param  array  $array
	 * @return array
*/
function append_config(array $array)
```

### array_add

```php
/**
	 * Add an element to an array using "dot" notation if it doesn't exist.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @param  mixed   $value
	 * @return array
*/
function array_add($array, $key, $value)
```

### array_build

```php
/**
	 * Build a new array using a callback.
	 *
	 * @param  array     $array
	 * @param  \Closure  $callback
	 * @return array
*/
function array_build($array, Closure $callback)
```

### array_divide

```php
/**
	 * Divide an array into two arrays. One with keys and the other with values.
	 *
	 * @param  array  $array
	 * @return array
*/
function array_divide($array)
```

### array_dot

```php
/**
	 * Flatten a multi-dimensional associative array with dots.
	 *
	 * @param  array   $array
	 * @param  string  $prepend
	 * @return array
*/
function array_dot($array, $prepend = '')
```

### array_except

```php
/**
	 * Get all of the given array except for a specified array of items.
	 *
	 * @param  array  $array
	 * @param  array|string  $keys
	 * @return array
*/
function array_except($array, $keys)
```

### array_fetch

```php
/**
	 * Fetch a flattened array of a nested array element.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @return array
*/
function array_fetch($array, $key)
```

### array_first

```php
/**
	 * Return the first element in an array passing a given truth test.
	 *
	 * @param  array     $array
	 * @param  \Closure  $callback
	 * @param  mixed     $default
	 * @return mixed
*/
function array_first($array, $callback, $default = null)
```

### array_last

```php
/**
	 * Return the last element in an array passing a given truth test.
	 *
	 * @param  array     $array
	 * @param  \Closure  $callback
	 * @param  mixed     $default
	 * @return mixed
*/
function array_last($array, $callback, $default = null)
```

### array_flatten

```php
/**
	 * Flatten a multi-dimensional array into a single level.
	 *
	 * @param  array  $array
	 * @return array
*/
function array_flatten($array)
```

### array_forgot

```php
/**
	 * Remove one or many array items from a given array using "dot" notation.
	 *
	 * @param  array  $array
	 * @param  array|string  $keys
	 * @return void
*/
function array_forget(&$array, $keys)
```

### array_get

```php
/**
	 * Get an item from an array using "dot" notation.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @param  mixed   $default
	 * @return mixed
*/
function array_get($array, $key, $default = null)
```

### array_has

```php
/**
	 * Check if an item exists in an array using "dot" notation.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @return bool
*/
function array_has($array, $key)
```

### array_only

```php
/**
	 * Get a subset of the items from the given array.
	 *
	 * @param  array  $array
	 * @param  array|string  $keys
	 * @return array
*/
function array_only($array, $keys)
```

### array_pluck

```php
/**
	 * Pluck an array of values from an array.
	 *
	 * @param  array   $array
	 * @param  string  $value
	 * @param  string  $key
	 * @return array
*/
function array_pluck($array, $value, $key = null)
```

### array_pluck

```php
/**
 * Push an item onto the beginning of an array.
 *
 * @param  array  $array
 * @param  mixed  $value
 * @param  mixed  $key
 * @return array
 */
function prepend($array, $value, $key = null)
```

### array_pull

```php
/**
	 * Get a value from the array, and remove it.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @param  mixed   $default
	 * @return mixed
*/
function array_pull(&$array, $key, $default = null)
```

### array_set

```php
/**
	 * Set an array item to a given value using "dot" notation.
	 *
	 * If no key is given to the method, the entire array will be replaced.
	 *
	 * @param  array   $array
	 * @param  string  $key
	 * @param  mixed   $value
	 * @return array
*/
function array_set(&$array, $key, $value)
```

### array_where

```php
/**
	 * Filter the array using the given Closure.
	 *
	 * @param  array     $array
	 * @param  \Closure  $callback
	 * @return array
*/
function array_where($array, Closure $callback)
```

### array_wrap

```php
/**
 * If the given value is not an array, wrap it in one.
 *
 * @param  mixed  $value
 * @return array
 */
function wrap($value)
```

### head

```php
/**
	 * Get the first element of an array. Useful for method chaining.
	 *
	 * @param  array  $array
	 * @return mixed
*/
function head($array)
```

### last

```php
/**
	 * Get the last element from an array.
	 *
	 * @param  array  $array
	 * @return mixed
*/
function last($array)
```

## Strings

### ascii

```php
/**
     * Transliterate a UTF-8 value to ASCII.
     *
     * @param  string  $value
     * @return string
 */
function ascii($value)
```

### camel_case

```php
/**
	 * Convert a value to camel case.
	 *
	 * @param  string  $value
	 * @return string
*/
function camel_case($value)
```

### charsArray

```php
/**
     * Returns the replacements for the ascii method.
     *
     * Note: Adapted from Stringy\Stringy.
     *
     * @see https://github.com/danielstjules/Stringy/blob/2.3.1/LICENSE.txt
     *
     * @return array
 */
function charsArray()
```

### ends_with

```php
/**
	 * Determine if a given string ends with a given substring.
	 *
	 * @param  string  $haystack
	 * @param  string|array  $needles
	 * @return bool
*/
function ends_with($haystack, $needles)
```

### preg_replace_sub

```php
/**
	 * Replace a given pattern with each value in the array in sequentially.
	 *
	 * @param  string  $pattern
	 * @param  array   $replacements
	 * @param  string  $subject
	 * @return string
*/
function preg_replace_sub($pattern, &$replacements, $subject)
```

### snake_case

```php
/**
	 * Convert a string to snake case.
	 *
	 * @param  string  $value
	 * @param  string  $delimiter
	 * @return string
*/
function snake_case($value, $delimiter = '_')
```

### starts_with

```php
/**
	 * Determine if a given string starts with a given substring.
	 *
	 * @param  string  $haystack
	 * @param  string|array  $needles
	 * @return bool
*/
function starts_with($haystack, $needles)
```

### str_contains

```php
/**
	 * Determine if a given string contains a given substring.
	 *
	 * @param  string  $haystack
	 * @param  string|array  $needles
	 * @return bool
*/
function str_contains($haystack, $needles)
```

### str_finish

```php
/**
	 * Cap a string with a single instance of a given value.
	 *
	 * @param  string  $value
	 * @param  string  $cap
	 * @return string
*/
function str_finish($value, $cap)
```

### str_is

```php
/**
	 * Determine if a given string matches a given pattern.
	 *
	 * @param  string  $pattern
	 * @param  string  $value
	 * @return bool
*/
function str_is($pattern, $value)
```

### str_limit

```php
/**
	 * Limit the number of characters in a string.
	 *
	 * @param  string  $value
	 * @param  int     $limit
	 * @param  string  $end
	 * @return string
*/
function str_limit($value, $limit = 100, $end = '...')
```

### str_random

```php
/**
	 * Generate a more truly "random" alpha-numeric string.
	 *
	 * @param  int  $length
	 * @return string
	 *
	 * @throws \RuntimeException
*/
function str_random($length = 16)
```

### str_replace_array

```php
/**
	 * Replace a given value in the string sequentially with an array.
	 *
	 * @param  string  $search
	 * @param  array   $replace
	 * @param  string  $subject
	 * @return string
*/
function str_replace_array($search, array $replace, $subject)
```

### str_slug

```php
/**
	 * Generate a URL friendly "slug" from a given string.
	 *
	 * @param  string  $title
	 * @param  string  $separator
	 * @return string
*/
function str_slug(string $title, string $separator = '-')
```

### studly_case

```php
/**
	 * Convert a value to studly caps case.
	 *
	 * @param  string  $value
	 * @return string
*/
function studly_case($value)
```

### title_case

```php
/**
 * Convert the given string to title case.
 *
 * @param  string  $value
 * @return string
 */
function title_case($value)
```

## Classes

### class_basename

```php
/**
	 * Get the class "basename" of the given object / class.
	 *
	 * @param  string|object  $class
	 * @return string
*/
function class_basename($class)
```

### class_uses_recursive

```php
/**
	 * Returns all traits used by a class, it's subclasses and trait of their traits
	 *
	 * @param  string  $class
	 * @return array
*/
function class_uses_recursive($class)
```

### trait_uses_recursive

```php
/**
	 * Returns all traits used by a trait and its traits
	 *
	 * @param  string  $trait
	 * @return array
*/
function trait_uses_recursive($trait)
```

## Misc.

### data_get

```php
/**
	 * Get an item from an array or object using "dot" notation.
	 *
	 * @param  mixed   $target
	 * @param  string  $key
	 * @param  mixed   $default
	 * @return mixed
*/
function data_get($target, $key, $default = null)
```

### e

```php
/**
	 * Escape HTML entities in a string.
	 *
	 * @param  string  $value
	 * @return string
*/
function e($value)
```

### object_get

```php
/**
	 * Get an item from an object using "dot" notation.
	 *
	 * @param  object  $object
	 * @param  string  $key
	 * @param  mixed   $default
	 * @return mixed
*/
function object_get($object, $key, $default = null)
```

### value

```php
/**
	 * Return the default value of the given value.
	 *
	 * @param  mixed  $value
	 * @return mixed
*/
function value($value)
```

### with

```php
/**
	 * Return the given object. Useful for chaining.
	 *
	 * @param  mixed  $object
	 * @return mixed
*/
function with($object)
```