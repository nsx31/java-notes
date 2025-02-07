# Source File Naming Convention 
- If a source file contains a public class, then the name of the source file and the name of that public class must be same.
- If a source file does not contain any public class then we can name source file whatever we want.

**Note :** A source file can contains at max only one public class.

# Import Statement
- If a Java class is present in the same folder as the source file, we don’t have to explicitly import that class; it is by default available to the source file. In all other cases, we have to explicitly import the classes.

# Package Statement
- A source file can have at most one package statement.
- Package statement must be the first statement in a source file.

# Class Level Modifiers
Modifiers that can be used with top level class :
- public 
- abstract 
    - if a class is an absract class, object creation of that class is not possible.
- final
    - if a class is using `final` modifier, creating subclass of that class is not possible.

Modifiers that can be used with inner class : 
- public
- abstract
- final
- private
- protected
- static

# Abstract Modifier 
- Abstract modifier can be used with methods and classes.
- Sometimes we can only predict the declartion of a function but not its implementation since its implementation depends on other factors in that case its better if we define that function as **abstract**.
```java
abstract class Vehicle {

    // abstract method
    public abstract int getNoOfWheels();
}
```
- If a class contains atleast one **abstract** method then that class also has to be declared as **abstract**.
- If a class does not contains any **abstract** method, we can still declare that class as **abstract** if we want to.
- A child class has to provide implementation of each abstract method present inside the abstract parent class.