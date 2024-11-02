### Binary Search Trees (BST) 
---

#### 1. **Definition and Structure**
   - **Binary Search Tree (BST)** is a type of binary tree where each node follows these properties:
     - The **left subtree** contains only nodes with values **less than** the node’s value.
     - The **right subtree** contains only nodes with values **greater than** the node’s value.
     - Each subtree must also be a BST.
   - **Recursive Nature**: Each subtree in a BST is itself a BST, which enables recursive approaches to operations like insertion, deletion, and searching.

#### 2. **Key Properties**
   - **In-Order Traversal** of a BST yields the elements in **sorted order**.
   - **Uniqueness**: Duplicate values are usually not allowed. Some variations like "Multiset BSTs" allow duplicates, often stored on one side consistently.
   - **Sorted Storage**: This property makes BSTs ideal for applications requiring sorted data retrieval.

#### 3. **Common Operations and Complexity**
   - For a BST of **height h**:
     - **Best Case (Balanced Tree)**: The height \( h = \log_2(n) \), where \( n \) is the number of nodes.
     - **Worst Case (Unbalanced Tree)**: Height can be as large as \( n \) (degenerates to a linked list).

   - **Insertion**:
     - Traverse the tree to find the appropriate leaf position where the new value should be inserted.
     - **Time Complexity**: 
       - Average: **O(log n)**
       - Worst Case (Unbalanced): **O(n)**
     - **Special Case**: In self-balancing BSTs like AVL or Red-Black Trees, rotations are used to maintain balanced height.

   - **Searching**:
     - Search down from the root, moving left or right based on comparisons.
     - **Time Complexity**: 
       - Average: **O(log n)**
       - Worst Case (Unbalanced): **O(n)**
     - **Use Case**: Efficiently finding minimum/maximum, or checking for existence of a specific element.

   - **Deletion**:
     - Deletion involves three main cases:
       1. **Node with No Children**: Directly remove the node.
       2. **Node with One Child**: Remove the node and link its parent to its child.
       3. **Node with Two Children**: Replace the node with its **in-order successor** (smallest node in the right subtree) or **in-order predecessor** (largest node in the left subtree).
     - **Time Complexity**:
       - Average: **O(log n)**
       - Worst Case: **O(n)** in an unbalanced tree.

#### 4. **Types of BSTs**
   - **Balanced Binary Search Trees**: Designed to avoid degenerating into a linked list, such as:
     - **AVL Trees**: Self-balances using rotations to ensure height difference of subtrees is at most 1.
     - **Red-Black Trees**: Uses coloring properties to maintain a balanced structure.
   - **Threaded Binary Search Trees**: Improves efficiency by threading nodes, allowing quick in-order traversal without recursion.

#### 5. **Applications of BSTs**
   - **Search Operations**: BSTs allow efficient searching in sorted data structures, especially when balanced.
   - **Sorting**: In-order traversal provides sorted output without extra space.
   - **Data Storage**: BSTs store hierarchical data with ordered properties, making them useful in:
     - **Database Indexing**: Indexing data for quick retrieval.
     - **Dictionaries and Sets**: Storing and quickly accessing unique keys.
   - **Other Uses**: Range queries, interval trees, and priority scheduling can also use BST variations.

#### 6. **Advanced Concepts**
   - **In-Order Successor and Predecessor**:
     - **In-Order Successor** of a node in a BST is the next node in in-order traversal, useful for deletion.
     - **In-Order Predecessor** is the previous node in in-order traversal.
   - **Height-Balancing**: Keeping the tree balanced is key for efficiency:
     - BSTs like **AVL Trees** use rotations to maintain height balance after insertions and deletions.
     - Red-Black Trees have a maximum height of **2 log(n)**, ensuring near-constant time operations.

#### 7. **Exam-Relevant and Unique Points**
   - **Degeneration to Linked List**:
     - A BST becomes inefficient if nodes are inserted in sorted order, leading it to behave like a linked list with O(n) operations.
     - To avoid this, balanced BSTs like **AVL** or **Red-Black** trees should be used.
   - **Range Queries**:
     - BSTs support range queries (finding all elements within a specific range) in O(k + log n) time, where \( k \) is the number of nodes in the range.
   - **Self-Balancing Trees**:
     - Know the difference between AVL (more strictly balanced, requires more rotations) and Red-Black Trees (less strict but easier to maintain), as they may appear in exam questions on efficiency trade-offs.
   - **Threaded BSTs**:
     - Some exams might explore concepts like **Threaded BSTs**, where pointers point to the in-order successor or predecessor instead of NULL, optimizing in-order traversal time.

#### 8. **Key Differences Between Binary Tree and BST**
   - **Binary Tree**: A node can have any arrangement of children.
   - **BST**: Nodes must follow a strict ordering (left child < parent < right child).
   - **Complexity and Applications**: Binary trees are simpler but can be inefficient for ordered data, whereas BSTs are ideal for scenarios needing sorted data.

---
