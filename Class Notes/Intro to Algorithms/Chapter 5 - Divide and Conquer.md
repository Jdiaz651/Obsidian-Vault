# Chapter 5: Divide and Conquer

## 5.1 Introduction to Divide and Conquer

Divide and conquer is a fundamental algorithm design technique that breaks a problem into smaller, more manageable subproblems, solves each recursively, and then combines their results.

### Key Characteristics

- **Recursive Structure**: Problems are divided into smaller instances of the same problem.
    
- **Parallel Processing**: Subproblems can be solved in parallel, enhancing performance on multicore processors.
    

**Example:** Mergesort divides an array into halves, sorts each half, and then merges the sorted halves.

## 5.2 Binary Search and Variants

### Binary Search Algorithm

Binary search is the classic divide-and-conquer algorithm for searching in a sorted array.

```
int binary_search(int s[], int key, int low, int high) {
    if (low > high) return -1;
    int mid = (low + high) / 2;
    if (s[mid] == key) return mid;
    if (s[mid] > key) return binary_search(s, key, low, mid - 1);
    return binary_search(s, key, mid + 1, high);
}
```

**Complexity:** O(log n)

### Variants

- **Counting Occurrences**: Modify binary search to find block boundaries.
    
- **One-Sided Binary Search**: Search for transitions in unbounded arrays.
    
- **Square Root Computation**: Bisection method to approximate square roots.
    

## 5.3 Recurrence Relations

Recurrence relations define an algorithm's time complexity based on smaller subproblems.

**Examples:**

- **Mergesort**: T(n) = 2T(n/2) + O(n) → O(n log n)
    
- **Binary Search**: T(n) = T(n/2) + O(1) → O(log n)
    
- **Fast Heap Construction**: T(n) = 2T(n/2) + O(log n) → O(n)
    

### Master Theorem Cases

For recurrences of the form T(n) = aT(n/b) + f(n):

1. **Case 1**: If f(n) grows slower → Θ(n^log_b a)
    
2. **Case 2**: If f(n) matches → Θ(n^log_b a * log n)
    
3. **Case 3**: If f(n) grows faster → Θ(f(n))
    

## 5.4 Fast Multiplication

### Karatsuba’s Algorithm

- Reduces n-digit multiplication to three multiplications of n/2 digits each.
    
- **Recurrence:** T(n) = 3T(n/2) + O(n)
    
- **Time Complexity:** O(n^1.585)
    

### Strassen’s Matrix Multiplication

- Multiplies two n×n matrices in O(n^2.81) using 7 recursive steps.
    

## 5.5 Largest Subrange and Closest Pair

### Largest Subrange Sum

- Divide array into two halves.
    
- Compute max subrange in left, right, and across the middle.
    
- **Time Complexity:** O(n log n)
    

### Closest Pair Problem

- Sort points by x-coordinate.
    
- Divide into left and right subsets.
    
- Recursively find closest pairs and check across the boundary.
    
- **Time Complexity:** O(n log n)
    

## 5.6 Parallel Algorithms

Parallel computing can significantly accelerate divide-and-conquer algorithms by executing subproblems concurrently.

### Pitfalls

- Diminishing returns when overhead dominates.
    
- Debugging complexity due to race conditions.
    
- Load imbalance if tasks are not evenly distributed.
    

## 5.7 Convolution

Convolution combines two sequences to produce a third sequence.

**Mathematical Definition:**

### Applications

- **Polynomial Multiplication**
    
- **String Matching**
    
- **Cross-Correlation Analysis**
    

**Fast Convolution:** Reduces complexity from O(n²) to O(n log n) using the Fast Fourier Transform (FFT).

## 5.8 War Story: Debugging with Binary Search

A virology research team applied binary search techniques to identify a lethal gene sequence efficiently, highlighting divide and conquer’s practicality beyond computing.

**Key Lesson:** Parallelized binary search can drastically reduce experimental time.

## 5.9 Summary

Divide and conquer simplifies complex problems by recursive decomposition and efficient recombination. Mastery of recurrence relations and parallel execution is crucial for optimizing such algorithms.