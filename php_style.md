# PHP Style Guide

The purpose of this style guide is to outline the programming style and formatting preferred for PHP programs.

There are various existing PHP style guides that have been drawn on in making this guide, including:

- [PHP Framework Interop Group's PSR-12](https://www.php-fig.org/psr/psr-12/)
- [PHP The Right Way](https://phptherightway.com/)
- [CodeIgniter4 Style Guide](https://github.com/codeigniter4/CodeIgniter4/blob/develop/contributing/styleguide.rst)
- [MIT Sloan PHP Code Style Guide](https://mitsloan.mit.edu/shared/content/PHP_Code_Style_Guide.php)

## 1) Files & Coding Structure
- Files must use the UTF-8 character set encoding and must use the UNIX LF (linefeed) line ending
- PHP Elements (Tags) should either be ```<?php  ?> ``` or the short-echo ```<?=  ?>```
- All PHP Class and NameSpace declarations and other configuration and class includes should be placed at the top of the PHP file, even for files containing a mix of HTML and PHP
- Process any GET data, and clear using ```$_GET = [];```, then process any POST data, and clear using ```$_POST = [];``` (and the same with ```$_FILES = []``` if used)
- For in-line comments, include 2 spaces after the code and before the comment, e.g. ```if ($expr) {  // comment```
- For files containing just PHP code, the closing ``` ?> ``` should be omitted
- All files must end with a single empty line
- Filenames should be saved as ```camelCase.php```

## 2) Spacing & Line ending
- PHP code must be indented by 4 spaces for each indent level, unless the code is imbedded within HTML where 2 spaces are allowed
- When including ```<?php  ?>``` in HTML, ensure the ```<?php``` opening element is positioned on the same line as the previous closing HTML ```</...>``` element, to avoid extra whitespace being output
- Each PHP statement should end with a semi-colon ```;``` although when using the short-echo format semi-colons are not required
- There should be no trailing whitespace at the end of lines
- Opening and Closing brackets should be tight to their contents and not have additional spaces within the brackets, e.g. ```($a = $b)```
- Spaces and new lines should be used to align blocks of code, array definitions or long string concatenations to improve code read-ability

## 3) Operators
- Unary operators should not have spaces between the operator and operand, e.g. ```$i++```
- Binary operators should have a space before and after the operator, e.g. ```$variable = ($a + $b) * $c;```. This includes the concatenation operator, e.g. ```$string = "Hello " . "World";```
- For Ternary operators, it is preferable to keep the "if" part in brackets, e.g. ```$variable = ($expr) ? "Yes" : "No";```
- For Logical operators, use the symbol versions ```&&``` and ```||``` instead of ```AND``` and ```OR```
- The Logical negation operator must be separated from its argument with a single space, e.g. ```! $empty()```, whereas the ```!=``` operator should not include extra spaces

## 4) Naming and Declaring
- All PHP keywords must be in lower case
- The keywords ```require ""```, ```require_once ""```, ```include ""``` and ```include_once ""``` are all statements and must be followed by quotes and not brackets
- Boolan values ```true``` and ```false```, as well as ```null``` should all be in lower case
- Class names and namespaces should be declared in PascalCase
- Class methods should be declared in camelCase and must have visibility declarations (e.g. ```private```, ```protected``` or ```public```)
- When instantiating a new class, parentheses must always be present even when there are no arguments passed to the constructor, e.g. ```$variable = new Model();```
- Functions and Variables should be declared in camelCase
- Constants should be declared in CAPITALS_SEPARATED_BY_UNDERSCORES
- Strings should be declared using double-quotes, e.g. ```$string = "Hello World";```
- Variables used within strings should be included within curly brackets, e.g. ```echo "Result: {$result}";```. Use the concatenation operator for more complex strings that include functions, e.g. ```$completed = "Completed on: " . $date("Y-m-d") . " by: " . $user;```
- Arrays should be declared using square brackets, with commas between each item, and with the final item including a trailing comma, e.g. ```$array = [item1, item2,];```

## 5) Functions and Class Methods
- The format (including spacing and braces) of declaring functions is:
```php  
function myFunction(arg1, arg2 = null)
{
    // code;
}
```
- The format (including spacing and braces) of declaring class methods is:
```php  
class ClassName
{
    public function myFunction($arg1, $arg2 = null)
    {
        // code;
    }
}
```
- When making a method or function call there should not be a space between the method or function name and the opening brackets, e.g. ```myFunction("test");``` or ```ClassName->myFunction("test");```
- All functions and methods should be commented with a docblock comment which describes the purpose, parameters and return values

## 6) Control Structures
- The format (including spacing and braces) of control structures is:
```php  
if ($expr) {
    // code;
}
```
- A ```for ``` statement would start: ```for ($i = 0; $i <  10; $i++) {```
- A ```foreach``` statement would start: ```foreach ($iterable as $key => $value) {```
- The keyword ```elseif``` should be used instead of two separeate keywords ```else if```
- When imbedding control structures within HTML the alternative syntax of ```if: elseif: else: endif; / for: endfor; / foreach: endforeach;``` etc. should be used in order to avoid confusion with where to place opening and closing curly brackets
