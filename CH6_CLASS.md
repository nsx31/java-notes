## 01 Class :
We use classes to create objects. Classes in Java also act as user-defined data types. A class contains methods and properties, which are referred to as class members.

```java
class Box {
    // class property
    double length, breadth, height;

    // constructor
    Box(double length, double breadth, double height){
        this.length = length;
        this.breadth = breadth;
        this.height = height;
    }

    // method
    double boxArea(){
        return length*breadth*height;
    }
}
```

```java
class Demo {
    public static void main(String[] args){
        /* 
            - First we created a variable b1 of 'Box' data type.
            - This box variable will store the memory address of Box object
              which is present in the heap memory. 
        */

        /*
            - A reference variable which not initialised only just declared,
              will always point towards null.
        */

        /*
            - Right now the variable is pointing to null since we didn't 
              initialize the variable.         
        */

        Box b1;

        // This will create a box object in heap memory
        b1 = new Box(12,12,12);

        // We can use dot operator to access the object elements
        System.out.println(b1.boxArea());   // 1728.0
    }
}
```

## 02 Method and Constructor overloading :
Method overloading mean creating multiple functions that have same name. During compile time java compiler will figure out which version of overloaded function to call based on number of method parameter and data type of parameter.

```java
// version 1
void sum(int a, int b){
    System.out.println(a+b);
}

// version 2
double sum(double a, double b){
    return a+b;
}

// version 3
double sum(double a, double b, double c){
    return a+b+c;
}


sum(2.1, 2.2); // java compiler will call version 2 of sum function
```

Similarly we can do constructor overloading 
```java
class Box {
    double l, b, h;

    Box(){
        // default parameter
        this.l = 10;
        this.b = 34;
        this.h = 54;
    }

    Box(double a, double f, double c){
        l=a;
        b=f;
        h=c;
    }
}
```

## 03 Passing object as parameter : 
```java
class Main {
    public static void main(String[] args){
        Box ob = new Box(12,33,69);
        showDimensions(ob); /*  
                                length : 12
                                breadth : 33
                                height : 69
                            */
    }

    static void showDimensions(Box ob){
        System.out.println("length : "+ob.length);
        System.out.println("breadth : "+ob.breadth);
        System.out.println("height : "+ob.height);
    }
}
```

## 04 Access control :
If we do not mention anything then by default class and class members are set to `public` but they are public with in their own package, outside code cannot access that class and class members.

- **public** 
- **private**
- **protected**
- **static** : if we want a class member to not depend on instance of that class in that case we define that class member as static.
    - static instance variable act like global variable.
    - you are not allowed to use non-static method inside the static method.
- **final**: 
    - When `final` is used with a variable, the variable behaves like a constant.
    - If a class method is defined as `final`, it cannot be overridden in a subclass.
    - To prevent the creation of subclasses, declare the class as `final`.

## 05 Array of objects :
```java
class Main {
    public static void main(String[] args){
        Box[] b = {
            new Box(1,2,3),
            new Box(4,5,6),
            new Box(7,8,9)
        } 

        /*
            b = [
                    {
                        length: 1,
                        breath: 2,
                        height: 3,
                    },
                    {
                        length: 4,
                        breath: 5,
                        height: 6,
                    },
                    {
                        length: 7,
                        breath: 8,
                        height: 9,
                    }
                ]

            above object will also contain area method 
            but for the sake of complexity i ignored it for now
        */
    }
}

``` 