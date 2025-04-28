## Primitive Data Types
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

