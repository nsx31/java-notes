## 01 Ineritance :
We use the `extends` keyword to create child classes from a parent class. A child class can have only one parent class in Java.

```java
class Animal {
    int legs;

    Animal(int l){
        legs = l;
    }
}

class Dog extends Animal {
    String name;
    int age;

    Dog(int legs, String name, int age){
        super(legs);
        // this is also correct 
        // super.legs = legs;
        this.name = name;
        this.age = age;
    }

    void bark(){
        System.out.println("dog says woof");
    }
}
```

- If a member in the parent is set to private then child class cannot access that member.

## 02 Method overriding : 
Redefining a method in a child class that already exists in the parent class is called method overriding. We can avoid this by setting that method as `final` in the parent class.

## 03 Avoid inhertiance :
If we want to prohibit inheritance of a class, i.e., prevent creating a child class from a parent class, declare the parent class as `final`.

## 04 Abstract class :
- If a parent class want its child classes to follow certain rules and regulations in that case we set that parent class as `abstract`.
- Suppose we create a parent class called Shapes and child classes such as Rectangle, Triangle, and Square. The parent class contains two integer variables and one method to calculate the area. Since different shapes have different formulas for area calculation, the parent class cannot predict the formula to use beforehand. In such cases, it is better for the child classes to implement the area function. To avoid a situation where a child class forgets to implement the area function, we define the area function in the parent class as `abstract`. This ensures that the child class must implement the area function; otherwise, it cannot use the parent class. When we define a class member as `abstract`, we also need to define the class itself as `abstract`.
```java
// parent 
abstract class Shapes {
    int dim1 , dim2

    Shapes(int a, int b){
        dim1 = a;
        dim2 = b;
    }

    // abstract method
    abstract int area();
}

// child
class Rectangle extends Shapes {
    Reactangle(int l, int b){
        super(l,b);
    }

    // child class cannot change signature of abstract method
    int area(){
        return l*b;
    }
}
```
- We cannot create instance of an abstract class.
- Java has a built in class called `Object` class. All the other classes that exists in java are childen class of the `Object` class. `Object` class have some methods that each child class inherits : 
    - toString()
    - equals()
    - wait()
    - clone() and many more.