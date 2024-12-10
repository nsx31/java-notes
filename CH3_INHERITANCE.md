## 01: Basics : 
```java
// super class
class Dog {
    String breed, age;
    Dog(String breed, String age){
        this.breed = breed;
        this.age = age;
    }

    void breedName(){
        System.out.println("breed: "+this.breed);
    }
}


// sub class
class Tommy extends Dog {
    String name;
    Tommy(String breed, String age, String name){
        super(breed, age)
        this.name = name;
    }

    void speak(){
        System.out.println(this.name+" says woof!!!");
    }
}

class InheritanceDemo {
    public static void main(String[] args){
        Tommy bruno = new Tommy("pomeranian", "8", "bruno");
        bruno.breedName();
        bruno.speak(); 
    }
}
```

- Although a subclass includes all of the members of its superclass, it cannot access those members of the superclass that have been declared as **private**.
- private members can be accessed with in the same class.

## 02: Method overriding :
- In a class hierarchy, when a method in a subclass has the same name and type signature as a method in its superclass, then the method in the subclass is said to override the method in the superclass. When an overridden method is called through its subclass, it will always refer to the version of that method defined by the subclass.

## 03: Abstract classes : 
- In Java, when the implementation of a class method cannot be determined in advance because it varies across subclasses, we use abstract methods and declare the class as abstract. 
- For example, consider a Shape class with an abstract method area():
    - Each subclass (e.g., Triangle, Rectangle, Square) implements the area() method differently, as the formula for area calculation varies by shape.

```java
abstract class Shape {
    abstract double area(); // Abstract method
}

class Triangle extends Shape {
    private double base, height;

    Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }

    @Override
    double area() {
        return 0.5 * base * height;
    }
}

class Rectangle extends Shape {
    private double length, width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    double area() {
        return length * width;
    }
}

class Square extends Shape {
    private double side;

    Square(double side) {
        this.side = side;
    }

    @Override
    double area() {
        return side * side;
    }
}
```

- Any class that contains one or more abstract methods must also be declared abstract. 

## 04: Using final with inheritance :
- using final to prevent overriding :
    - While method overriding is one of Java’s most powerful features, there will be times when you will want to prevent it from occurring. To disallow a method from being overridden, specify final as a modifier at the start of its declaration. Methods declared as final cannot be overridden.

- using final to prevent inheritance : 
    - Sometimes you will want to prevent a class from being inherited. To do this, precede the class declaration with final. Declaring a class as final implicitly declares all of its methods as final, too. 

