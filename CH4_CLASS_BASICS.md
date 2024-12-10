## 01: Classes : 
- variables present inside the class are called instance variables.
- functions present inside the class are called class methods.
- variables and methods defined with in the class are called class members.

```java
// basic structure of class
class Dog {
    // instance variables
    String breed, name;
    int age;

    // constructor method
    Dog(String name, String breed, int age){
        this.name = name;
        this.breed = breed;
        this.age = age;
    }

    // class method
    void bark(){
        System.out.println("dog says woof!!!");
    }

    void getName(){
        System.out.println("dog's name : ",this.name);
    }
}
```

```java
// creating object using the class
class Demo {
    public static void main(String[] args){
        // NOTE : data type of object is Dog
        Dog kutta = new Dog("tommy","desi",8);

        kutta.bark();
    }
}
```

## 02: Method overloading :
- it is possible to define two or more methods with in the same class that share the same name, as long as their parameter declaration are different, this is called method overloading.
- when an overloaded method is invoked, java uses the type and/or number of agruments as its guide to determine which version of the overloaded methods to actually call.

```java
class OverloadDemo {
    // test v1
    void test(){
        System.out.println("no parameter");
    }

    // test v2
    void test(int a){
        System.out.println("a: "+a);
    }

    // test v3
    void text(int a, int b){
        System.out.println("a,b :"+a+","+b);
    }

    // test v3
    double test(double a){
        System.out.println("double a: "+a);
        return a*a;
    }
}

class Overload {
    public static void main(String[] args){
        OverloadDemo od = new OverloadDemo();

        od.test();      // this will call test v1
        od.test(12);    // this will call test v2
        od.test(45,2);  // this will call test v3
        od.test(56.78); // this will call test v4
    }
}
```
- in similar fashion we can do constructor overloading
```java
class Box {
    double width, length, height;

    // cons v1
    Box(double w, double h, double l){
        this.width = w;
        this.height = h;
        this.length = l;
    }

    // cons v2
    Box(){
        this.width = 12;
        this.length = 12;
        this.height = 12;
    }
    
    // cons v3
    Box(double len){
        this.width = this.height = this.length = len;
    }
}

class OverloadCons {
    public static void main(String[] args){
        Box bo = new Box(12.0, 45.0, 23.2); // this will call cons v1
        Box bo1 = new Box();                // this will call cons v2
        Box bo2 = new Box(90.5);            // this will call cons v3
    } 
}
```

## 03: Introduction to access modifiers : 
- public : when a member of a class is modified by public, then that member can be accessed by any other code
- private : when a member of a class is specified as private, then that member can only be accessed by other members of its class.

**Note :** when no access modifier is used, then by default the member of a class is public within its own package, but cannot be accessed outside of its package. 

- static : when we want a class member to use independently i.e without first creating an object then using it in that case we use static. 
    - instance variables declared as static are act as global variables.
    - we cannot call non static methods within the static method.

## 04: Introducing final : 
- A field can be declared as final. Doing so prevents its contents from being modified, making it, essentially, a constant. 
```java
final String USER_ID = "d485613nn1";
```