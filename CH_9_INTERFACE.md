1. Just like **class** we can use **interface** to create our own data type. 
2. A **class** can inherit can inherit multiple **interfaces**.

```java
// **************** INTERFACE CREATION ****************
public interface BoxModel {
    double boxVolume(double l, double b, double h);
}
```

```java
// **************** INTERFACE IMPLEMENTATION ****************
class Box implements BoxModel {
    String label;

    Box(String label){
        this.label = label;
    }

    // interface method
    @Override
    double boxVolume(double l, double b, double h){
        return l*b*h;
    }

    void labelBox(String name){
        label = name;
    }
}
```

```java
// **************** INTERFACE AS DATA TYPES ****************
class Demo {
    public static void main(String[] args){
        // class as data type
        Box bb = new Box();
        bb.boxVolume(2.0, 3.0, 4.0);
        bb.labelBox("red label");

        // interface as data type
        BoxModel aa= new Box();
        aa.boxVolume(2.0, 3.0, 4.0);
        aa.label("the taj");   // error

        /******* Why error? ******
        When we use interface as a data types we can access only 
        those methods which are defined inside the interface.  
        */
    }
}
```