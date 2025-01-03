## 01  Java class : 
- Using java class we can define our own data types.
- Classes are used to create object.
- A class contains properties and methods which are also known as class members. 

## 02 Class syntax, properties & methods : 
```java
class Student() {
    // class properties also known as instance variables
    String name;
    int age;
    int rollno;
    double percentage;

    // class methods
    void getStudentInfo(){
        System.out.println(this.name);
        System.out.println(this.age);
        System.out.println(this.rollno);
        System.out.println(this.percentage);
    }
}
```

## 03 Object creation :
The class we created above is just a blueprint for an object, defining what properties and methods the object will have. However, it does not actually create any object.

To create an object, we use the following syntax:
```java
Student bruno = new Student();
```

We use spread also known as dot operator to access object properties and methods : 
```java
bruno.name;  // this will return the name
bruno.age;   // this will return the age
```

## 04 Constructor :
To initialize all variables of class when an instance is created in that case we need constructor method.
```java
class Student() {
    String name;
    int age;
    int rollno;
    double percentage;

    // constructor
    Student(String name, int age, int rollno, double percentage){
        this.name = name;
        this.age = age;
        this.rollno = rollno;
        this.percenntage = percentage;
    }

    void getStudentInfo(){
        System.out.println(this.name);
        System.out.println(this.age);
        System.out.println(this.rollno);
        System.out.println(this.percentage);
    }
}
```

```java
// initializing class variables during instance creation
Student bruno = new Student("bruno mars", 27, 69, 89.12);
```
Earlier we have to manually initialize all class variables which can be very tedious and inefficient now its super easy and quick. 

## 05 Constructor overloading : 
- Defining two or more methods with same name inside the same class is called method overloading.
- Java use type and number of arguments as its guide to determine which version of the overloaded method to actually call.
```java
class Student() {
    String name;
    int age;
    int rollno;
    double percentage;

    // constructor
    Student(String name, int age, int rollno, double percentage){
        this.name = name;
        this.age = age;
        this.rollno = rollno;
        this.percenntage = percentage;
    }

    // constructor
    Student (){
        this.name = "john doe";
        this.age = 44;
        this.rollno = 39;
        this.percentage = 93;
    }

    void getStudentInfo(){
        System.out.println(this.name);
        System.out.println(this.age);
        System.out.println(this.rollno);
        System.out.println(this.percentage);
    }
}
```


```java
Student bruno = new Student("bruno mars", 27, 69, 89.12);
Student user = new Student();

bruno.name;  // bruno mars
user.name;  // john doe
```

## 06 Passing object as method parameter : 
```java
class Student () {
    String name;
}

// passing object as method parameter
void setStudentName(Student obj){
    obj.name = "tommy";
}

// object
Student std = new Student();

// passing object as method argument
setStudentName(std);
```

## 07 Access control : 
- Java has three access modifiers : 
    - Public
    - Private
    - Protected
- When class members are modified by **public**, then those members can be accessed by anyone.
- When class members are modified by **private**, then members can be accessed by other members of same class.
- When no access modifier is used then class members are by default set to **public** but those members are public within its own package.

```java
class Student() {
    public String name;
    private int age;
    private int rollno;
    double percentage;
}
```

- Static : when we want a class member to run independently i.e without creation of instance first in that case we modify that member with **static**.
    - method, class, variable, block can be set to static.
    - variables declared as static act as global variables.
    - we cannot use non-static method inside a static method.

```java
class Example {
    // static variable
    static int global = 13;

    // static block
    /*
    You might be wondering why we need a static block. To answer that, if we have some code 
    that needs to execute when the class is loaded into memory, we use a static block.
    */
    static {
        System.out.println("Static block executed.");  
    }

    // static method
    static void display() {  
        System.out.println("This is a static method.");  
    }  
}
```

## 08 Inheritance : 
- Child class inherits properties and methods of parent class.
- Child class is called subclass and the parent class is called super class.
- We use **extend** keyword to perform inheritance.
-  A child class can inherit from only one parent class in Java (single inheritance). To inherit from multiple parent classes, we need to create an inheritance hierarchy, where a child class inherits from a parent class, and that parent class, in turn, inherits from another class.
```java
// parent class or super class
class A {
    int i,j;

    void showij(){
        System.out.println("i: "+i);
        System.out.println("j: "+j);
    }
}

// child class or sub class
class B extends A {
    int k;

    void showijk(){
        System.out.println("i: "+i);
        System.out.println("j: "+j);
        System.out.println("k: "+k);
    }
}
```
- Although child class includes all of the members of parent class but it cannot inherit those members which are set to **private** in parent class.

## 09 Calling constructor of parent class from child class : 
- To call constructor of parent class from the child class, we use **super()**.
```java
// parent
class Student {
    String name;
    int rollnumber;
    int age;

    Student(String name, int rollnumber, int age){
        this.name = name;
        this.rollnumber = rollnumber;
        this.age = age;
    }

    void getInfo(){
        System.out.println(this.name);
        System.out.println(this.age);
        System.out.println(this.rollnumber);
    }
}

// child
class BtechStudent extends Student {
    String branch;
    int batch;

    BtechStudent(String name, int rollnumber, int age, String branch, int batch){
        // super
        super(String name, int rollnumber, int age);
        this.branch = branch;
        this.batch = batch;
    }
}


// BtechStudent object
BtechStudent nakul = new BtechStudent("nakul singh", 45, 25, 'ECE', 2018);
```
- We can use **super** in a similar way to how we use **this**. While **this** is used to access members of the same class, **super** is used to access members of the parent class.
- Imagine we override a property of the parent class inside the child class. If there is a situation where we want to use the overridden property as it was implemented in the parent class, we can use super.propertyName to access the parent class's property.

```java
class A {
    int i = 10;
}

// child class or sub class
class B extends A {
    int i = 20;

    void showi(){
        System.out.println(i);  // 20
    }

    void showisuper(){
        System.out.println(super.i);    // 10
    }
}
```

## 10 Abstract class : 
- When a parent class wants its child classes to follow certain, the parent class can be defined as an **abstract** class.
- Sometimes, the parent class cannot predict the exact implementation of its members. In such cases, the parent class delegates the task of implementation to the child class. To achieve this, the parent class must be marked as **abstract**, and the members that will be implemented by the child class must also be declared as **abstract**.
- It is complusory for a child class to implement those members which are marked as **abstract** in parent class.
- Abstract class cannot be used to instantiate objects.

```java
abstract class Shape {
    int dim1, dim2;

    // method marked as abstract
    abstract void area();
}

class Rectangle extends Shape {
    int length, breadth;

    Rectangle(int length, int breadth){
        this.length = length;
        this.breadth = breadth;
    }

    // implementation of method that was previously marked as abstract
    void area(){
        System.out.println(this.length*this.breadth);
    }
}

```

## 11 Final :
- If we use **final** with a variable it will act as a constant.
- If we use **final** will a class then we cannot perform inheritance with that class.
- If we use **final** with a method then we cannot override that method in the child class.

## 12 Interface : 
- Interface is like a blueprint of class, it specifies what a class must do, but not how it does.
- Variables inside the interface are by default **public**, **final** and **static** and the methods are **public**, **abstract**.
- Inside interface we do not define method body only it's name, return data type and method paramter.
- A class can use multiple interfaces.
- If we are defining an interface in a separate file then the name of the file and interface name must be same.
```java
interface Callback {
    void callback(int param);
}
```
- If a class is using one or more interface, the interface is separated by comma. 
- When you implement an interface method, it must be declared as **public**.
```java
class Client implements Callback {
    String userId = "fs3214a";

    // interface method (which is also set to public)
    public void callback(int p){
        System.out.println("p: "+p);
    }

    void getId(){
        System.out.println(this.userId);
    }
}
```
- Interface can extend one another
```java
interface A {
    void showA();
}

interface B extends A {
    void showB();
}

/*
now if a class is implemented using interface B that class must implement
both showA and showB methods 
*/

class Demo implements B {
    public void showA(){
        System.out.println("A");
    }

    public void showB(){
        System.out.println("B");
    }
}
```