# PHP Syntax Guide
My PHP Syntax Guide

## PHP Comments
Comments help make your code more readable and describe what is going on within the PHP. Comments are ignored by the PHP engine.

```
// single line comment
# single line comment
/* multi-line comment */
```

## PHP Variables
Variables begin with $ and are used to store data

```
$var = "My variable";
```

**It's important to note that variable names are case sensitive. $var is not the same are $Var**
### A few more rules:
* No spaces can be used
* Only alpha-numeric characters and underscores can be used (0-9, a-z & _)
* Variable names must begin with a letter or underscore, not a number

## PHP Echo/ Print
Echo & Print are both used to display output to the browser. Print can only output one string and always returns 1, whereas echo can print multiple strings and does not return any value which makes it faster. HTML code can also be used in both echo and print statements to format what is printed to the screen.

```
<?php
  print "This text will print to the screen!";
?>
```
```
<?php
  $color = 'purple';
  echo "My favorite color is " . $color;
?>
```

## PHP Data Types
There are eight data types supported in PHP: Integer, Float, String, Booleans, Array, Object, Resource and NULL.
### PHP Integer 
The integer data type is a non-decimal number that must have at least one digit that can be either positive or negative. They can be specified in decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation.

```
$integer = 1234;
```

### PHP Float
Also known as floating point numbers, doubles or real numbers, the float data type is a exponential or decimal number.
```
$float = 12.345;
```

### PHP String
A string is a sequence of characters (letters, numbers or special characters) inside double or single quotes. Every character equals a byte.
```
$string = "This is my string example.";
```

### PHP Booleans
Booleans represent two values, either 0(false) or 1(true). Booleans are often used for conditional testing. 
```
$boolean1 = true;
$boolean2 = false;
```

### PHP Arrays
An array holds multiple values within one variable. 
```
$shapes = array("circle", "square", "triangle");
```

### PHP Object

### PHP Resource

### PHP NULL
Null is a data type that can only have one value - NULL. This represents an empty variable. If a variable's data type is NULL, this means there has been no value assigned. 
``` 
$var1 = NULL; // has NULL value
$var2 = ""; // has no value assigned
```

## PHP Strings
Strings are a sequence and/or combination of numbers, letters, special characters and arithmetic values. Double quotations marks can be used, however it's best practice to use single quotation marks as they are treated almost literally. There are many built-in string functions within PHP, here are a few:
strlen() - calculate number of characters (and blank spaces) inside a string
```
<?php
  $first_string = 'How many characters and spaces here';
  echo strlen($first_string); // Outputs 35
?>
```
str_word_count() - counts the number of words in a string
```
<?php
  $second_string = 'Yesterday my car was stuck in the snow';
  echo str_word_count($second_string); // Outputs 8
 ?>
```
str_replace() - replaces selected text within the string
```
<?php
  $third_string = 'First I was wrong, then I was right.'
  echp str_replace("wrong", "right", $third_string);
  // Outputs 'First I was right, then I was wrong.'
 ?>
```
strrev() - reverse a string
```
<?php
  $fourth_string = 'Hello, is it me you're looking for?'
  echo strrev($fourth_string);
  // Outputs '?rof gnikool er'uoy em ti si ,oellH'
 ?>
 ```
See [PHP Strings](https://www.tutorialrepublic.com/php-reference/php-string-functions.php "PHP Strings") for a complete list of string functions. 

## PHP Numbers

## PHP Constants
Constants are used when storing data (aka a fixed value) that doesn't change. Unlike PHP variable, constants do not begin with a $ but rather a letter or underscore. They are definited using the `define()` function, that takes 1)the name of the constant and 2)the value as arguments. 

```
<?php
  define("GREETING", "Thank you for visting our website! We look forward to serving you.");
?>
```

## PHP Operators
Operators in PHP are symbols that perform certain actions with variables and actions. It can be broken down into:
*Arithmetic operators
*Assignment operators
*Comparison operators
*Increment/Decrement operators
*Logical operators
*String operators
*Array operators
*Conditional assignment operators

### Arithmetic Operators
Arithmetic operators are used with numbers to perform common operations such as division, addition, subtraction, etc
```
Operator	Name	          Example	    Result	
+	        Addition	      $x + $y	    Sum of $x and $y	
-	        Subtraction	    $x - $y	    Difference of $x and $y	
*	        Multiplication	$x * $y	    Product of $x and $y	
/	        Division	      $x / $y	    Quotient of $x and $y	
%	        Modulus	        $x % $y	    Remainder of $x divided by $y	
**    	    Exponentiation	$x ** $y	  Result of raising $x to the $y'th power
```
## PHP If & Else & ElseIf

## PHP Functions

## PHP Arrays

## PHP Loops
