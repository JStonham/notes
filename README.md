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

Some classes can be defined as abstract classes. This means that the class is too broad for simple defining characteristics. The primary use of an abstract class is to define and show only the relevant details of the class/object it creates and hide the irrelevant details from future users.

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

# Polymorphism

Polymorphism is the capability of a method to do different things based on the object that it is acting upon. It decouples a method's contract (method signature) from its implementation. (It stipulates what should be done, but allows for different implementations or calculations).

If we think of the class Shape, it would be an abstract class as there are many shapes. We want to calculate the circumference of these shapes. The problem is that the circumference for different shapes is calculated in different ways. Rather than putting all of the different methods into the Shape class, we put a Constructor to say what we want, and force the problem of the method down into the sub classes.

A constructors looks like a method, but it cannot have a return type. It is used for setting up the inital state of an object. The name of a constructor is always the same as the name of the class. When writing the syntax for a class/object it is fields, then constructors, then methods.

``` java
public abstract class Shape {
    public abstract double circumference();
}
```

We then create our Shape sub classes of Circle, RightAngleTriangle and Rectangle, each with their own methods for calculating their circumference.

### Circle

``` java
public class Circle extends Shape {
    private double radius;

    public Circle(double radius) {
        if (radius >= 0) {
            this.radius = radius;
        } else {
            System.out.println("ERROR: Radius needs to be a non-negative value.");
        }
    }

    public double circumference() {
        return 2*radius*Math.PI;
    }
}
```

This method includes a check that the radius entered is a non-negative value i.e. 0 or positive.

### RightAngleTriangle

``` java
public class RightAngleTriangle extends Shape {
    private double height;
    private double width;

    public RightAngleTriangle(double height, double width) {
        this.height = height;
        this.width = width;
    }

    public double circumference() {
        return height + width + hypotenuse();
    }

    private double hypotenuse() {
        return Math.sqrt(height * height + width * width);
    }
}
```

### Rectangle

``` java
public class Rectangle extends Shape {
    private double height;
    private double width;

    public Rectangle(double height, double width) {
        this.height = height;
        this.width = width;
    }


    public double circumference() {
        return 2 * height + 2 * width;
    }
}
```

### Calling the method of Circumference

We can then call the method of circumference on the abstract class of Shape and its sub classes in the Main application.

``` java
public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle(5);
        Shape triangle = new RightAngleTriangle(3, 4);
        Shape rectangle = new Rectangle(3, 4);

        Shape[] shapes = {circle, triangle, rectangle};

        for (Shape shape : shapes) {
            System.out.println(shape.circumference());
        }
    }
}
```

The method circumference is called for all shapes in shape, and returns 3 values based on what height/width/radius has been selected and how the circumference of the individual shapes is calculated. 

# Interfaces

To change an abstract class to an interface remove 'abstract' from class and methods and change 'class' to 'interface'. Public can be removed from methods as all interface methods are implicitly public.

### Shape Interface

``` java
public interface Shape {
    double circumference();
}
```

### Rectangle implementation of Shape Interface

Sub classes become implementations so change 'extends' to 'implements'.

``` java
public class Rectangle implements Shape {
}
```

# Differences between Abstract Classes and Interfaces in Java

- Both Abstract Classes and Interfaces are used for varying degrees of abstraction (defining relevant/irrelevant details and showing/hiding them from users).
- Abstract Classes are used for partial abstraction whereas Interfaces are used for full abstraction.
- As Abstract Classes are used for partial abstraction, they can have both abstract and concrete methods. Since Interfaces are used for full abstraction, they can only have abstract methods.
- In an Abstract Class, the 'abstract' keyword is mandatory to declare a method as abstract. In an Interface, the 'abstract' keyword is optional as all Interface methods are abstract anyway.
- An Abstract Class can have public and private abstract methods whereas an Interface can only have public abstract methods.

Perhaps the biggest differences are:
1. An Abstract Class can extend only one class at a time whereas an Interface can extend multiple interfaces at the same time.
2. An Abstract Class can extend a concrete (regular) class or an abstract class, and it can also implement an interface. (It can only do 1 of these 3 things at once!). An interface can only extend another interface.

When we talk about abstract classes we are defining characteristics of an object type; specifying what an object is.

When we talk about an interface and define capabilities that we promise to provide, we are talking about establishing a contract about what the object can do.

For example, the following can all be animals: cat, dog, hippo, meerkat. However, only a cat or dog would lick people. In this case we could make Animal an abstract class where the animals can inherit certain characteristics, and LicksPeople as an interface, which the cat and the dog would implement.

# Git Bash

Git is a command line application adjacent to code. It excels as a Version Control System. There are some other systems you can use, but Git is the best. There are many Graphical User Interfaces (GUIs) for Git e.g. IntelliJ. Bash (Bourne Again SHell) is a program that facilitates the running of applications.

Git has directories and repositories. The directories are the structure of files and folders and the repositories track changes and form the basis of the version control system.

## Useful Git Commands

Some Git commands need a 'Git' in front of them as they are Git specific.

history  (shows the command line history)\
cd  (change directory)\
ls  (list contents of current directory)\
git status  (checking the state of a repository)\
git init  (creates an empty repository within the current directory)\
git add  (adds files where the names succeed the key word)\
git commit  (commits the files to the repository)\
\-m  (allows you to add a comment within "" to the commit)\
nano  (text editor)\
cat  (concatenates/combines - shows you the file)\
cp  (copy file)\
mv  (move and rename file or directory)\
/  (the highest directory you can navigate to)\
~  (the home directory)\
.  (the current directory)\
..  (the directory above the current one)\
\-  (the previous directory you navigated to)\
rm  (remove file - be VERY careful with this one!)

## Git Repositories

We create repositories in Git to initialise a version control system and allow many people to work on the same code.

To create a repository, 'cd' to the directory you want to create the repository in.\
Use 'ls' to see everything that the directory contains.\
Create the repository using 'git init'.\
Use 'git status' to check the status of the repository.\
Use 'git add' followed by the full file names, or '.' for everything, to prepare files for adding to the repository.\
Use 'git status' to check the status of the repository.\
Use 'git commit' to commit (add) the files to the repository. Use '-m' followed by text in "" to add comments to the commit.\
Comments are very good for explaining why you are doing things.\
Use 'git status' to check the status of the repository.\
If there are files you want to be ignored or you want to create a space for future files to ignore, type 'nano' followed by a file name to open the nano text editor and load a file. If no file is found nano will create one.\
Use 'git status' to check the status of the repository.\
Use 'git add' to prepare the to-be-ignored files for adding to the repository.\
Use 'git status' to check the status of the repository.\
Use 'git commit' to commit (add) the files to-be-ignored to the repository. Use '-m' followed by text in "" to add comments to the commit.\
Use 'git status' to check the status of the repository.\
When you are done, you should get the message 'working tree clean'.

## Updating GitHub through Git Bash and Intellij

- change directory into the directory you want to update.
- If you don't have the directory already, clone it to your computer using 'git clone' followed by the full directory link (found using 'clone or download' on GitHub).
- Make sure you are working from the latest version by using 'git pull'.
- update the file using a text editor.
- prepare the changes using 'git add' followed by file name or '.'.
- commit the changes using 'git commit' and add a message using -m "[message text here]".
- push the changes to the orignal branch using 'git push'.
- add reviewer on GitHub.

# budjen

# Design
 ## User Journey
 1. User initialises application.
1. User is automatically taken to the main menu.
1. User can select summary of transactions or to enter a new transaction.
1. From summary of transactions or enter a new transaction, user can select the other option or go to the main menu.
1. User logs out.

## Simplify User Journey
To simplify the user journey, break down the conditions into their simplest form (no fluff!).
1. User runs application.
1. Application prints report.

 ## Requirements
1. The application should show the user how much money they have saved every month and for the year.
1. The application should show the user what they are spending their money on.
1. The application should deal with money in pounds sterling.
1. The application should deal with time using the absolute calendar month and year.
1. The application should use the English language for input and output.
1. The application should be built in the Java 8 programming language.
1. The user will be the person who invokes the application.
1. A purse is a representation of a number of money in pounds sterling.
1. How much money is made per month will be represented in terms of a credit to the purse.
1. How much money is spent per month will be represented in terms of an expenditure from the purse.
1. How much money is saved per month will be represented in terms of the difference between the credit and the expenditure.
1. How much money is saved per year will be a cumulative count of the difference between the credit and the expenditure in a calendar year.
1. The user will interact with the application and enter particular details for each transaction.
1. Each transaction will include a transaction type, a transaction description and a number of money in pounds sterling.
1. The transaction type will be in the form of a credit or an expenditure.
1. The transaction description will be formed of a list of credit and expenditure options.
1. All money entered by the user into the purse will be in non-negative values.
1. The application will display credit and expenditure in non-negative values.

## A Plain Old Java Object (pojo) called Transaction

Create a class called Transaction with private fields of different types and set-ers and get-ers.

``` java
public class Transaction {
    private String type;
    private String description;
    private long money;
     public void setType(String type) {
        this.type = type;
    }
     public void setDescription(String description) {
        this.description = description;
    }
     public void setMoney(long money) {
        this.money = money;
    }
     public String getType() {
        return type;
    }
     public String getDescription() {
        return description;
    }
     public long getMoney() {
        return money;
    }
}
```

## Creating a Simple Successful Test


The beginning of test driven development (tdd). Tests must be:
- public
- void
- have no input arguments
- begin with '@Test'

There should be at least two classes. A main class and a test class.

```java
public class Bank {
    private long balance;
     public long add(Transaction transaction) {
        balance = balance + transaction.getMoney();
        balance += transaction.getMoney();
        return balance;
    }
}
```

Since the updated balance will be the balance plus the result of the transaction, we can simplify the code in line 4 to be the '+=' in line 5 and get rid of line 4.

``` java
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class BankTest {
    Bank bank = new Bank();
     @Test
    public void testZero() {
        Transaction transaction = makeTransaction(0);
        assertEquals(0, bank.add(transaction));
    }
     @Test
    public void test() {
    public void testFive() {
        long balance = bank.add(makeTransaction(5));
        assertEquals(5, balance);
    }
```

    3 in 1 positive and negative test:
    Look closely at what is expected in the assertEquals
    after each new transaction is made.

``` java
    @Test
    public void testTransaction() {
        Transaction transaction1 = makeTransaction(10);
        assertEquals(10, bank.add(transaction1));
        Transaction transaction2 = makeTransaction(-8);
        assertEquals(2, bank.add(transaction2));
        Transaction transaction3 = makeTransaction(4);
        assertEquals(6, bank.add(transaction3));
    }
     private Transaction makeTransaction(long money) {
        Transaction transaction = new Transaction();
        transaction.setMoney(money);
        return transaction;
    }
 }
```

## Transactions

Looking back at the requirements for budjen:
"Each transaction will include a transaction type,
a transation reason and a number of money in pounds sterling."

``` java
public class Transaction {
    private String type;
    private String description;
    private long money;
     public void setType(String type) {
        this.type = type;
    }
     public void setDescription(String description) {
        this.description = description;
    }
     public void setMoney(long money) {
        this.money = money;
    }
     public String getType() {
        return type;
    }
     public String getDescription() {
        return description;
    }
     public long getMoney() {
        return money;
    }
}
```

## Test Driven Development (tdd)

tdd rules:
1. RED. Write as little test code as possible to make your production code fail.
1. GREEN. Write as little production code as possible to make your test pass.
1. REFACTOR. Clean up the code. (Not allowed to change the behaviour of the production code).

The classes Bank and BankTest now become:

``` java
public class Bank {
    private long balance = 0;
     public long getBalance() {
        return balance;
    }
     public void addTransaction(Transaction transaction) {
        balance += transaction.getMoney();
    }
}

public class BankTest {
    public static final long BIG_NUMBER = 64000000000l;
    private Bank bank = new Bank();

     @Test
     public void hasZeroBalanceByDefault() {
        assertEquals(0, bank.getBalance());
    }
     @Test
     public void canHandleMultipleTransactions() {
        bank.addTransaction(makeTransaction(128));
        bank.addTransaction(makeTransaction(-256));
        bank.addTransaction(makeTransaction(64));
        assertEquals(-64, bank.getBalance());
    }
     @Test
     public void canHandleVeryLargeAmountsOfMoney() {
        bank.addTransaction(makeTransaction(BIG_NUMBER));
        assertEquals(BIG_NUMBER, bank.getBalance());
    }
     private Transaction makeTransaction(long money) {
        Transaction transaction = new Transaction();
        transaction.setMoney(money);
        return transaction;
    }
}
```

The class Transaction needs a TransactionTest class:

```java
import org.junit.Test;
import static org.junit.Assert.*;
public class TransactionTest {
     @Test
    public void givenNoData_returnsNoDataMessage() {
        String summary = new Transaction().getSummary();
        assertEquals("No data.", summary);
    }
     @Test
    public void givenMoney_returnsMonetaryDescription() {
        String summary = makeTransaction().getSummary();
        assertEquals("You have £10", summary);
    }
    @Test
    public void givenPositiveMoney_returnsMonetaryValue() {
        long money = makeTransaction().getMoney();
        assertEquals(10, money);
    }
     private Transaction makeTransaction() {
        Transaction transaction = new Transaction();
        transaction.setMoney(10);
        return transaction;
    }
}
```

To make 2 of these tests pass, we need to add a method to the Transaction class:

``` java
    public String getSummary() {
        if (money == 0) {
            return "No data.";
        }
        return "You have £10";
    }
```

So that was positive money, but how about negative money?

``` java
    @Test
    public void givenNegativeMoney_returnsNegativeMonetaryValue() {
        long money = makeNegativeTransaction().getMoney();
        assertEquals(-20, money);
    }
     @Test
    public void givenNegativeMoney_returnsMonetaryDescription() {
        String summary = makeNegativeTransaction().getSummary();
        assertEquals("You have spent £20", summary);
    }
     private Transaction makeNegativeTransaction() {
        Transaction transaction = new Transaction();
        transaction.setMoney(-20);
        return transaction;
    }
```

Which means we need to add lines 5-7 of the following to Transaction:

``` java
    public String getSummary() {
        if (money == 0) {
            return "No data.";
        }
        if (money <0) {
            return "You have spent £20";
        }
        return "You have £10";
    }
```

The amount of money I have spent or I have can be refactored:

``` java
    public String getSummary() {
         if (money == 0) {
            return "No data.";
        }
        if (money <0) {
            return "You have spent £" + (money * -1);
        }
        return "You have £" + money;
    }
```

Now, what about zero money?

``` java
    @Test
    public void givenZeroMoney_returnsZeroMonetaryValue() {
        long money = new Transaction().getMoney();
        assertEquals(0, money);
    }
     @Test
    public void givenZeroMoney_returnsMonetaryDescription() {
        String summary = new Transaction().getSummary();
        assertEquals("No data.", summary);
    }
```

Tests and method for Transaction description:

``` java
    @Test
    public void givenDescription_returnsDescription() {
        String description = makeDescription().getDescription();
        assertEquals("Rent",description);
    }
    @Test
    public void givenNullDescription_returnsNullDescription() {
        String description = new Transaction().getDescription();
        assertNull(description);
    }
    @Test
    public void givenEmptyDescription_returnsDescription() {
        String description = makeEmptyDescription().getDescription();
        assertEquals("",description);
    }
     private Transaction makeDescription() {
        Transaction transaction = new Transaction();
        transaction.setDescription("Rent");
        return transaction;
    }
    private Transaction makeEmptyDescription() {
        Transaction transaction = new Transaction();
        transaction.setDescription("");
        return transaction;
    }
```

The 3rd test above is a dangerous test. Essentially it is allowing an empty description to be set (which we don't want to allow).

Tests on Transaction Date:

``` java
import java.util.Date;
    @Test
    public void givenDate_returnDate() {
        Date date = new Date();
        Transaction transaction  = new Transaction();
        transaction.setDate(date);
        assertEquals(date, transaction.getDate());
    }
     @Test
    public void givenNullDate_returnDateToday() {
        Date today = new Date();
        Transaction transaction = new Transaction();
        transaction.setDate(null);
        assertEquals(today, transaction.getDate());
    }
```

And of course we need to modify the Transaction class to make these tests pass by adding a date field and set-ers and get-ers:

``` java
import java.util.Date;
private Date date;
public void setDate(Date date) {
        this.date = date;
    }
public Date getDate() {
        return date;
    }
```

We can change this code so that if the date is null the date returned will be today...

``` java
public Date getDate() {
        if (date == null) {
            return new Date();
        }
            return date;
    }
```

The problem with this code is that if the transaction date is null, by the time we get the date it might be slightly different to the date that was set (e.g. 1 second out). This means we need to set the date in the setDate method rather than the getDate method:

``` java
public void setDate(Date date) {
        this.date = date;
        if (date == null) {
            this.date = new Date();
        }
        else {
            this.date = date;
        }
    }
public Date getDate() {
        return date;
    }
```

## TDD with a new money format

So far we have been thinking about money in terms of whole pounds... but what do we need to do if we want to think about money in terms of pence?

We can modify our existing Transaction Tests to include pence:

``` java
@Test
    public void givenMoney_returnsMonetaryDescription() {
        String summary = makeTransaction().getSummary();
        assertEquals("You have £10", summary);
        assertEquals("Your account has been credited with £10.00", summary);
    }
     @Test
    public void givenPositiveMoney_returnsMonetaryValue() {
        long money = makeTransaction().getMoney();
        assertEquals(10, money);
        assertEquals(1000, money);
    }
     private Transaction makeTransaction() {
        Transaction transaction = new Transaction();
        transaction.setMoney(10);
        transaction.setMoney(1000);
        return transaction;
    }
     @Test
    public void givenNegativeMoney_returnsNegativeMonetaryValue() {
        long money = makeNegativeTransaction().getMoney();
        assertEquals(-20, money);
        assertEquals(-2000 , money);
    }
     @Test
    public void givenNegativeMoney_returnsMonetaryDescription() {
        String summary = makeNegativeTransaction().getSummary();
        assertEquals("You have spent £20", summary);
        assertEquals("You have spent £20.00", summary);
    }
     private Transaction makeNegativeTransaction() {
        Transaction transaction = new Transaction();
        transaction.setMoney(-20);
        transaction.setMoney(-2000);
        return transaction;
    }
     @Test
    public void givenNegativeMoney_returnsMonetaryDescription2() {
        String summary = makeNegativeTransaction2().getSummary();
        assertEquals("You have spent £20.01", summary);
    }
     private Transaction makeNegativeTransaction2() {
        Transaction transaction = new Transaction();
        transaction.setMoney(-2001);
        return transaction;
    }
```

Simply adding pence as 00 is fine when we are still working in whole pounds, but to get the actual pence (the remainder of a whole pound) we need to do:
- a % b = c

A big number divided by another number will give a number of whole values and a remainder. It is the remainder we are interested in.

For example, in 15 % 10 = 5, 10 goes into 15 once, with 5 as the remainder.

Some other examples:
- 25 % 10 = 5
- 13 % 6 = 1
- 64 % 255 = 64
- 146 % 12 = 2

We can create a class called Currency to give us the pence:

``` java
public class Currency {
    public String formatPounds(long i) {
        if (i == 0) {
            return "0";
        }
        long remainder = i % 100;
        String pence = remainder < 10 ? "0" + remainder : "" + remainder;
        return "£" + (i / 100) + "." + pence;
    }
}
```

The code 'remainder < 10 ? "0" + remainder : "" + remainder' works as an if-else statement. i.e. If the remainder is less than 10, then 0 + remainder, else "" + remainder.

With the Currency class, we need a Currency Test class:

``` java
import org.junit.Test;
import static org.junit.Assert.assertEquals;
public class CurrencyTest {
     @Test
    public void givenZero_givesZero() {
        runTest("0", 0);
    }
     @Test
    public void given5Pounds_gives5Pounds() {
        runTest("£5.00", 500);
    }
     @Test
    public void given42Pence_gives42Pence() {
        runTest("£0.42", 42);
    }
     private void runTest(String s, int i) {
        assertEquals(s, new Currency().formatPounds(i));
    }
 }
```

We can also modify the getSummary method in the Transaction class to tell us exactly how much money was involved in the transaction.

``` java
public String getSummary() {
         if (money == 0) {
            return "No data.";
        }
        if (money <0) {
            return "You have spent " + new Currency().formatPounds(-money);
        }
        return "Your account has been credited with " + new Currency().formatPounds(money);
    }
```

Always remember to REFACTOR!! There could be unused imports or multiple assertions that could be put into the same Test.

This code

``` java
private Date date;

public void setDate(Date date) {
        if (date == null) {
            this.date = new Date();
        }
        else {
            this.date = date;
        }
}
```

could be changed to

``` java
private Date date = new Date();

public void setDate(Date date) {
        if (date != null) {
            this.date = date;
        }
        else {
            this.date = date;
        }
}
```

## Exceptions

An exception is a disruption to the execution of a programme. There are a few reasons why an exception can occur, including:
- Data requested is out of range (e.g. Data held is 1-5 and I ask for record 8).
- File cannot be found.
- Network connection was interrupted.

There are two types of exceptions:
1. Checked Exceptions
1. Unchecked Exceptions

Checked exceptions have to be handled when a programme is executed. The programmer is forced to build in a way of handling these exceptions.

Unchecked exceptions do not have to be handled when a programme is executed. It is up to the programmer to handle them.

Java documents states: "If a client can reasonably be expected to recover from an exception, make it a checked exception. If a client cannot do anything to recover from the exception, make it an unchecked exception".

In Java, the Exception class is checked, but the RuntimeException class is unchecked.

Exceptions should be handled to enable the safe execution of a programme. Ideally exceptions need to be handled as closely as possible to make the execution more performant.

The way we handle exceptions is using the try/catch syntax.

We 'try' the method that will throw an exception and we 'catch' the result of that exception.

By catching the exception we allow the programme to be executed, although instead of the expected response the user will be shown an error message.

``` java
import org.junit.Test;
 public class ExceptionPracticeTest {
     @Test
    public void exceptionTest() {
        a();
    }
     private void a() {
        b();
    }
     private void b() {
        c();
    }
     private void c() {
        d();
    }
     private void d() {
        e();
    }
     private void e() {
        try {
            f();
        } catch (JenException re) {
            String bob = re.getBob();
            System.out.println(bob.equals("agergaerg"));
        }
    }
     private void f() {
        g();
    }
     private void g() {
        h();
    }
     private void h() throws JenException {
        throw new JenException("Doesn't matter");
    }
}
 class JenException extends RuntimeException {
    private String bob;
     JenException(String message) {
        super(message);
    }
     public String getBob() {
        return bob;
    }
}
```

## Creating an Alias

To create an alias, we need to create and modify a file that will contain our alias.

- Open text editor for file containg alias: nano ./.bashrc
- Edit file: alias shortcut = "full command"
- Write Out, Enter and Exit text editor.
- Enable use of shortcut straight away: source ./.bashrc
