

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
- https://www.geeksforgeeks.org/binary-heap-notes-for-gate-exam/?ref=lbp  (Main)
- https://www.geeksforgeeks.org/introduction-to-heap/
- https://www.geeksforgeeks.org/applications-advantages-and-disadvantages-of-heap/
- https://www.geeksforgeeks.org/applications-of-heap-data-structure/


### 2. **Heap Properties and Complexity**
   - **Height**: Height of a heap with `n` nodes is `O(log n)`.
   - **Time Complexity**:
     - **Insertion**: `O(log n)` because of heapify-up.
     - **Deletion**: `O(log n)` for heapify-down.
     - **Find Min/Max**: `O(1)` since it’s always at the root.
     - **Build Heap**: `O(n)` when constructing from an unsorted array (using Floyd’s method).
   - **Space Complexity**: `O(n)` for storing `n` elements.

### 3. **Types of Heaps**
   - **Binary Heap**: Most common; complete binary tree that follows the heap property.
   - **Binomial Heap**: Supports faster union operations, often used in network algorithms.
   - **Fibonacci Heap**: Provides improved amortized time for operations; used in advanced algorithms like Dijkstra’s shortest path.
   - **Min-Max Heap**: A double-ended priority queue supporting both min and max operations efficiently.

### 4. **Heapify Operations**
   - **Heapify-Up (Swim)**: Used during insertion; element is moved up the tree until the heap property is restored.
   - **Heapify-Down (Sink)**: Used during deletion or extract-max/min; element is moved down until the heap property is restored.
   - **Recursive and Iterative Implementations**: Know both recursive and iterative ways to implement heapify for handling edge cases effectively.

### 5. **Heap Sort**
   - **Process**: Convert the array to a max-heap and repeatedly extract the max element to sort in ascending order.
   - **Time Complexity**: `O(n log n)` (both average and worst case).
   - **Space Complexity**: `O(1)` (in-place sorting).
   - **Stability**: Heap Sort is not a stable sort (relative order of equal elements may not be preserved).

### 6. **Priority Queues Using Heaps**
   - Heaps are widely used to implement priority queues, especially in cases where dynamic element insertion and deletion are required.
   - Operations:
     - **Insert** (enqueue with priority): `O(log n)`
     - **Extract Max/Min** (dequeue the highest priority element): `O(log n)`

### 7. **Applications of Heaps in Algorithms**
   - **Dijkstra’s Shortest Path Algorithm**: Uses a min-heap to fetch the minimum distance node.
   - **Prim’s Minimum Spanning Tree**: Uses a min-heap for selecting the minimum edge.
   - **Median of Stream of Numbers**: Two heaps (max-heap and min-heap) are used to efficiently find the median in streaming data.
   - **Top-K Elements**: Min-heap can be used to maintain the top K elements of a large dataset.

---
