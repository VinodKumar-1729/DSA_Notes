
### 1. Linear Search
   - **Definition**: Linear search is a straightforward algorithm that checks each element in the array sequentially until the target value is found or the end of the array is reached.
   - **Algorithm Steps**:
     1. Start from the first element.
     2. Compare each element with the target value.
     3. If a match is found, return the index of the element.
     4. If the target is not found, return an indication (e.g., -1 for no match).
   - **Time Complexity**:
     - **Best Case**: O(1), when the target is the first element.
     - **Worst and Average Case**: O(n), where \( n \) is the number of elements.
     - Exam Tip: Expect linear search to take more time as \( n \) grows, since every element might need to be checked.
   - **Space Complexity**: O(1), as it requires constant space.
   - **Key Characteristics**:
     - Works on both sorted and unsorted data.
     - Effective for small datasets or arrays without a specific ordering.
   - **Limitations**:
     - Inefficient for large datasets as every element needs to be checked in the worst case.
     - Not feasible for sorted arrays where binary search can be applied.
   - **Exam-Relevant Insight**:
     - Linear search is often the fallback when the data is unsorted or very small.
     - Questions may compare linear and binary search, focusing on when each is preferred.

---

### 2. Binary Search
   - **Definition**: Binary search is an efficient algorithm that finds the position of a target value within a sorted array by dividing the search interval in half repeatedly.
   - **Precondition**: The array must be sorted in ascending or descending order for binary search to work.
   - **Algorithm Steps**:
     1. Identify the middle element of the array.
     2. If the middle element matches the target, return the index.
     3. If the target is less than the middle element, narrow the search to the left half.
     4. If the target is greater, narrow it to the right half.
     5. Repeat until the target is found or the search space is empty.
   - **Time Complexity**:
     - **Best Case**: O(1), when the target is the middle element initially.
     - **Average and Worst Case**: O(log n), because the search space is halved with each step.
   - **Space Complexity**:
     - **Iterative Implementation**: O(1), requires no extra space beyond a few variables.
     - **Recursive Implementation**: O(log n), due to the call stack from recursive calls.
   - **Key Characteristics**:
     - Binary search is much faster than linear search for large sorted arrays.
     - Only applicable to sorted data structures (arrays, linked lists if doubly linked).
     - A binary search tree (BST) enables binary search with a tree-based data structure.
   - **Limitations**:
     - Not applicable for unsorted data; an unsorted array would need to be sorted first, adding overhead (typically O(n log n)).
   - **Exam-Relevant Insight**:
     - Binary search is optimal when data is sorted and static (unchanging).
     - In competitive exams, binary search questions may appear in contexts like finding a specific value, detecting a boundary (e.g., smallest/largest element greater than a value), or implementing variations (e.g., finding first/last occurrence of duplicates).
   - **Unique Points for Edge in Exams**:
     - **Variants**: Understanding binary search variants like lower bound, upper bound, and binary search on answer space (useful for optimization problems).
     - **Applications**: Binary search is also applied in algorithms involving bisecting sorted ranges, approximate matching, and other optimization cases.
     - **Edge Cases**: Pay attention to edge cases in binary search:
       - Empty array or array with one element.
       - Duplicate elements, especially in questions that specify finding the first or last occurrence of a target value.
       - Non-trivial conditions where the middle element itself should not be counted (e.g., finding nearest greater element).

---

### Additional Insights on Searching Algorithms
   - **Comparison of Linear and Binary Search**:
     - **Linear Search**: Suitable for small or unsorted datasets.
     - **Binary Search**: Highly efficient for sorted data, significantly reducing search time as data grows.
     - Common exam questions might test which algorithm to use in different data scenarios.
   - **Practical Use-Cases**:
     - **Linear Search**: Useful in situations where data structure changes frequently, and sorting is not feasible.
     - **Binary Search**: Optimal in static sorted arrays, databases, and large data collections with structured order.
   - **Variants and Special Cases**:
     - **Exponential Search**: Combines binary and linear search to quickly find an element's position in unbounded or very large datasets by first identifying a range.
     - **Interpolation Search**: Variant of binary search, more efficient in uniformly distributed data but less common in exams due to complexity.
