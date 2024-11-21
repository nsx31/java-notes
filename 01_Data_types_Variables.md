## Datatypes :

Java has two type of data tpes : 

*   primitive data types
*   reference data types

Primitive data types are built in while Reference data types are user defined. Primitve data types actually store the assigned value while refrerence data types store the memory address of the assigned value.

Example of primitve data types are :

1. integer : 
    - int
    - long
    - short
    - byte

2. floating point number : 
    - float
    - double
3. boolean
4. character

## Variables : 
**Identifier** : name given to the variable is known as the identifier.<br>
**Literal** : value assigned to a variable is known as literals.

```java
// Integer type
int num = 12;
long num1 = 2121212L;   // long should end with "L"
short num2 = 574;
byte num3 = 45;

// Floating point number
double num = 812.49;
float num1 = 98.18f;    // float should end with "f"

// character type
char option = 'a';  // char are placed inside the single quote

// boolean
boolean isSelected  = true;
```

before using variable we have to first initialise them i.e assign a default value otherwise java will throw an error.
```java
int luckyNum;   // this is called variable declaration

int luckyNum = 18;  // this is called varaible initialization
```

## Type casting : 
It is fairly common to assign a value of one type to a variable of another type. If the two types are compatible, then Java will perform the conversion automatically.
```java
int x = 69;

// type casting int into float
float pos = (int)x;  //output : 69.0
```

