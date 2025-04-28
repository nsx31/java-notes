## 01 : Primitive Data Types
Everything is an object in Java except primitve data types. There are 8 types of primitve data types.

- **Integer**
    - byte  *(8 bits)*
    - short *(16 bits)*
    - int   *(32 bits) (default)*
    - long  *(64 bits)*
- **Floating Point Numbers**
    - float *(32 bits)*
    - double *(64 bits) (default)*
- **Characters**
    - char *(16 bits)*
- **Boolean**
    - boolean

> Unlike other programming languages, where the size of data types depends on the machine on which the program is running — for example, the size of an integer can be 32 bits on some machines and 64 bits on others — this is not the case with Java. Java has a fixed size for its primitive data types, irrespective of the platform it is running on.

**Q:** Since Java is an object-oriented programming language, and everything is considered an object, why did the developers decide to create primitive data types instead of making them objects? <br>
**A:** Making the primitve types into objects would have degraded performance too much.

### 1.1 : Integer
Java does not support unsigned, positive-only integers. It supports signed integers, i.e., both positive and negative values. By default, all integer literals are treated as `int`. If we want to define a `long`, we must explicitly tell the compiler by adding a capital or small `L` at the end of the integer value. Additionally, `byte` and `short` types are automatically promoted to `int` when the expression is evaluated.

```java
byte b = 12;
short s = 678;
int num = 12;
long id = 3563467L;
```

```java
byte a;
byte b = 12;
// error, because when b+5 expression is evaluated the result is int but not byte.
a = b + 5;  // error

short num1;
short num2 = 12;
// error, because when num2+5 expression is evaluated the result is int but not short.
num1 = num2 + 5;  // error
```

### 1.2 : Floating Point Types
If we want to define a `float`, we must explicitly tell the compiler by adding a capital or small `F` at the end of the double value.
```java
float temp = 34.6f;
double leastCount = 534.53422;
```

### 1.3 : Characters 
Character is defined using single quotes.
```java
char ch = 'a';
```

### 1.4 : Boolean
```java
boolean isAdmin = true;
```

## 02 : Type Conversion & Casting
Converting one data types into another is what we called type conversion. Type conversion can be automatic process or we have to do it forcefully. 