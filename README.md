# Abstract-Polymorphism
To describe the difference between Abstraction and Polymorphism

### **Abstraction :**

the concept of OOP that shows only essential attributes and "hides" unnecessary information.
when we want to commit the programmer to write a certain class method, but we are only sure about the name of the method, and not the details of how it should be written

```php
<?php
abstract class Car {
  public $name;
  public function __construct($name) {
    $this->name = $name;
  }
  abstract public function intro() : string;
}

class Audi extends Car {
  public function intro() : string {
    return "Choose German quality! I'm an $this->name!";
  }
}

class Volvo extends Car {
  public function intro() : string {
    return "Proud to be Swedish! I'm a $this->name!";
  }
}

class Citroen extends Car {
  public function intro() : string {
    return "French extravagance! I'm a $this->name!";
  }
}

$audi = new audi("Audi");
echo $audi->intro();
echo "<br>";

$volvo = new volvo("Volvo");
echo $volvo->intro();
echo "<br>";

$citroen = new citroen("Citroen");
echo $citroen->intro();
?>
```



### **Polymorphism :**

Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.
This example is shown the implementation of polymorphism using abstract class , note that we can implement it using interface ..
```php
<?php

abstract class Person
{
	abstract public function greet();
}

class English extends Person
{
	public function greet()
	{
		return 'Hello!';
	}
}

class Arabic extends Person
{
	public function greet()
	{
		return 'مرحبا!';
	}
}

class French extends Person
{
	public function greet()
	{
		return 'Bonjour!';
	}
}


function greeting($people)
{
	foreach ($people as $person) {
		echo $person->greet() . '<br>';
	}
}

$people = [
	new English(),
	new Arabic(),
	new French()
];

greeting($people);
```

In the below program, we have declared an abstract class,Language, and this abstract class contains an abstract method or abstract function called greet( ).
We have used the property to inherit the properties from the parent class to three English, Arabic and French classes,and each child class will return a different output.
Later we have declared a function greeting ( ) that will accept input as an array and will automatically call the greet function.
further to retrieve the output, we have declared an array of objects of all the child classes English, Arabic and French ( to call a class or to retrieve an output from a class we have to create an object of that particular class) and 
passed the object to out greeting function as the perimeter.

###**To sum up :**
**Abstraction** is conceptual,while **Polymorphism** is behavioral

