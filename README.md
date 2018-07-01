# Notes
Notes for learning programming.

# Markdown

## Slightly smaller header

Used two hashes for slightly smaller header.


###### tiny header


## Code

```
select
*
from
*
```

Three backticks for a code block followed by code and then three more backticks.


```sql
select
*
from
*
```

Same as above, but with 'sql' straight after the first three backticks.

# Hello Dog

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("hello dog!");
    }
}
```

This is the syntax needed to create a very simple java application.

# Conditionals

```java
public class Main {
    public static void main(String[] args) {
        String name = "Jen";
        if (name.equals("Jen")){
            System.out.println("hello dogs!");
        } else {
            System.out.println("hello world!");
        }
    }
}
```
The simple syntax for creating java applications has been modified to add a conditional. A variable (condition) in the form of a String has been given the name Jen and, if the condition is met, hello dogs will be printed, if not, hello world will be printed.

# Java Data Types

Java has some different data types to SQL. Here are some similarities and differences:

## SQL
float, date, datetime, int, bigint, varchar, null.

## Java
float, Date, DateTime, int, long, String, null.

Java also has some additional data types that SQL doesn't have:

double (higher precision float, use for all decimals), byte, boolean (true or false).

# Variables

To write the following sentence in Java, variables need to be defined: "My name is Jen and I have 0 dogs. I walked 2.4 miles today. Flat earth theory is false."

```java
public class Main {
    public static void main(String[] args) {
        String name = "Jen";
        int dogsCount = 0;
        double milesWalked = 2.4;
        boolean earthTheory = false;
        String greeting = "My name is "+name+" and I have "+dogsCount+" dogs. I walked "+milesWalked+" miles today. Flat earth theory is "+earthTheory+".";
        System.out.println(greeting);
    }
}
```

There are 4 data types used in the above sentence: String, int, double and boolean.

String is used for "Jen" and most of the other words in the sentence, int is used for 0, double is used for 2.4 and boolean is used for false.

The variables need a data type, then a name and then a condition.

The String used for most of the sentence needs the format " "+String+" "+int+" "+double+" "+boolean+"." as the words need spaces between them and the sentence needs a fullstop after the boolean condition.

# Nested Ifs

Introducing...
||  or
&&  and
!  not

Don't use !! as this has the same effect as a double negative turning the value back to positive.

Both of the below if, else if and else statements have the same outcome, but the first statement uses and/or to remove the need for the second else if.

The statements have the following outcomes: If String name is Jen/Roger and if likesDogs is true then 'hello dogs and Jen/Roger' will be returned, if String name is not Jen/Roger and if likesDogs is true then 'hello dogs' will be returned, and if likesDogs is false then 'hello '+ String name value will be returned (even if String name is Jen/Roger).

``` java
public class Main {
    public static void main(String[] args) {
        String name = "Walter";
        boolean likesDogs = true;
        if (likesDogs &&(name.equals("Jen") || name.equals("Roger"))) {
            System.out.println("hello dogs and "+ name +"!");
        } else if (likesDogs) {
            System.out.println("hello dogs!");
        } else {
            System.out.println("hello "+ name +"!");
        }

        if (likesDogs && name.equals("Jen")) {
            System.out.println("hello dogs and Jen!");
        } else if (likesDogs && name.equals("Roger")){
            System.out.println("hello dogs and Roger!");
        } else if(!(!likesDogs)) {
            System.out.println("hello dogs!");
        } else {
            System.out.println("hello "+ name + "!");
        }
    }
}
```

# Classes and Objects

Classes are moulds for objects. They define fields and methods that objects possess. The class itself doesn't have the fields or possibility of using these methods.

Example: Object is a dog called Bertie. It has fields including collar, colour and microchipped. It has methods including bark and fetch ball.

To define the method of an object we need: a return type, a name (written in an imperative style), input argument(s) and a bracket body.

## Defining an Object

The Object below has fields (collar, colour and microchipped) and a method (bark).

``` java
public class Dog {
    String collar;
    String colour;
    boolean microchipped;

    String bark (double volume) {
        if (volume <= 5) {
            return "ruff";
        }
        return "woof";
    }

}
```

## Using an instance of an Object

The statement below will return 'Bertie says woof' as the first condition 'Bertie says ruff' was not met.

``` java
public class Main {
    public static void main(String[] args) {
        Dog bertie = new Dog();
        String bertieSays = bertie.bark(6);
        System.out.println("Bertie says " + bertieSays);
    }
}
```

# Enumeration (enum)

A finite list of possible values. Similar to objects in that it can have fields and methods. It's not possible to use the syntax 'new' with enum. For each possible enum value, what Java does under the hood is assign a number (called an 'ordinal') to each. Java really only knows about this number, but the programmer may use an easy-to-read name instead.

For example:

``` java
public enum FlingableObject {
    BALL,
    STICK,
    FRISBEE,
    TOY,
    HOT_DOG
}
```

# Case Statements within a Method

A list of cases, which in this case is within a method and returns a value for each enum option. Make sure to include a default return value at the end!

``` java
String fetch(FlingableObject flingableObject) {
        switch (flingableObject) {
            case TOY: return "That's not your toy, give it back!";
            case BALL: return "Good boy!";
            case STICK: return "Have a treat!";
            case FRISBEE: return "That's not what I threw!";
            default: return "I don't know what this is!";
        }
    }
```

# Using an enum

The statement below defines a method for playing fetch with scout. I throw a flingable object (in this case a ball), Scout fetches the ball, I say "Good Boy!"

``` java
public class Application {
    void run() {
    System.out.println("Jen throws "+ FlingableObject.BALL);
        String response = scout.fetch(FlingableObject.BALL);
        System.out.println("Jen says \"" + response + "\"");
        }
  }
```

# Using a For Loop

The For Loop below effectively says: For all dogs, create a variable dog of type Dog, call the method (bark) and return what the dogs will say.

In the following example: The dogs are created one at a time (line by line) using a line from the 1st paragraph and the whole last paragraph. Once the 3 dogs have been created they are put into an array (2nd paragraph). The 3rd paragraph uses a for loop to say for all the dogs in the array (one at a time in the specified order), call the method (bark) and return what each dog will say.

``` java
public class Application {
    void run() {
        Dog pia = makeDog("Pia", 4);
        Dog bertie = makeDog("Bertie", 2);
        Dog scout = makeDog("Scout", 62);

        Dog[] dogs = new Dog[]{bertie, pia, scout};

        for (Dog dog : dogs) { 
            String dogsSay = dog.bark(5000);
            System.out.println(dog.name + " says " + dogsSay);
        }
       
    }

    Dog makeDog(String dogName, int dogAge) {
        Dog dog = new Dog();
        dog.name = dogName;
        dog.age = dogAge;
        return dog;
    }

}
```

# Encapsulation

Encapsulation in Java allows you to hide certain fields from other classes. These fields can only be accessed through defined set and get methods.

There are four levels of class protection: public, protected, package-private (the default) and private. For all except package-private the keyword must be used at the start. For package-private there is no keyword. For now just use public and private.

In the following example, the public class Animal has private fields of age and limbsCount, which can only be called by using the defined set methods (setLimbsCount and setAge) and the get methods (getLimbsCount and getAge).

``` java
public class Animal {
    private int age;
    private int limbsCount;

    public int getLimbsCount() {
        return limbsCount;
    }

    public void setLimbsCount(int limbsCount) {
        this.limbsCount = limbsCount;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age >= 0) {
            this.age = age;
        }
    }
}
```

When using the set method, remember to include void after public to let Java know you don't want to return any values. Also, to allow you to use the same word multiple times, write 'this.' before the field name to let Java know which word in the method links to the field.

When using the get method, remember to list the data type after public, and tell Java what to return.

Note - the 'get' keyword is fine for get methods involving all data types except boolean. For boolean, instead of 'get' use 'is'.

# Inheritance

Classes can inherit fields and methods from another, super, class. In the case of Animal there can be many animals so Animal is a super class. The sub classes for Animal could be Dog, Cat and Rabbit. As these might all have similar features that other animals may not have, they can be included in a super class Pet, which would be a sub class of Animal.

In order to show that one class is a sub class of another, you should use the following syntax after public/private class: "sub class name" + extends + "super class name".

The following sub class Pet inherits age and limbsCount from its super class Animal, and also has a field called name.

``` java
public class Pet extends Animal {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

The following class Rabbit is a sub class of Pet. It inherits name from Pet, and age and limbsCount from Pet's super class Animal.

Rabbit also has a field of fluffDegree, which Pet and Animal do not have.

``` java
public class Rabbit extends Pet {
    private String fluffDegree;

    public String getFluffDegree() {
        return fluffDegree;
    }

    public void setFluffDegree(String fluffDegree) {
        this.fluffDegree = fluffDegree;
    }
}
```

# Using Set-ers and Get-ers

The following code will make a new cat and a new rabbit with defined name, age, limbsCount and fluffDegree for the Rabbit only (The Cat class doesn't include or inherit this field).

We could use the Animal class to get the age and limbsCount of the Cat and Rabbit, but to get the name for both as well we need to use the Pet class.

``` java
public class Application {

    void run() {
        Pet tom = makeCat();
        Pet bugs = makeRabbit();

        Pet[] pets = {tom, bugs};

        for (Pet pet : pets) {
            System.out.println(pet.getAge());
            System.out.println(pet.getLimbsCount());
            System.out.println(pet.getName());
        }
    }

    private Rabbit makeRabbit() {
        Rabbit rabbit = new Rabbit();
        rabbit.setName("Bugs");
        rabbit.setAge(6);
        rabbit.setLimbsCount(3);
        rabbit.setFluffDegree("quite fluffy");
        return rabbit;
    }


    private Cat makeCat() {
        Cat cat = new Cat();
        cat.setName("Tom");
        cat.setAge(5);
        cat.setLimbsCount(4);
        return cat;
    }
}
```

# Abstract Classes

Some classes can be defined as abstract classes. This means that the class is too broad for simple defining characteristics.

Of the following classes: Animal, Pet, Dog, Cat and Rabbit, Animal and Pet should be considered abstract as there are many animals and many animals can be pets.

In order to define a class as abstract simply use the abstract keyword before defining the class.

``` java
public abstract class Animal {
}
```

``` java
public abstract class Pet extends Animal {
}
```

# Useful Windows Keyboard Shortcuts

Alt + Enter will help you out with almost anything!
To create a main method signature use shortcut 'psvm'.
If you need to rename a class or a method - Refactor, Rename (Shift + F6).
Ctrl + Alt + l sorts out dodgy formatting e.g. lots of random spaces.
