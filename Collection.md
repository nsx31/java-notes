### Chapter 01: Overview
---
<br>

# 01 Location of collection framework : 
`java.util` package.

# 02 Why do we need collection framework ?
To understand the need of collection framework let's first understand the limitations of arrays. Since we already have arrays, why do we need more data structures that collection framework provides.

## 2.1 Limitation of arrays : 
1. **Fixed Size:** Arrays have a fixed size, which must be determined at the time of creation and cannot be changed later.
2. **Homogeneity:** Arrays are homogeneous in nature, meaning they can store only one type of object. 
3. **Lack of Built-in Methods:** Arrays do not have an underlying data structure. As a result, there are no ready-made methods available for operations like sorting, deletion, or searching. This requires developers to repeatedly implement these functionalities from scratch.
4. **Inefficient Memory Utilization:** Arrays can lead to poor memory utilization. For instance, if an array of 100 elements is created but only 2 elements are initialized at runtime, the remaining 98 positions are wasted.

To overcome these challenges java introduces collection framework. It provides built-in interfaces and methods that allow us to efficiently store and manage individual objects as part of a unified collection. 

![Alt text](./images/Screenshot_20250121_144854.png)

# 03 Collection Framework 
Interfaces offered by the collection framework can be divided into two categories :
1. Interfaces that define data structures storing objects in key-value pairs
Example: The `Map` interface.
2. Interfaces that define data structures storing objects in non-key-value pairs
Example: The `Collection` interface. 

## 3.1 Five key interfaces offered by the collection framework :
1. **Collection Interface :** The `Collection` interface is rarely used directly; instead, its child interfaces are more commonly utilized. The Collection interface provides general-purpose methods that are applicable to any collection object. Example : `add()`, `remove()`, `size()`, `isEmpty()`.

    ##### 1.1 Difference between `Collection` and `Collections` : 
    `Collection` is an interface while `Collections` is an utility class which defines several utility methods for collection objects to use. `Collections` class is also a part of collection framework. 

2. **List :** It is a child interface of `Collection` interface. When we want to store duplicate values along with their insertion order in that case use `List` interface. Implemented classes of `List` interface are `ArrayList`, `LinkedList`, `Vector`
3. **Set :** Again it is a child interface of `Collection` interface. When we want to store non-duplicate value and the order of insertion does not matter in that case use `Set` interface. 
4. **Queue :** It is a child interface of `Collection` interface. It is used when we want to store the data before processing it.
5. **Map :** When we want to store collection object in key value pair in that case we use map interface. 

## 3.2 Comparable interface : 
When we want the default sorting order i.e sorting order that collection framework offers then use this interface.

## 3.3 Comparator interface :
But if want to create our own sorting order then use this inteface.

## 3.4 Cursors :
If we want to extract objects from a collection but objects extraction is done at one object at a time then we should go for cursors. There are three type of cursors available in java :
1. `Enumeration` interface
2. `Iterator` interface
3. `ListIterator` interface


## 3.5 Utility Classes : 
There are two utility classes in collection framework :
1. Collections
2. Arrays

<br>

---
### Chapter 02: Everything in detail
---
<br>

# 01 Collection Interface :
- If we want to represent a group of individual objects as a single quantity in that case we use collection interface.
- Collection Interface defines most common methods which are applicable for any collection object.
- Methods provided by `Collection` interface : 
```java
boolean add(Object o)
boolean addAll(Collection o)
boolean remove(Object o)
boolean removeAll(Collection o)
void clear()
boolean retainAll(Collection c)     // removes everything except c
boolean isEmpty()
int size()
boolean contains(Object o)
boolean containsAll(Collection c)
Object[] toArray()
Iterator iterator()
```

**Note** : Collection Interface does not contain any methods to reterive objects. 

# 02 List Interface :
- It is a child interface of `Collection` interface. 
- We use `List` interface when we want to insert duplicate values and also want to maintain the insertion order. 
- In `List` inteface, **index** play an important role. Using **index** we can maintain insertion order as well as differentiate between duplicate values.
- Methods provided by `List` interface :

```java
List l = new ArrayList();

l.add("a");
l.add(int index, Object o);         // adding object at specific index.
l.addAll(int index, Collection c)   // adding a group of objects at specific. location
l.remove(int index)                 // remove element from specific index.
l.indexOf("A")                      // returns the index of first occurrence of. "A".
l.lastIndexOf("A")                  // returns the last index of "A".
l.get(int index)                    // returns object present at that index.
l.listIterator()                    // returns object one by one.
l.set(int index, Object o)          // replace element at specific location.
```
## 2.1 Implemented classes of `List` interface : 
### 1. ArrayList Class :
- Underlying data structure of `ArrayList` is resizable array.
- Duplicates are allowed and insertion order is preserved.
- Hetrogenous objects are allowed.
**Note:** Hetrogenous objects are allowed in collection framewok except in case of `TreeSet` and `TreeMap`.
- `null` insertion is allowed .

### ArrayList Constructors :
```java
/* *************** FIRST TYPE OF CONSTRUCTOR ***************
Creates an empty ArrayList object with default initial capacity 10.
Once ArrayList reaches its map capacity a new ArrayList will be created with
new capacity = (currentCapacity * 3/2) + 1.
*/
ArrayList al = new ArrayList()


/* *************** SECOND TYPE OF CONSTRUCTOR ***************
When we want to define an ArrayList with different intial capacity then we use this 
constructor.
*/
ArrayList l = new ArrayList(int newIntialCapacity)


/* *************** THIRD TYPE OF CONSTRUCTOR ***************
When we want to create equivalent ArrayList using collection object in that case
use this constructor.
*/
ArrayList l = new ArrayList(Collection c);
```

**Usually we can use Collections to hold and transfer Objects from one place to another place, to provide support for this requirement every Collection already implements `Serializable` and `Cloneable` interface.**

- To make sure any element can be accessed in same amount of constant time whether it is first element or the last element both `ArrayList` and `Vector` class implement `RandomAccess` interface.
    - `RandomAccess` interface is present inside `java.util` package. It does not contain any methods hence it is a **Marker** interface.
- If our frequent operation is retrieval of data then `ArrayList` is the best choice since it implements RandomAccess interface. 
- If our frequent operation is insertion or removal of objects from the middle then `ArryaList` is the worst choice since it requires several shifting operation.  

### Difference between ArrayList and Vectors 
![Alt](./images/ArrayListVsVectors.png)
- ArrayList size grows as: (currentSize * 3/2) + 1 while Vectors size doubles.

### How to get synchronized version of ArrayList object :
```java
ArrayList l = new ArrayList();

List newList = Collections.synchronized(l);
```

### 2. LinkedList Class :
- Underlying data structure for LinkedList is doubly linked list.
- Insertion order is preserved and duplicates are allowed.
- Hertogenous elements are allowed.
- `null` insertion is possible.
- LinkedList implements `Serializable` interface and `Clonable` interface but not `RandomAccess` interface.
- If insertion and deletion of data from the middle is our ultimate requirement then going for the `LinkedList` is our best option.
- `LinkedList` is the worst choice if we want to retrieve an element because our program has to iterate over each element to get to the desired element becuase previous element stores the memory location of the next element.
- Using array we can implement stack and queue very easily but same can be done using `LinkedList` although it can be quite challenging. To ease out our pain LinkedList class provides 6 methods which we can use during stack and queue implementation.  
```java
void addFirst(Object o)
void addLast(Object o)
Object getFirst()
Object getLast()
Object removeFirst()
Object removeLast()
```

### LinkedList Constructors :
```java
// creates empty linked list object.
LinkedList l = new LinkedList();

// creates an equivalent linked list object for the given collection.
LinkedList = new LinkedList(Collection c);
``` 

### Difference between ArrayList and LinkedList :
![Alt](./images/Screenshot%20From%202025-01-24%2015-29-02.png)


### 3. Vectors :
- Underlying data structure is growable arrays.
- Duplicates are allowed and insertion order is maintained.
- Hetrogenous objects are allowed.
- `null` insertion is allowed.
- Vectors implements `Serializable`, `Clonable` and `RandomAccess` interface.
- All methods of vectors are synchronous hence they are thread safe.
- Best choice if the frequesnt operation is retrieval.

```java
// these are some vector specific methods
int size()
int capacity()
Object elementA(int index)
Object firstElement()
Object lastElement()
removeElement()
removeElementAt()
removeAllElement()
addElement()

/*
If we don't want to use these vectors specific methods we can also use equivalent
methods provided by the List and Collection interface.
For example: 
add()
remove()
set()
.
.
.
etc.
*/
```

### Vector Constructor :
```java
// creates vector object with 10 initial capacity
// capacity of newly created vector when current vector gets filled is twice the size of current vector.
Vector v = new Vector();


// creates empty vector object with specified initial capacity
Vector v = new Vector(int newInitialCapacity);


// if we dont want the new vector to double every time current vector get filled 
// then we can define our own inceremental value. 
Vector v = new Vector(int initialCapacity, int incrementalCapacity);


// creates equivalent vector object for the given collection
Vector v = new Vector(Collection c);
```

### 4. Stack :
- It is a child class of `Vector` class. 
- `Stack` works on LIFO (last-in-first-out) model.
```java
push(Object o)  // add element into the stack.
pop()           // remove element from the top of the stack.
peek()          // returns element present at the top of the stack without removing it.
empty()         // check if stack is empty.
offset search(Object o) // from top of the stack at which level the object is present. 
                        // and returns -1 if it does not exists.
```

### Stack constructor :
```java
Stack s = new Stack()
```

# 03 Cursors :
If we want to retrieve objects one by one  from the collections then we should go for Cursors. There are three type of cursors in java :
1. Enumeration
2. Iterator
3. ListIterator

## 3.1 Enumeration :
To get `Enumeration` use `elements()` method with `Vector`.
```java
Vector v = new Vector();
Enumeration e = v.elements();

/*
In enumeration we have only two methods :
1. boolean hasmoreElements();
2. Object nextElement();
*/ 
```
```java
// Example :
Vector v = new Vector();
for(int i=0; i<=10; i++){
    v.addElement(i);
}

// printing only those elements which are even
Enumeration e = v.elements();
while(e.hasmoreElements()){
    Integer i = (Integer)e.nextElement();

    if(i%2 == 0){
        System.out.println(i);
    }
}
```

### Limitations of Enumeration :
- can only be used with legacy code.
- using `Enumeration` we can only read data but we cannot remove the data.

To overcome these problems java introduces `Iterator` cursor.

## 3.2 Iterator :
- It is a universal cursor.
- With iterator we can do both read as well as remove operation.
- `Collection` interface contins `iterator()` method which returns Iterator.
- Methods available in Iterator interface are:
```java
boolean hasNext()
Object next()
void remove()
```
```java
ArrayList c = new ArrayList();  // c can be any collection object

Iterator itr = c.iterator();
```

### Limitations of Iterator :
- Both iterator and enumeration can only move in formward direction, they cannot move in backward direction.
- We cannot perform replace, add operation with iterator.

## 3.3 ListIterator : 
- It is a child interface of Iterator interface.
- It is bidirectional cursor.
- With listiterator we can perform read, remove, replace, addition of new objects.
- `List` interface has `listIterator()` method which returns ListIterator.
- Methods available in ListIterator :
```java
// forward movement
boolean hasNext()
Object next()
int nextIndex()

// backward movement
boolean hasPrevious()
Object previous()
int previousIndex()

void remove()
void set(Object o)
void add(Object o)
```

```java
LinkedList l = new LinkedList();    // l can only be list object
l.add("papi");

ListIterator ltr = l.listIterator();
```

**Note :** ListIterator is the most powerful cursor but its limitation is, it is applicable only for list objects.