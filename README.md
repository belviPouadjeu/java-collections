# COLLECTIONS IN JAVA

 Collections in Java are a fundamental part of the Java Standard Library and provide a way to store and manipulate groups of objects. 

## 1. Overview of the Java Collections Framework
**collections** are nothing an object that groups miultiple elements into a single unit.

The Java **Collections Framework** is a unified architecture for representing and manipulating collections. It includes:

- **Interfaces**: Define the contract for different types of collections.

- **Implementation**s: Concrete classes that implement the interfaces.

- **Algorithms**: Methods that perform useful operations on collections, such as sorting and searching.
---
## 2. Core Interfaces
The main interfaces in the Collections Framework are:

  - **Collection**: The root interface for all collections.

  - **List**: An ordered collection (sequence). Allows duplicate elements.

  - **Set**: A collection that does not allow duplicate elements.

  - **Queue**: A collection designed for holding elements prior to processing.

  - **Deque**: A double-ended queue.

  - **Map**: An object that maps keys to values. Not a true collection, but part of the framework.
---
## 3. Common Implementations
Here are some commonly used implementations of these interfaces:

  - **ArrayList**: A resizable array implementation of the List interface.

  - **LinkedList**: A doubly-linked list implementation of the List and Deque interfaces.

  - **HashSet**: A hash table implementation of the Set interface.

  - **TreeSet**: A red-black tree implementation of the Set interface, which maintains elements in sorted order.

  - **HashMap**: A hash table implementation of the Map interface.

  - **TreeMap**: A red-black tree implementation of the Map interface, which maintains keys in sorted order.

  - **PriorityQueue**: A priority heap implementation of the Queue interface.

 4. Key Methods
---
Here are some key methods provided by the Collection interface:

  - **add(E e)**: Adds an element to the collection.

  - **remove(Object o)**: Removes an element from the collection.

  - **contains(Object o)**: Checks if the collection contains a specific element.

  - **size()**: Returns the number of elements in the collection.

  - **isEmpty()**: Checks if the collection is empty.

  - **iterator()**: Returns an iterator over the elements in the collection.
---
## 5. Iterating Over Collections
You can iterate over collections using:

  - **Iterator**: Using the iterator() method.

  - **Enhanced for-loop**: For simpler iteration.

  - **Streams**: Using the Stream API introduced in Java 8.
Example:
```java
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add("Cherry");

// Using Iterator
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    System.out.println(iterator.next());
}

// Using Enhanced for-loop
for (String fruit : list) {
    System.out.println(fruit);
}

// Using Streams
list.stream().forEach(System.out::println);
```
---
# A. List Interface
The List interface extends the Collection interface and provides the following key features:

  - **Ordered**: Elements are stored in a specific order (index-based).

  - **Indexed Access**: Elements can be accessed by their index.

  - **Allows Duplicates**: The same element can be added multiple times.

  - **Allows null**: A List can contain null elements.

**Key Methods in the List Interface**
   - **add(E e)**: Adds an element to the end of the list.

   - **add(int index, E element)**: Inserts an element at the specified index.

   - **get(int index)**: Returns the element at the specified index.

   - **remove(int index)**: Removes the element at the specified index.

   - **set(int index, E element)**: Replaces the element at the specified index.

   - **size()**: Returns the number of elements in the list.

   - **indexOf(Object o)**: Returns the index of the first occurrence of the specified element.

   - **lastIndexOf(Object o)**: Returns the index of the last occurrence of the specified element.

  **subList(int fromIndex, int toIndex)**: Returns a view of the portion of the list between the specified indices.

--- 

## 2. Implementations of the List Interface
The **List** interface has several implementations in Java. Let's explore each one:
---
## 2.1 ArrayList
  - **Description**: `ArrayList` is a resizable array implementation of the `List` interface. It is the most commonly used implementation.

  - **Features:**

    - Fast random access (O(1) time complexity for `get` and `set`).

    - Slow insertion and deletion in the middle of the list (O(n) time complexity).

    - Not synchronized (not thread-safe).

  - **Use Case**: Use `ArrayList` when you need fast access to elements and don't need frequent insertions/deletions in the middle of the list.

**Example: ArrayList**
```java
import java.util.ArrayList;
import java.util.List;

public class ArrayListExample {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();

        // Adding elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        // Accessing elements
        System.out.println("First fruit: " + fruits.get(0)); // Output: Apple

        // Updating elements
        fruits.set(1, "Blueberry");
        System.out.println("Updated list: " + fruits); // Output: [Apple, Blueberry, Cherry]

        // Removing elements
        fruits.remove(2);
        System.out.println("After removal: " + fruits); // Output: [Apple, Blueberry]

        // Iterating over the list
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

## Challenges for ArrayList

### Challenge 1: Basic Operations
- Create an ArrayList of integers.

- Add the following elements: `10, 20, 30, 40, 50.`

- Print the size of the list.

- Remove the element at index 2.

- Check if the list contains the number 30.

- Print the updated list.

### Challenge 2: Iteration
  - Create an ArrayList of strings.

  - Add the following elements: `"Apple", "Banana", "Cherry", "Date"`.

  - Iterate over the list using a **for-each loop** and print each element.

  - Iterate over the list using an **iterator** and print each element.

### Challenge 3: Sorting
  - Create an ArrayList of integers.

  - Add the following elements: 34, 12, 56, 7, 23.

  - Sort the list in ascending order using Collections.sort().

  - Sort the list in descending order using a custom comparator.

  - Print both sorted lists.

### Challenge 4: Searching
  - Create an ArrayList of strings.

  - Add the following elements: `"Apple", "Banana", "Cherry", "Date"`.

  - Search for the index of the element `"Cherry"`.

  - Check if the list contains the element `"Grape"`.

  - Print the results.

### Challenge 5: Sublist
  - Create an ArrayList of integers.

  - Add the following elements: `10, 20, 30, 40, 50, 60, 70`.

  - Extract a sublist from index `2 to 5` 
--- 
## 2.2 LinkedList
  - **Description**: `LinkedList` is a doubly-linked list implementation of the `List`and `Deque` interfaces.

  - **Features**:

    - Fast insertion and deletion at both ends (O(1) time complexity).

    - Slow random access (O(n) time complexity for `get` and set`).

    - Not synchronized (not thread-safe).

  - **Use Case**: Use LinkedList when you need frequent insertions/deletions at the beginning or end of the list.

  - **Example: LinkedList**
```java
import java.util.LinkedList;
import java.util.List;

public class LinkedListExample {
    public static void main(String[] args) {
        List<String> fruits = new LinkedList<>();

        // Adding elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        // Adding elements at the beginning
        ((LinkedList<String>) fruits).addFirst("Apricot");

        // Adding elements at the end
        ((LinkedList<String>) fruits).addLast("Date");

        System.out.println("LinkedList: " + fruits); // Output: [Apricot, Apple, Banana, Cherry, Date]

        // Removing elements from the beginning
        ((LinkedList<String>) fruits).removeFirst();

        // Removing elements from the end
        ((LinkedList<String>) fruits).removeLast();

        System.out.println("After removal: " + fruits); // Output: [Apple, Banana, Cherry]
    }
}
```
---

## 2.3 Vector
  - **Description**: Vector is a legacy class that implements a dynamic array. It is similar to `ArrayList` but is synchronized (thread-safe).

  - **Features**:
    - Synchronized (thread-safe).

    - Slower than ArrayList due to synchronization overhead.

    - Increases its size by doubling it when the capacity is exceeded.

  - **Use Case**: Use Vector when thread safety is required.

**Example: Vector**
```java
import java.util.Vector;

public class VectorExample {
    public static void main(String[] args) {
        Vector<String> fruits = new Vector<>();

        // Adding elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        // Accessing elements
        System.out.println("First fruit: " + fruits.get(0)); // Output: Apple

        // Updating elements
        fruits.set(1, "Blueberry");
        System.out.println("Updated vector: " + fruits); // Output: [Apple, Blueberry, Cherry]

        // Removing elements
        fruits.remove(2);
        System.out.println("After removal: " + fruits); // Output: [Apple, Blueberry]
    }
}
```
---
## 2.4 Stack
  - **Description**: Stack is a legacy class that extends `Vector` and implements a last-in-first-out (LIFO) data structure.

  - **Features**:

    - Provides push, pop, and peek methods.

    - Synchronized (thread-safe).

  - **Use Case**: Use Stack when you need a LIFO data structure.

**Example: Stack**
```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();

        // Pushing elements onto the stack
        stack.push("Apple");
        stack.push("Banana");
        stack.push("Cherry");

        // Peeking at the top element
        System.out.println("Top element: " + stack.peek()); // Output: Cherry

        // Popping elements from the stack
        System.out.println("Popped element: " + stack.pop()); // Output: Cherry
        System.out.println("Popped element: " + stack.pop()); // Output: Banana

        // Checking if the stack is empty
        System.out.println("Is stack empty? " + stack.isEmpty()); // Output: false
    }
}
```

## 3. Comparison of List Implementations
| Feature                | ArrayList          | LinkedList           | Vector             | Stack              |
|------------------------|--------------------|----------------------|--------------------|--------------------|
| **Underlying Data Structure** | Dynamic Array      | Doubly-Linked List   | Dynamic Array      | Dynamic Array      |
| **Random Access**      | O(1)              | O(n)                 | O(1)               | O(1)               |
| **Insertion/Deletion** | O(n)              | O(1) at ends         | O(n)               | O(1) at top        |
| **Thread Safety**      | No                | No                   | Yes                | Yes                |
| **Use Case**           | Fast access       | Frequent insertions/deletions | Thread-safe list  | LIFO data structure |


## 4. When to Use Which Implementation?
  - **ArrayList**: Use when you need fast access to elements and don't need frequent insertions/deletions in the middle.

  - **LinkedList**: Use when you need frequent insertions/deletions at the beginning or end of the list.

  - **Vector**: Use when thread safety is required (though `Collections.synchronizedList()` is preferred for `ArrayList`).

  - **Stack**: Use when you need a LIFO data structure.
