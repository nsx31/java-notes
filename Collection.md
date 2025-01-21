#### Location of collection framework : 
`java.util` package.

#### Why do we need collection framework ?
To understand the need of collection framework let's first understand the limitations of arrays. Since we already have arrays, why do we need more data structures that collection framework provides.

##### Limitation of arrays : 
1. **Fixed Size:** Arrays have a fixed size, which must be determined at the time of creation and cannot be changed later.
2. **Homogeneity:** Arrays are homogeneous in nature, meaning they can store only one type of object. 
3. **Lack of Built-in Methods:** Arrays do not have an underlying data structure. As a result, there are no ready-made methods available for operations like sorting, deletion, or searching. This requires developers to repeatedly implement these functionalities from scratch.
4. **Inefficient Memory Utilization:** Arrays can lead to poor memory utilization. For instance, if an array of 100 elements is created but only 2 elements are initialized at runtime, the remaining 98 positions are wasted.

To overcome these challenges java introduces collection framework. It provides built-in interfaces and methods that allow us to efficiently store and manage individual objects as part of a unified collection. 

![Alt text](./images/Screenshot_20250121_144854.png)

#### Collection Framework 
Interfaces offered by the collection framework can be divided into two categories :
1. Interfaces that define data structures storing objects in key-value pairs
Example: The `Map` interface.
2. Interfaces that define data structures storing objects in non-key-value pairs
Example: The `Collection` interface. 

#### 5 Key interfaces offered by the collection framework :
1. **Collection Interface :** The `Collection` interface is rarely used directly; instead, its child interfaces are more commonly utilized. The Collection interface provides general-purpose methods that are applicable to any collection object. Example : `add()`, `remove()`, `size()`, `isEmpty()`.

    ##### 1.1 Difference between `Collection` and `Collections` : 
    `Collection` is an interface while `Collections` is an utility class which defines several utility methods for collection objects. `Collections` is also the part of collection framework. Example: If we want to sort `ArrayList` use `Collections.sort()` method.

2. **List :** It is a child interface of `Collection` interface. When we want to store duplicate value along with their insertion order in that case use `List` interface. Implemented classes of `List` interface are `ArrayList`, `LinkedList`, `Vector`
3. **Set :**: Again it is a child interface of `Collection` interface. When we want to store non-duplicate value and the order of insertion does not matter in that case use `Set` interface. 
4. **Queue :** It is a child interface of `Collection` interface. It is used when we want to store the data before processing the data.
5. **Map :** When we want to store collection object in key value pair in that case we use map interface. 

#### Comparable interface : 
When we want the default sorting order i.e sorting order that collection framework offers then use this interface.

#### Comparator interface :
But if want to create our own sorting order then use this inteface.

#### Cursors :
Suppose we want to extract an object from the collection in that case we need cursors. There are 3 cursors in java :
1. Enumeration interface
2. Iterator interface
3. ListIterator interface


#### Utility Classes : 
There are two utility classes in collection framework :
1. Collections
2. Arrays
