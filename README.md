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
