

### Hashing

**Definition:**  
Hashing is a technique used to map data to a specific, fixed-size data structure called a hash table. This mapping is done through a **hash function** that converts data (keys) into a unique index within the table, allowing for efficient data storage and retrieval. Hashing is commonly applied in scenarios where quick access to data is crucial, such as database indexing and caching.

**Key Components of Hashing:**

1. **Hash Function:**  
   - A function that takes an input (or key) and returns an integer, which is used as an index to place the data in a hash table.
   - A good hash function minimizes the probability of two keys mapping to the same index (collision).
   - **Characteristics of an Ideal Hash Function:**
     - **Deterministic:** Produces the same output for the same input each time.
     - **Uniformity:** Distributes data across the hash table evenly.
     - **Efficiency:** Computes quickly, with minimal processing time.
     - **Non-reversible:** Hard to reverse engineer the input from the hash output, which also enhances data security.

2. **Hash Table:**  
   - A data structure that stores key-value pairs and uses hash functions to determine the index for each key.
   - In case of a collision, hash tables use various methods to handle it.

3. **Collisions in Hashing:**  
   - **Collision:** When two keys produce the same hash value, leading them to the same index.
   - **Collision Resolution Techniques:**
     - **Separate Chaining:** Links entries at the same index through a linked list.
     - **Open Addressing:** Searches for another available index based on specific probing sequences:
       - **Linear Probing:** Looks at the next available index.
       - **Quadratic Probing:** Probes at intervals that increase quadratically.
       - **Double Hashing:** Uses a secondary hash function if the first one results in a collision.

**Common Operations in Hashing:**

1. **Insertion/Search:**
   - **Time Complexity:** 
     - **Average Case:** \(O(1)\) due to direct access by the hash function.
     - **Worst Case:** \(O(n)\) when many collisions occur, leading to degraded performance.
   - **Deletion:** Performed by finding the key and either marking it as deleted or removing it directly if using chaining.

**Applications of Hashing:**

- **Implementing Associative Arrays/Maps:** Allows key-value pairing, where each key is hashed to store the corresponding value.
- **Database Indexing:** Quick lookup of records based on unique keys.
- **Caches:** Stores frequently accessed data to reduce retrieval time in web servers and databases.
- **Symbol Tables in Compilers:** For storing variables and functions in programming languages.
- **Password Storage (Cryptographic Hashing):** Hashes user passwords to enhance security.

**Key Properties in Competitive Exams:**

1. **Load Factor (α):**
   - Defined as \(\alpha = \frac{n}{m}\), where \(n\) is the number of entries, and \(m\) is the size of the hash table.
   - **Impact on Performance:** A higher load factor increases the probability of collisions.
   - **Load Factor Thresholds:** Hash tables may resize when a certain load factor threshold is reached to maintain efficiency.

2. **Rehashing:**  
   - A technique used to increase the size of the hash table when the load factor exceeds a specified threshold.
   - During rehashing, all elements are reinserted into a new, larger hash table using the hash function, reducing collisions.

3. **Types of Hash Functions:**
   - **Division Method:** Uses modulo operation (e.g., \( h(k) = k \mod m \)).
   - **Multiplication Method:** Multiplies the key with a constant and takes the fractional part to generate the index.
   - **Universal Hashing:** Randomly selects a hash function from a family of functions, reducing the probability of collision under adversarial inputs.

4. **Perfect Hashing:**  
   - A specialized type of hashing with no collisions, ideal for static datasets.
   - **Minimal Perfect Hashing:** Ensures no empty spaces and no collisions, with exactly one slot for each key, commonly used in compiler symbol tables.

**Unique and Exam-Relevant Points:**

1. **Cryptographic Hashing:**  
   - Although not used in typical data structures, cryptographic hashing (e.g., SHA-256) has applications in secure data storage and is notable in competitive exams for its one-way and collision-resistant properties.

2. **Hashing with Load Balancing:**  
   - In distributed systems, **consistent hashing** helps distribute data across multiple servers efficiently, balancing load and ensuring fault tolerance. This concept is crucial in large-scale data processing systems like NoSQL databases.

3. **Double Hashing (for Competitive Exams):**  
   - Double hashing uses two different hash functions to compute the index and handle collisions more effectively than linear or quadratic probing, which may come up as an advanced question on hashing in exams.

---
