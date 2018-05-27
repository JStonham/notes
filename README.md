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

double float (use for all decimals), byte, boolean (true or false).

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

There are 4 data types used in the above sentence. String, int, double and boolean.

String is used for "Jen" and most of the other words in the sentence
int is used for 0
double is used for 2.4
boolean is used for false

The variables need a data type, then a name and then a condition.

The String used for most of the sentence needs the format " "+" "+" "+" "+"." as the words need spaces between them and the sentence needs a fullstop after the boolean condition.

