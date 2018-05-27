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

## SQL          ## Java
float           float
date            Date
datetime        DateTime
int             int
bigint          long
varchar         String
null            null

Java also has some additional data types that SQL doesn't have:

double float (use for all decimals)
byte
boolean (true or false)

