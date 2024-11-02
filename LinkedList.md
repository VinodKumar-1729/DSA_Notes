
### Linked Lists (DSA)

#### Definition
A **Linked List** is a linear data structure where each element, called a **node**, contains:
1. **Data**: The actual information stored in the node.
2. **Pointer/Link**: A reference to the next node in the sequence (in the case of singly linked lists) or to both the next and previous nodes (in doubly linked lists).

Linked lists provide dynamic memory allocation, allowing efficient management of memory in cases where array sizes are difficult to predict.

#### Types of Linked Lists

1. **Singly Linked List (SLL)**
   - **Structure**: Each node has data and a pointer to the next node. 
   - **Operations**: Traversal is unidirectional, from the head to the tail.
   - **Use Cases**: Useful for applications where only forward traversal is needed, like a simple implementation of a stack.

2. **Doubly Linked List (DLL)**
   - **Structure**: Each node has three components: data, a pointer to the next node, and a pointer to the previous node.
   - **Operations**: Allows traversal in both directions, which makes it more versatile than a singly linked list.
   - **Memory Overhead**: Due to the extra pointer for the previous node, DLLs require more memory.
   - **Use Cases**: Often used in applications where bi-directional traversal is needed, like in the navigation system of a browser (forward and backward links).

3. **Circular Linked List (CLL)**
   - **Structure**: Similar to singly or doubly linked lists, but the last node points back to the first node, forming a circular structure.
   - **Operations**: Traversal can start from any node and eventually loop back to it.
   - **Use Cases**: Suitable for applications that require a cyclic traversal, such as a round-robin scheduling mechanism.

#### Key Operations

1. **Access**
   - **Time Complexity**: \(O(n)\) (where \(n\) is the number of nodes), as linked lists do not support random access like arrays.
   - **Sequential Access**: Nodes must be accessed in sequence, starting from the head.

2. **Insertion**
   - **At Head**: \(O(1)\) - Directly updating the head pointer to the new node.
   - **At Tail**: \(O(n)\) if only the head is referenced; \(O(1)\) if the tail is directly accessible (common in circular or doubly linked lists).
   - **In Middle**: \(O(1)\) if the location is known, but \(O(n)\) if traversal is required to find it.

3. **Deletion**
   - **At Head**: \(O(1)\) - Update the head pointer to the next node.
   - **At Tail**: \(O(n)\) if only the head is referenced; \(O(1)\) if the tail is directly accessible.
   - **In Middle**: \(O(1)\) if the node reference is known; otherwise, \(O(n)\) for traversal.

4. **Traversal**
   - **Time Complexity**: \(O(n)\) for both singly and doubly linked lists. For circular linked lists, traversal ends when we revisit the starting node.
   - **Applications of Traversal**: Useful for performing operations like searching, counting nodes, or updating values in each node.

#### Unique/Exam-Relevant Points

- **Memory Efficiency**: Linked lists are efficient in cases of unpredictable sizes, as they use dynamic memory allocation. Unlike arrays, they do not require contiguous memory, reducing the chance of memory fragmentation.

- **Pointer Manipulation in DLLs**: With an extra pointer (prev), DLLs offer more flexibility in node manipulation. However, this requires handling four pointers for insertion and deletion, making implementation more error-prone.

- **Circular Linked Lists for Cyclic Tasks**: This structure is ideal for applications like **round-robin scheduling**, **playlist loops**, and **real-time gaming**, where cyclic iteration is essential.

- **Sentinel Nodes**: Some implementations use **sentinel (dummy) nodes** to simplify edge cases, such as inserting or deleting at the head or tail without additional checks.

- **Space Complexity**: Since each node has a pointer, the space complexity for linked lists is higher than for arrays. In DLLs, the space complexity is effectively double that of an SLL due to the additional pointer.

#### Applications of Linked Lists
1. **Dynamic Memory Allocation**: Frequently used in OS memory management to handle the allocation and deallocation of memory blocks.
2. **Undo Mechanisms**: In applications like text editors, where each change can be stored as a node in a linked list, allowing for undo and redo actions.
3. **Hash Tables (Collision Handling)**: Linked lists are often used in hash tables for chaining, where each index in the table points to a linked list of entries with the same hash.
4. **Implementing Stacks/Queues**: Linked lists allow efficient implementation of stacks and queues, particularly when the size of the data is dynamic.
  
#### Exam Tips and Tricks
- **Tricky Edge Cases**: For singly linked lists, pay attention to null pointer exceptions, especially when adding or removing nodes at the head or tail.
- **Reverse a Linked List**: Frequently asked in competitive exams; reversing a singly linked list can be done in \(O(n)\) time with iterative pointer manipulation.
- **Merge Sorted Linked Lists**: Another popular question; merging two sorted lists without creating additional nodes requires careful pointer adjustments.
