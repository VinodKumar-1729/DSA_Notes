
### Introduction to Stack
- **Definition**: A stack is a linear data structure where elements are added and removed from the same end, called the **top**.
- **LIFO Principle**: Last In, First Out (LIFO) states that the most recently added element is removed first. A stack of plates represents this concept well.

### Basic Operations on Stack
1. **Push(x)**: Adds element `x` to the top of the stack.
2. **Pop()**: Removes and returns the top element of the stack.
3. **Top/Peek()**: Returns the current top element without removing it.
4. **isEmpty()**: Returns `true` if the stack is empty; otherwise, `false`.
5. **Size()**: Returns the number of elements in the stack.

| Operation | Time Complexity |
|-----------|-----------------|
| Push      | O(1)            |
| Pop       | O(1)            |
| Top       | O(1)            |
| isEmpty   | O(1)            |
| Size      | O(1)            |

### Stack Implementation using Linked List
- **Concept**: In a linked list-based stack, elements are stored as nodes in a singly linked list, allowing dynamic growth.
- **Advantages**:
  - **Dynamic Sizing**: Unlike arrays, a stack in a linked list has no fixed size, eliminating overflow unless memory is full.
- **Implementation Details**:
  - **Push Operation**: Creates a new node, links it to the current top, and updates the top pointer.
  - **Pop Operation**: Removes the top node and updates the top pointer.
  - **Peek Operation**: Returns the value of the top node.
  - **Display Operation**: Traverses from the top to the end, printing each node's value.

### Competitive Exam Insights
1. **Key Properties**:
   - Operations are all O(1) due to direct access to the top of the stack.
   - Stack is suitable for any function with an LIFO requirement.
   - Stack overflow and underflow conditions are critical for understanding error handling.

2. **Edge Cases to Note**:
   - **Stack Overflow**: Occurs when pushing to a full stack (only in fixed-size implementations).
   - **Stack Underflow**: Occurs when popping from an empty stack.
   
3. **Practical Applications**:
   - **Browser History**: URLs stored in a stack to allow backtracking.
   - **Function Calls**: Each function call is pushed to a stack; upon return, it is popped, ensuring LIFO order.
   - **Expression Evaluation**: Used in evaluating postfix expressions.
   - **Balanced Parentheses**: Helps in checking if parentheses are balanced.
   - **Backtracking Algorithms**: Stacks help in storing previous states during recursive function calls.
   
### Additional Applications in Detail
1. **Function Calls and Recursion**: The call stack stores the current function call and its data. When a function returns, the last call’s data is popped, ensuring recursive and nested calls execute correctly.
2. **Undo/Redo Operations**: The last action is stored at the top of the stack, and an undo operation involves popping this action.
3. **Expression Evaluation**:
   - **Infix to Postfix**: Operators are pushed into a stack based on precedence, converting expressions from infix to postfix notation.
   - **Postfix Evaluation**: Operands are pushed, and operators pop operands for calculation.

### Advantages of Stack
1. **Simple to Implement**: Stack operations are straightforward.
2. **Efficient Memory Use**: Contiguous memory allocation (in arrays) can reduce memory usage.
3. **Fast Access**: Only the top element is accessed or modified.
4. **Supports Recursion**: Recursion is implemented using a stack.
5. **Backtracking Support**: The LIFO nature is suitable for backtracking.

### Disadvantages of Stack
1. **Limited Capacity**: In array-based stacks, overflow can occur if the size is exceeded.
2. **No Random Access**: Elements can only be accessed sequentially from the top.
3. **Memory Management**: Contiguous blocks can lead to fragmentation with frequent changes.
4. **Not Suitable for Middle Element Access**: Accessing non-top elements is inefficient.
5. **Stack Overflow/Underflow**: These errors are common in recursive calls and need to be managed in applications like parsers and algorithms.

### Infix to Postfix Operation
1. **Precedence Handling**: Operators are stored in the stack based on precedence and associativity. Higher precedence operators are pushed before lower ones.
2. **Associativity Rules**:
   - `^` operator is **right-associative**; operators like `+`, `-`, `*`, `/` are **left-associative**.
3. **Algorithm Summary**:
   - For each operand, add it to the postfix expression.
   - For each operator, check precedence and add it to the stack if appropriate.
   - If `(` is encountered, it’s pushed; `)` pops until `(` is found.
   - At the end, pop remaining operators from the stack.

### Postfix Evaluation Using Stack
- Traverse the expression from left to right.
- Push operands to the stack.
- When encountering an operator, pop the top two elements, apply the operation, and push the result back to the stack.
  
### Towers of Hanoi Using Stack
1. **Objective**: Move disks from one rod to another without placing a larger disk on a smaller disk.
2. **Rules**:
   - Only one disk can be moved at a time.
   - The goal is to move all disks to the target rod.
3. **Algorithm**:
   - Use recursion, moving N-1 disks to an auxiliary rod before transferring the largest disk.

### Competitive Exam Preparation Tips for Stack
1. **Understanding Edge Cases**:
   - Be aware of stack overflow and underflow.
   - Know which applications require fixed vs. dynamic stacks.
2. **Special Problems on Stack**:
   - **Balanced Parentheses**: Often tested with edge cases.
   - **Expression Evaluation**: Conversion from infix to postfix or prefix notation.
3. **Theoretical Knowledge**:
   - **Pros and Cons of Array vs. Linked List Implementation**: Know the memory constraints and benefits.
4. **Advanced Applications**:
   - Be familiar with **reverse polish notation**, **call stack structure**, and real-world **undo/redo systems**.
5. **Time and Space Complexities**:
   - Understand when a stack provides O(1) time for all operations.
   - Know the recursion limitations due to stack depth (common in deep recursive calls).

---
