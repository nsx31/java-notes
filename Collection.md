#### Q1: Why do we need collection framework ?
To understand the need of collection frameword let's first understand the limitations of arrays. Since we already have arrays, why do we need more data structures that collection frameword provides.

##### Limitation of arrays : 
1. **Fixed Size:** Arrays have a fixed size, which must be determined at the time of creation and cannot be changed later.
2. **Homogeneity:** Arrays are homogeneous in nature, meaning they can store only one type of object. 
3. **Lack of Built-in Methods:** Arrays do not have an underlying data structure. As a result, there are no ready-made methods available for operations like sorting, deletion, or searching. This requires developers to repeatedly implement these functionalities from scratch.
4. **Inefficient Memory Utilization:** Arrays can lead to poor memory utilization. For instance, if an array of 100 elements is created but only 2 elements are initialized at runtime, the remaining 98 positions are wasted.

To overcome these challenges java introduces collection framework. It provides built-in interfaces and methods that allow us to efficiently store and manage individual objects as part of a unified collection. 

![Alt text](./images/Screenshot_20250121_144854.png)

