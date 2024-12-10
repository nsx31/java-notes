Before diving deeper, remember that in Java, almost everything is treated as an object except for primitive data types, loops, and statements.

## 01: Primitve and Reference data types : 
- primitve data types also known as built in data types.
    - integers : 
        - byte
        - short
        - int
        - long
    - float : 
        - double
        - float
    - characters : 
        - char
    - booleans : 
        - boolean
```java
// integers
byte b = 12;
short s = 5;
int i = 454;
long x = 73245L;

// float
double d = 12.12;
float e = 45.23F;

// characters
char option = 'd';

// booleans
boolean isAdmin = false;
```
- reference data types also known as user defined data types.
    - objects
    - arrays
    - strings
    - classes

**NOTE :** in java, primitive data types also have corresponding reference type counterparts (e.g., int → Integer, double → Double). This allows primitive values to be used in Java's collection framework, which only supports reference types. These reference types are part of Java's wrapper classes.

## 02: Variables : 

When we initialize a variable with a primitive data type, the variable stores the actual value. However, when we use a reference data type, the variable stores the memory address of the **object**, not the actual value. In other words, the reference variable points to the location where the value is stored, effectively creating a reference to that value. 

## 03: Type casting : 

```java
// cast: integer to floating point number
int x = 12;
float z = (float)x;

// cast: floating point number to integer
int avg = (int)12.45;
```

## 04: Arrays :

```java
// array declaration
int[] arr;
// array initialization
arr = new int[30];


// array declaration and array initializtion in single line
int[] days = new int[30];

// assigning values to the array during array declaration
int[] rollNo = {1,2,3,4,5,6};
```

in java array creation is a two step process:
1. first, we declare a reference variable of the array type (e.g., int[] arr;).
2. then, we create the actual array object in the heap memory (e.g., arr = new int[5]). This step allocates memory for the array elements and associates the reference variable with the memory location.


---

### **Step 1: Creating a Reference Variable**
When you declare an array like this:

```java
int[] days;
```

- **What happens?**
  - A **reference variable** named `days` is created in memory.
  - This reference variable can point to an array of integers.
  - At this point, no memory has been allocated for the actual array elements. The variable `days` is just a placeholder, initialized to `null`.

- **Key points:**
  - `int[]` indicates the type of elements the array will hold (integers in this case).
  - The reference variable is stored in the **stack memory**.

---

### **Step 2: Creating the Actual Array Object in Heap Memory**
When you use the `new` keyword, like this:

```java
days = new int[30];
```

- **What happens?**
  - Java allocates memory in the **heap** to store 30 integers.
  - Each element is initialized to its default value (`0` for integers, `false` for booleans, `null` for objects, etc.).
  - The reference variable `days` now points to this memory location.

- **Key points:**
  - `new int[30]` explicitly tells Java:
    - Allocate memory for 30 integers.
    - Initialize each element with the default value.
  - The reference (`days`) holds the address of this memory location.

---

### Combined Syntax
Typically, these two steps are combined into a single line for simplicity:

```java
int[] days = new int[30];
```

This is just shorthand for:
1. Declaring the reference: `int[] days;`
2. Creating the array: `days = new int[30];`

---

### Why Two Steps?
The separation of reference declaration and object creation provides:
1. **Flexibility**: You can declare the reference first and initialize it later, depending on conditions in your program.
   ```java
   int[] days; // Declare the reference
   if (someCondition) {
       days = new int[7]; // Initialize the array based on a condition
   } else {
       days = new int[30];
   }
   ```
2. **Type Safety**: The reference type (`int[]`) ensures that the array will only hold integers, avoiding runtime errors.
