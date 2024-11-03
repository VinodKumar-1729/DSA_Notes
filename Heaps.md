

### **Heaps (DSA)**

#### **Definition and Properties**
- **Heap**: A specialized binary tree-based data structure that satisfies the **heap property**.
  - **Max-Heap**: For any given node \( N \), the value of \( N \) is greater than or equal to the values of its children. The maximum value is stored at the root.
  - **Min-Heap**: For any given node \( N \), the value of \( N \) is less than or equal to the values of its children. The minimum value is stored at the root.
- **Structure**:
  - Heaps are **complete binary trees** (all levels except possibly the last are fully filled, and nodes are as left-aligned as possible).
  - Stored as arrays to optimize memory usage and traversal.

#### **Array Representation of Heaps**
- **Indexing**: If a node is at index \( i \), its children and parent can be found as:
  - **Left child**: \( 2i + 1 \)
  - **Right child**: \( 2i + 2 \)
  - **Parent**: \( \frac{{i - 1}}{2} \)
- Array representation saves memory by eliminating pointers.

#### **Common Operations**
1. **Insertion**:
   - **Time Complexity**: \( O(\log n) \)
   - **Process**:
     1. Insert the new element at the next available position in the array (maintains completeness).
     2. **Heapify Up**: Compare the new element with its parent; if it violates the heap property, swap it with the parent and repeat until the property is restored.
   - **Edge Case**: Inserting into an empty heap directly places the element at the root.

2. **Deletion**:
   - **Primary Operation**: Remove the root element (max or min element, depending on heap type).
   - **Time Complexity**: \( O(\log n) \)
   - **Process**:
     1. Replace the root with the last element in the heap.
     2. **Heapify Down**: Compare the new root with its children; if it violates the heap property, swap it with the appropriate child and repeat until the property is restored.
   - **Edge Case**: Deleting from a single-element heap leaves it empty.

3. **Peek**:
   - Retrieves the root element without removing it.
   - **Time Complexity**: \( O(1) \)
   - **Use**: Allows easy access to the maximum or minimum value.

4. **Heapify (Building a Heap)**:
   - Converts an unordered array into a heap.
   - **Bottom-Up Approach**: Starts heapifying from the last non-leaf node to the root.
   - **Time Complexity**: \( O(n) \) (more efficient than \( O(n \log n) \) due to amortized cost on lower levels).

#### **Applications**
1. **Priority Queues**:
   - Heaps are commonly used to implement priority queues where the highest (or lowest) priority element is accessed first.
   - **Advantages**: Efficient access to priority elements, dynamic adjustments of priorities.

2. **Heap Sort**:
   - **Algorithm**: Builds a heap from the array, then repeatedly extracts the root to build a sorted array.
   - **Time Complexity**: \( O(n \log n) \)
   - **Stability**: Not stable, meaning equal elements may not retain their initial order.

#### **Types of Heaps**
1. **Binary Heap**:
   - Most common form of heap, organized as a binary tree.
   - **Balanced** and ensures efficient \( O(\log n) \) insertions and deletions.

2. **d-ary Heap**:
   - A generalization where each node has \( d \) children (e.g., 3-ary, 4-ary).
   - **Advantage**: Decreases the tree height, potentially improving performance for large data sets.

3. **Fibonacci Heap**:
   - Used in advanced applications (e.g., **Dijkstra's shortest path algorithm**).
   - **Amortized Time Complexity**: \( O(1) \) for insertion and decrease-key operations.
   - **Benefits**: Improves performance in applications with many decrease-key operations.

#### **Exam-Relevant Concepts**
- **Complexity Awareness**:
  - In competitive exams, remember that **Insertion** and **Deletion** in binary heaps both have a time complexity of \( O(\log n) \), while **Building a Heap** is \( O(n) \), not \( O(n \log n) \).
- **Heapify Distinction**:
  - Understand the difference between **Heapify Up** (used in insertion) and **Heapify Down** (used in deletion).
- **In-place Sorting**:
  - Heap sort is **in-place** (does not require additional storage), making it memory efficient compared to other sorting algorithms like merge sort.

#### **Out-of-the-Box Points**
- **Lazy Deletion**:
  - Instead of physically deleting nodes, a "deleted" flag can mark nodes. Useful in scenarios requiring frequent heap adjustments.
- **Real-World Use Cases**:
  - Task scheduling, bandwidth management, and load balancing often use heaps for efficient prioritization.
- **Amortized Complexity Insight**:
  - Building a heap in \( O(n) \) time for **heapify** is possible due to the decreased height impact on lower levels of the binary tree (fewer swaps at higher levels).

#### **Tricky Edge Cases**
- **Handling Duplicates**:
  - Heaps do not typically guarantee the order of duplicates. In exams, questions may test how duplicates affect the order, especially in heap sort.
- **Memory Management**:
  - For large data sets, heaps may require significant memory. Optimizations in memory usage can be tested, particularly with d-ary or Fibonacci heaps.

--- 

**GFG Links :** 
- https://www.geeksforgeeks.org/introduction-to-heap/
- https://www.geeksforgeeks.org/applications-advantages-and-disadvantages-of-heap/
- https://www.geeksforgeeks.org/applications-of-heap-data-structure/
