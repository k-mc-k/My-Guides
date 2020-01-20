# PHP Syntax Guide

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
The integer data type is a non-decimal number that must have at least one digit that can be either positive or negative. They can be specified in decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation. **See more detail under the PHP Numbers heading

```
$integer = 1234;
```

### PHP Float
Also known as floating point numbers, doubles or real numbers, the float data type is a exponential or decimal number. **See more detail under the PHP Numbers heading
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
A class is a template for objects, and an object is an instance of class. Multiple objects can be created from a class and each object has the properties and methods defined in the class, however different property values.
```
<?php
class junkFood {
  public $name;
  public $type;

  function set_name($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
  function set_type($type) {
    $this->type = $type;
  }
  function get_type() {
    return $this->type;
  }
}

$KitKat = new junkFood();
$KitKat->set_name('KitKat');
$KitKat->set_type('cholocate bar');
echo "Name: " . $KitKat->get_name();
echo "<br>";
echo "Type: " .  $KitKat->get_type();
?>
```
### PHP Resource
A resource is a special variable, not an actual data type, that holds special handlers to an external source such as open files, database connections, image areas, etc. In the below example, we are creating a file resource object reference: 
```
$fp = fopen("index.php",'r');
```

### PHP NULL
Null is a data type that can only have one value - NULL. This represents an empty variable. 
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
  echo strlen($first_string); 
  // Outputs 35
?>
```
str_word_count() - counts the number of words in a string
```
<?php
  $second_string = 'Yesterday my car was stuck in the snow';
  echo str_word_count($second_string); 
  // Outputs 8
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
PHP provides automatic data type conversions, meaning if you assign an integer value to a variable, the datantype of that variable will be an integer. On the next line, this variable could change to a string if you assign a string to the same variable. There are different types of Numbers in PHP: Integers, Floats, Infinity, NaN.
### PHP Integer
An integer is a negative or positive number without a decimal point that ranges between -2147483648 and 2147483647. Any value lower or greater is considered a float. An integer must have at least one digit and it's important to note that even if the result is a whole number, if there is any decimal number being used, the result will be stored as a float (ie. 2 * 1.5 = 3). PHP has the below functions to check if a variable's data type is an integer:
* is_int()
* is_integer()
* is_long()
```
<?php
  $int = 40;
  var_dump(is_int($int));
  // Outputs true as it's a non-decimal number
?>
```
### PHP Floats
Opposite of integer, float is a number with a decimal point or exponent. The typical max value is 1.7976921248623E+308 depending on the platform, and has a maximum precision on 14 digits. PHP has the below functions to check if a variable's data type is a float:
* is_float()
* is_double()
```
<?php
  $flt = 12.345;
  var_dump(is_float($flt));
  // Outputs true has $flt is a decimal number
?>
```
### PHP Infinity
A value that exceeds the float max is considered infinite. PHP has the below functions to check if a variable's data type is finite or infinite:
* is_finite()
* is_infinite()
Note that PHP's var_dump() function returns the value and data type as well.
```
<?php
  $inf = 1.9e411;
  var_dump($inf);
  // Outputs float(INF)
?>
```
### PHP NaN
NaN stands for 'Not a Number' and is used for impossible operations. Like infinity, NaN can use the PHP function var_dump() to return the value and data type, the below function can also be used:
* is_nan()
```
<?php
  $numb = test(7);
  var_dump($numb);
  // Outputs float(NAN)
  // if $numb = 7, Outputs int(8)
?>
```
## PHP Constants
Constants are used when storing data (aka a fixed value) that doesn't change. Unlike PHP variable, constants do not begin with a $ but rather a letter or underscore. They are definited using the `define()` function, that takes 1) the name of the constant and 2) the value as arguments. 

```
<?php
  define("GREETING", "Thank you for visting our website! We look forward to serving you.");
?>
```

## PHP Operators
Operators in PHP are symbols that perform certain actions with variables and actions. It can be broken down into:
* Arithmetic operators
* Assignment operators
* Comparison operators
* Increment/Decrement operators
* Logical operators
* String operators
* Array operators
* Conditional assignment operators

### Arithmetic Operators
Arithmetic operators are used with numbers to perform common operations such as division, addition, subtraction, etc.
```
Operator	Name	            Example	      Result	
+	        Addition	        $x + $y	      Sum of $x and $y	
-	        Subtraction	      $x - $y	      Difference of $x and $y	
*	        Multiplication	  $x * $y	      Product of $x and $y	
/	        Division	        $x / $y	      Quotient of $x and $y	
%	        Modulus	          $x % $y	      Remainder of $x divided by $y	
**    	  Exponentiation	  $x ** $y	    Result of raising $x to the $y'th power
```
```
<?php
  $x = 11;  
  $y = 9;
  echo $x + $y;
  // Outputs 20
?>  
```
### Assignment Operators
Assignment operators are used to assign a value to a variable. The basic assignment operators in PHP is '='.
```
Assignment	    Same as...	    Description
x = y	          x = y	          The left operand gets set to the value of the expression on the right	
x += y	        x = x + y	      Addition	
x -= y	        x = x - y	      Subtraction	
x *= y	        x = x * y	      Multiplication	
x /= y	        x = x / y	      Division	
x %= y	        x = x % y	      Modulus
```
```
<?php
 $x = 80;  
 $x += 200;
 echo $x;
 // Outputs 280
?> 
```
### Comparison Operators
Comparison operators are used to compare two values (number or string) in a Boolean fashion.
```
Operator	      Name	                Example	          Result
==	            Equal	                $x == $y	        Returns true if $x is equal to $y	
===	            Identical	            $x === $y	        Returns true if $x is equal to $y, and they are of the same type	
!=	            Not equal	            $x != $y	        Returns true if $x is not equal to $y	
<>	            Not equal	            $x <> $y	        Returns true if $x is not equal to $y	
!==	            Not identical	        $x !== $y	      Returns true if $x is not equal to $y, or they are not of the same type	
>	              Greater than	        $x > $y	          Returns true if $x is greater than $y	
<	              Less than	            $x < $y	          Returns true if $x is less than $y	
>=	            Greater than or equal to	$x >= $y	    Returns true if $x is greater than or equal to $y	
<=	            Less than or equal to	$x <= $y	        Returns true if $x is less than or equal to $y	
<=>	            Spaceship	            $x <=> $y	        Returns an integer less than, equal to, or greater than zero,     depending on if $x is less than, equal to, or greater than $y. Introduced in PHP 7.	
```
```
<?php
  $numb1 = 25;
  $numb2 = 70;
  var_dump($x < $y); 
  // Returns true because $numb1 is less than $numb2
?> 
```
### Incrementing and Decrementing Operators
These operators are used to increment/decrement a variable's value.
```
Operator	       Name	              Description
++$x	           Pre-increment	    Increments $x by one, then returns $x	
$x++	           Post-increment	    Returns $x, then increments $x by one	
--$x	           Pre-decrement	    Decrements $x by one, then returns $x	
$x--	           Post-decrement	    Returns $x, then decrements $x by one
```
```
<?php
  $x = 20;  
  echo ++$x;
  // Outputs 21
?> 
```
### Logical Operators
Logical operators are used to combine conditional statements.
```
Operator	Name	  Example	      Result
and	      And	    $x and $y	    True if both $x and $y are true	
or	      Or	    $x or $y	    True if either $x or $y is true	
xor	      Xor	    $x xor $y	    True if either $x or $y is true, but not both	
&&	      And	    $x && $y	    True if both $x and $y are true	
||	      Or	    $x || $y	    True if either $x or $y is true	
!	        Not	    !$x	          True if $x is not true
```
```
<?php
  $x = 150;  
  $y = 5;
  if ($x == 150 or $y == 80) {
    echo "Hello world!";
  }
  // Outputs 'Hello world!'
?>
```
### String Operators
Two operations that are designed for strings
```
Operator	Name	                      Example	            Result
.	        Concatenation	              $txt1 . $txt2	      Concatenation of $txt1 and $txt2	
.=	      Concatenation assignment	  $txt1 .= $txt2	    Appends $txt2 to $txt1
```
```
<?php
  $var1 = "Good";
  $var2 = " morning!";
  echo $var1 . $var2;
  // Outputs 'Good morning!'
?> 
```
### Array Operators
The array operators are used to compare arrays 
```
Operator	 Name	          Example	      Result
+	         Union	        $x + $y	      Union of $x and $y	
==	       Equality	      $x == $y	    Returns true if $x and $y have the same key/value pairs	
===	       Identity	      $x === $y	    Returns true if $x and $y have the same key/value pairs in the same order and of the same types	
!=	       Inequality	    $x != $y	    Returns true if $x is not equal to $y	
<>	       Inequality	    $x <> $y	    Returns true if $x is not equal to $y	
!==	       Non-identity	  $x !== $y	    Returns true if $x is not identical to $y
```
```
<?php
  $x = array("a" => "red", "b" => "green");  
  $y = array("c" => "blue", "d" => "yellow");  
  var_dump($x <> $y);
  // Outputs 'true'
?>  
```
### Spaceship Operator PHP 7
Also known as combined comparison operator, the spaceship operator is used for comparing two expressions. It provides a three-way comparison: 0 if equal, 1 if left is greater or -1 if right is greater.
```
Operator	<=> Equivalent
$x < $y	($x <=> $y) === -1
$x <= $y	($x <=> $y) === -1 || ($x <=> $y) === 0
$x == $y	($x <=> $y) === 0
$x != $y	($x <=> $y) !== 0
$x >= $y	($x <=> $y) === 1 || ($x <=> $y) === 0
$x > $y	($x <=> $y) === 1
```
```
<?php
  echo 10 <=> 10; // Outputs: 0
  echo 10 <=> 25; // Outputs: -1
  echo 25 <=> 10; // Outputs: 1
?>
```
## PHP If & Else & ElseIf
These are onditional statments that take in different conditions to perform different actions.<br/>
**if** statement - Executes a block of code if the condition is true 
```
<?php
  $a = 5;
  $b = 5;

  if ($a == $b) {
  echo "The numbers are equal";
  }
  // Outputs "The numbers are equal"
?>
```
**if..else** statement - Executes one block of code if the condition is true and a different block of code if the condition is false
```
<?php
  $mycash = 10;
  $yourcash = 100;

  if ($mycash > $yourcash) {
  echo "Looks like I have more money than you";
    } elseif ($mycash < $yourcash) {
    echo "Can you please lend me some cash?"
    }
    // Outputs "Can you please lend me some cash?"
?>
```
**if..elseif..else** statement - Executes multiple if..else statements 
```
<?php
  $opt1 = 10;
  $opt2 = 2;

  if ($val1 > $val2) {
  echo "Option 1 is bigger than option 2";
    } elseif ($val1 == $val2) {
    echo "Option 1 is equal to option 2";
      } else {
      echo "Option 1 is smaller than option 2";
      }
  // Outputs 'Option 1 is bigger than option 2'
?>
```
## PHP Functions
The real power of PHP comes from it's functions. Not only do functions reduce the repetition of code within a program, it makes it easier to elimiate errors and makes the code easier to read. There are more than 1,000 built-in PHP functions aside from the functions you can create yourself! 
```
function functionName() {
    code to be executed;
}
```
A few important things to note:
* A function name must start with a letter or underscore
* Functions are not case-sensitive
* A function will not execute automatically when the page loads and it needs to be 'called'
* Information can be passed to functions through arguments, which are like variables. The argument is mentioned inside parentheses after the function name `function user($fname, $lname){ ..`
* PHP automatically associates a data type to the varialble, this can be overridden using the `strict` declaration
* Use the `return` statment to let a function return a value
```
<?php  
  function sayHi($name,$age){  
  echo "Hello $name, you are $age years old<br/>";  
  }  

  sayHi("Kelly",27);  
  sayHi("Kayvan",24);  
  sayHi("Billy",99);  
  
   // Outputs "Hello Kelly, you are 27 years old  
               Hello Kayvan, you are 24 years old
               Hello Billy, you are 99 years old"
?> 
```

## PHP Arrays
An array can hold many different values values under a single variable. You can access any of the values by referring to an index number. In PHP, there are three different types of arrays: Indexed, Associative and Multidimensional.
### Indexed Arrays
The index can be assigned manually or automatically. Please note the index always starts at 0
```
<?php
  $fruits = array("apples", "grapes", "peaches"); 
  echo "I like " . $fruits[0] . ", " . $fruits[1] . " and " . $fruits[2] . ".";
  // Outputs "I like apples, grapes and peaches"
?>
```
### Associative Arrays
These are arrays that use named keys that you assign to them. Please note there are two ways to create an associative array:<br/>
`$yearBorn = array("Kelly"=>"1992", "Kayvan"=>"1995", "Billy"=>"1909");` OR <br/>
`$yearBorn['Kelly'] = "1992";
$yearBorn['Kayvan'] = "1995";
$yearBorn['Billy'] = "1990";`
```
<?php
  $yearBorn = array("Kelly"=>"1992", "Kayvan"=>"1995", "Billy"=>"1909");
  echo "Kelly was born in " . $yearBorn['Kelly'];
  // Outputs "Kelly was born in 1992"
?>
```
### Multidimensional Arrays
A mulidimensional array is an array that contains one or more arrays. It allows you to store values with more than one key.
```
<?php
$cars = array
  (
  array("Volvo",22,18),
  array("BMW",15,13),
  array("Saab",5,2),
  array("Land Rover",17,15)
  );
  
echo $cars[0][0].": In stock: ".$cars[0][1].", sold: ".$cars[0][2].".<br>";
echo $cars[1][0].": In stock: ".$cars[1][1].", sold: ".$cars[1][2].".<br>";
echo $cars[2][0].": In stock: ".$cars[2][1].", sold: ".$cars[2][2].".<br>";
echo $cars[3][0].": In stock: ".$cars[3][1].", sold: ".$cars[3][2].".<br>";
?>
```
There are a number of ways you can sort an array:
* sort() - sort array in ascending order
* rsort() - sort array in descending order
* asort() - sort associative arrays in ascending order, according to the value
* ksort() - sort associative arrays in ascending order, according to the key
* arsort() - sort associative arrays in descending order, according to the value
* krsort() - sort associative arrays in descending order, according to the key

## PHP Loops
Loops are used to execute the same block of code multiple times providing a certain condition is true. There are different types of loops:
**while** loop - Loops through a block of code as long as the condition is true
```
<?php
  $x = 5;

  while($x <= 10) {
    echo "The number is: $x <br>";
    $x++;
}
?>
```
**do..while** loop - Loops through a block of code once, then repeats as long as the condition remains true
```
<?php
  $x = 50;

  do {
    echo "The number is: $x <br>";
    $x++;
    } while ($x <= 60);
?>
```
**for** loop - Loops through a block of code a certain number of times. 
```
<?php  
  for ($x = 100; $x <= 120; $x++) {
  echo "The number is: $x <br>";
  }
?> 
```
**foreach** loop - This loop can only be used with arrays. It loops through each key/value pair in an array.
```
<?php
  $favFruit = array("Kelly"=>"peach", "Kayvan"=>"apple", "Billy"=>"banana");

  foreach($favFruit as $x => $val) {
  echo "$x = $val<br>";
  }
?>
```
