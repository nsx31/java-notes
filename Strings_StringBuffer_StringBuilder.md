# 01 Difference between String and StringBuilder :
1. `String` are immutable while `StringBuilder` is mutable.
2. `String` override the defult behaviour of `equals()` method while `StringBuilder` don't.

```java
// verifying strings are immutable in java
String name = new String("loco");
name.concat("poco");
System.out.println(name);   // loco
```
```java
// verifying StringBuffer is mutable in java
StringBuffer sb = new StringBuffer("es ");
sb.append("loce es");
System.out.println(sb);     // es loce es
```

# 02 String object creation in Heap memory and String Constant Pool (SCP) :