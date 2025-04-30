## 01 : Classes
- Class defines a new data type. Once defined, this new data type can be used to create objects of that type.
- General form of class : 

```java
class Box{
    // instance variables 
    double length, width, height;

    // constructor method
    Box(double length, double width, double height){
        this.length = length;
        this.width = width;
        this.height = height;
    }

    // class method
    double volume(){
        return length*width*height;
    }
}
```
- Obtaining objects of a class is a two step process. First, we must decalre a variable of the class type. This variable does not define an object. Instead, it is simply a variable that can refer to an object. Second, we must acquire an actual, physical copy of the object and assign it to that variable. We can do this using the `new` operator. The new operator dynamically allocates an object and returns a reference to it. 

```java
// variable of type Box
Box myBox;

// actual object creation
myBox = new Box();

// we can do both steps in one single line
Box myBox = new Box();
```
- Constructor defines what occurs when an object of a class is created. 

```java
Box myBox = new Box(12,12,12);
myBox.volume();     // 1728
```