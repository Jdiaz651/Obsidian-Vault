
---

### **Algorithm Analysis**
- **Purpose**: Evaluate efficiency through time (Big-O) and space complexity analysis.
  - **Big-O Notation**:
    - O(1): Constant Time
    - O(n): Linear Time
    - O(log n): Logarithmic Time
    - O(n log n): Quasi-linear Time
    - O(n²): Quadratic Time
- **Worst-case vs. Average Case**: Consider worst-case scenarios for algorithm performance.

---

### **Data Structures**
- **Primary Structures**:
  - Arrays: O(1) access, O(n) insertion/deletion (for dynamic sizes).
  - Linked Lists: O(n) time complexity for most operations.
  - Stacks and Queues: LIFO/FIFO with constant-time operations at ends.
  - Trees:
    - Binary Search Trees (BST): Average case O(log n), worst-case O(n).
    - Heaps: Used for priority queues, typically implemented as arrays or complete trees.
- **Graphs**: Represent relationships between nodes using adjacency lists or matrices.

---

### **Divide-and-Conquer**
- **Technique**:
  - Split problem into smaller subproblems recursively.
  - Solve each subproblem and combine results (e.g., merge sort).
- **Examples**:
  - Merge Sort: O(n log n) time complexity.
  - QuickSort: Average case O(n log n), worst-case O(n²). Randomized pivot selection can improve average performance.

---

### **Randomization Algorithms**
- **Approach**: Use randomness to enhance efficiency or reduce errors.
  - Example:
    - **Randomized Quicksort**: Selecting a random pivot reduces the chance of worst-case behavior (O(n log n) expected time).
- **Use Cases**:
  - Sorting algorithms, primality testing.

---

### **Combinatorial Search**
- **Technique**: Explore possible solutions in large search spaces.
  - Techniques: Backtracking, Branch-and-Bound.
- **Applications**:
  - Game trees (e.g., minimax algorithm).
  - Optimization problems like the Traveling Salesman Problem or Knapsack problem.

---

### **Dynamic Programming**
- **Principle**: Solve optimization problems by breaking them into overlapping subproblems and storing results to avoid recomputation.
  - Key Components:
    - Optimal Substructure: Solution can be built from solutions of smaller subproblems.
    - Overlapping Subproblems: Many similar or identical subproblems are solved multiple times.
- **Examples**:
  - Knapsack Problem, Shortest Path Algorithms (e.g., Floyd-Warshall), Sequence Alignment in Bioinformatics.

---

### **Key Considerations**
- **Comparison Table**: Create a summary table comparing techniques based on problem type and efficiency.
- **Practice Problems**: Engage in exercises to apply each technique effectively. Focus on real-world applications for better retention, such as web crawlers using memoization or game AI with alpha-beta pruning.
