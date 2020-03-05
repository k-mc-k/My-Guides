## Object Oriented Programming

Object Oriented Programming (OOP) uses "objects" to represent data and methods. It provides a clear modular structure for large programs by allowing functions to be "chunked" together into a Class. It is easy to maintain, to modify, keeps the code organized while shrinking the size of your project.

There are 3 basic features of OOP that allow you to reuse your program or part of your program:

**Inheritance:** this is concerned with the relationship between classes. The relationship takes the form of a parent and child. The child uses the methods defined in the parent class. The main purpose of inheritance is re-usability– a number of children, can inherit from the same parent. This is very useful when we have to provide common functionality such as adding, updating and deleting data from the database.

**Polymorphism:** this is concerned with having a single form but many different implementation ways. The main purpose of polymorphism is simplify maintaining applications and making them more extendable.

**Encapsulation:** this is concerned with hiding the implementation details and only exposing the methods. The main purpose of encapsulation is to reduce software development complexity – by hiding the implementation details and only exposing the operations, using a class becomes easy.
Protect the internal state of an object – access to the class variables is via methods such as get and set, this makes the class flexible and easy to maintain.
The internal implementation of the class can be changed without worrying about breaking the code that uses the class.


### Object Oriented Programming in PHP

A Class is simply a way to store functions (aka methods) and properties (aka data) as PHP code in one or more related "chunks" where each individual "chunk" deals with a specific topic or piece of functionality. 

The Object Oriented concepts in PHP are:

**Class** − This is a programmer-defined data type, which includes local functions as well as local data. You can think of a class as a template for making many instances of the same kind (or class) of object.

**Object** − An individual instance of the data structure defined by a class. You define a class once and then make many objects that belong to it. Objects are also known as instance.

**Methods** - functions that are logically related to one another in some meaningful way. The words "method" and "function" are basically two different terms for the same thing.

**Properties** - Data values that are related to the class. These are values that are intentionally non-isolated to any individual function, because more than one of the functions in the class should have access to them.

**Inheritance** − When a class is defined by inheriting existing function of a parent class then it is called inheritance. Here child class will inherit all or few member functions and variables of a parent class.

**Polymorphism** − This is an object oriented concept where same function can be used for different purposes. For example function name will remain same but it make take different number of arguments and can do different task.

**Overloading** − a type of polymorphism in which some or all of operators have different implementations depending on the types of their arguments. Similarly functions can also be overloaded with different implementation.

**Data Abstraction**− Any representation of data in which the implementation details are hidden (abstracted). 

**Encapsulation** − refers to a concept where we encapsulate all the data and member functions together to form an object.

**Constructor** − refers to a special type of function which will be called automatically whenever there is an object formation from a class.

**Destructor** − refers to a special type of function which will be called automatically whenever an object is deleted or goes out of scope.


### OOP Exmaple
```
<?php

class Example
{
  private $vars = array();

  public function set($name, $value)
  {
    $this->vars[$name] = $value;
  }

  public function get($name)
  {
    return isset($this->vars[$name]) ? $this->vars[$name] : null;
  }
}

$example = new Example();
$example->set('foo', 'hello');
$value = $example->get('foo');

?>

```

### Procedural Exmaple
```
<?php

function example_new() {
  return array(
    'vars' => array()
  );
}

function example_set($example, $name, $value) {
  $example['vars'][$name] = $value;
  return $example;
}

function example_get($example, $name) {
  $value = isset($example['vars'][$name]) ? $example['vars'][$name] : null;
  return array($example, $value);
}

$example = example_new();
$example = example_set($example, 'foo', 'hello');
list($example, $value) = example_get($example, 'foo');

?>

```
