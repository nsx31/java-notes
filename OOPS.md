## 01  Java class : 
- using java class we can define our own data types.
- classes are used to create object.
- a class contains properties and methods which are also known as class members. 

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
- defining two or more methods with same name inside the same class is called method overloading.
- java use type and number of arguments as its guide to determine which version of the overloaded method to actually call.
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
- java has three access modifiers : 
    - public
    - private
    - protected
- when class members are modified by **public**, then those members can be accessed by anyone.
- when class members are modified by **private**, then members can be accessed by other members of same class.
- when no access modifier is used then class members are by default set to **public** but those members are public within its own package.

```java
class Student() {
    public String name;
    private int age;
    private int rollno;
    double percentage;
}
```

