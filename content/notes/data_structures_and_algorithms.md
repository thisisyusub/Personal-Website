---
title: "Data Structures and Algorithms"
date: 2022-11-13T19:36:36+04:00
draft: false
subscribe: true
math: true
cover:
    image: /notes/algorithms_and_ds/cover.jpeg
---

## 0. Why use Data Structures?

Data Structure is a way to store and organize data so that it can be used efficiently.

The following are the advantages of a data structure:

- **Efficiency**: If the choice of a data structure for implementing a particular ADT is proper, it makes the program - very efficient in terms of time and space.
- **Reusability**: The data structure provides reusability means that multiple client programs can use the data structure.
- **Abstraction**: The data structure specified by an ADT also provides the level of abstraction. The client cannot see the internal working of the data structure, so it does not have to worry about the implementation part. The client can only see the interface.
---

## 1. Complexity and Asymptotic Analysis

### Asymptotic Analysis

The efficiency of an algorithm depends on the amount of time, storage and other resources required to execute the algorithm. The efficiency is measured with the help of asymptotic notations.

An algorithm may not have the same performance for different types of inputs. With the increase in the input size, the performance will change.

The study of change in performance of the algorithm with the change in the order of the input size is defined as asymptotic analysis.

### Asymptotic Notations

There are mainly three asymptotic notations:

- Big-O notation
- Omega notation
- Theta notation

![Notations](/notes/algorithms_and_ds/notations.jpeg)

#### Big-O notation

Big-O notation represents the upper bound of the running time of an algorithm. Thus, it gives the worst-case complexity of an algorithm.

![Big O math explanation](/notes/algorithms_and_ds/bigo.png)

#### Theta notation

Theta notation encloses the function from above and below. Since it represents the upper and the lower bound of the running time of an algorithm, it is used for analyzing the average-case complexity of an algorithm.

![Theta math explanation](/notes/algorithms_and_ds/theta.png)

#### Omega notation

Omega notation represents the lower bound of the running time of an algorithm. Thus, it provides the best case complexity of an algorithm.

![Omega math explanation](/notes/algorithms_and_ds/omega.png)

### Complexity

![Complexity](/notes/algorithms_and_ds/complexity.jpeg)

---

## 2. Stack and Heap Memory

### What is Stack?

A stack is a special area of computer’s memory which stores temporary variables created by a function. In stack, variables are declared, stored and initialized during runtime.

It is a temporary storage memory. When the computing task is complete, the memory of the variable will be automatically erased. The stack section mostly contains methods, local variable, and reference variables.

**Here, are the pros/benefits of using stack:**
- Helps you to manage the data in a Last In First Out(LIFO) method which is not possible with Linked list and array.
- When a function is called the local variables are stored in a stack, and it is automatically destroyed once returned.
- A stack is used when a variable is not used outside that function.
- It allows you to control how memory is allocated and deallocated.
- Stack automatically cleans up the object.
- Not easily corrupted
- Variables cannot be resized.

**Cons/Drawbacks of using Stack memory are:**
- Stack memory is very limited.
- Creating too many objects on the stack can increase the risk of stack overflow.
- Random access is not possible.
- Variable storage will be overwritten, which sometimes leads to undefined behavior of the function or program.
- The stack will fall outside of the memory area, which might lead to an abnormal termination.

### What is Heap?

The heap is a memory used by programming languages to store global variables. By default, all global variable are stored in heap memory space. It supports Dynamic memory allocation.

The heap is not managed automatically for you and is not as tightly managed by the CPU. It is more like a free-floating region of memory.

**Pros/benefit of using heap memory are:**
- Heap helps you to find the greatest and minimum number
- Garbage collection runs on the heap memory to free the memory used by the object.
- Heap method also used in the Priority Queue.
- It allows you to access variables globally.
- Heap doesn’t have any limit on memory size.

**Cons/drawbacks of using Heaps memory are:**
- It can provide the maximum memory an OS can provide
- It takes more time to compute.
- Memory management is more complicated in heap memory as it is used globally.
- It takes too much time in execution compared to the stack.

---

## 3. Physical and Logical Data Structures and ADT

**Physical data structures** are actually meant for storing the data in the memory. Then on the stored data or values, we may be performing some operations like inserting more values or deleting existing values or searching for the values, and many more operations. Now, the question is, how you want to utilize those values? How you will be performing insertion and deletion? What is the discipline that you are going to follow? That discipline is defined by **logical data structures** i.e. stack, queues, trees, graphs, and hash table.

**Abstract Data type (ADT)** is a type (or class) for objects whose behavior is defined by a set of values and a set of operations. The definition of ADT only mentions what operations are to be performed but not how these operations will be implemented. It does not specify how data will be organized in memory and what algorithms will be used for implementing the operations. It is called “abstract” because it gives an implementation-independent view. 

![Types of Data Structures](/notes/algorithms_and_ds/types-of-data-structure.png)

---

## 4. Recursion

A function that calls itself is known as a recursive function. And, this technique is known as recursion.

### Master Theorem

The master method is a formula for solving recurrence relations of the form:

![Master Theorem](/notes/algorithms_and_ds/master.png)
![Master Theorem](/notes/algorithms_and_ds/recursion-complexity-1.jpg)
![Master Theorem](/notes/algorithms_and_ds/recursion-complexity-2.jpg)

### Types of Recursion

#### Tail Recursion

```cpp
// if it is last statement in the function, it is called [Tail Recursion]
void func(int n) {
   if(n > 0) {
      cout << n << endl;
      func(n-1);
   }
}
```

#### Head Recursion
#### Tree Recursion

#### Indirect Recursion
#### Nested Recursion


