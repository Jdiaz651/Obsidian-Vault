# Chapter 1: Introduction to Algorithm Design

## What is an Algorithm?

An **algorithm** is a well-defined procedure designed to solve a specific task. It forms the core of computer programs.

- **Problem vs. Instance**:
    
    - **Algorithmic Problem**: Describes the set of all valid input instances and expected outputs.
        
    - **Instance**: A specific input for the algorithm to process.
        
- **Example – Sorting Problem**:
    
    - **Input**: A sequence of keys
        
    - **Output**: A permutation
        

**Key Properties of Good Algorithms:**

1. **Correctness**: Produces the expected results for all valid inputs.
    
2. **Efficiency**: Uses minimal computational resources.
    
3. **Ease of Implementation**: Simple, readable, and maintainable code.
    

### Example: Insertion Sort

Insertion sort incrementally builds a sorted array by inserting elements into their correct position.

**Algorithm Logic:**

- Start with the first element as a sorted array.
    
- Repeatedly insert the next element into its correct position relative to the sorted portion.
    

**C Implementation:**

```
void insertion_sort(item_type s[], int n) {
    int i, j;
    for (i = 1; i < n; i++) {
        j = i;
        while (j > 0 && s[j] < s[j - 1]) {
            swap(&s[j], &s[j - 1]);
            j--;
        }
    }
}
```

**Key Insight**: The algorithm is generic and works with any comparable elements, such as strings or integers.

## Robot Tour Optimization

**Problem**: Find the shortest closed tour that visits each point in a set `S`.

**Real-World Context**: Used in manufacturing, robotics, and logistics to minimize travel distance.

**Heuristics Explored**:

4. **Nearest-Neighbor**: Start at a point and repeatedly visit the closest unvisited neighbor.
    
    - Simple and intuitive.
        
    - Fails in certain layouts, causing inefficient routes.
        
5. **Closest-Pair**: Merge the closest pairs of points until all points form a single closed tour.
    
    - Better performance in some cases.
        
    - Still susceptible to suboptimal outcomes.
        

**Optimal TSP Algorithm:**

- Enumerates all `n!` possible tours.
    
- Guarantees an optimal solution.
    
- Computationally infeasible for large inputs due to factorial complexity.
    

**Takeaway**: Algorithms guarantee correctness, while heuristics offer approximations without assurance.

## Movie Scheduling Problem

**Scenario**: An actor must choose movies to maximize work time without overlapping schedules.

**Problem Statement**:

- **Input**: A set of movie intervals with start and end times.
    
- **Output**: The largest subset of intervals with no overlaps.
    

**Proposed Heuristics:**

6. **Earliest Start Time**: Select the earliest starting movie available.
    
7. **Shortest Duration**: Choose the movie with the shortest runtime.
    
8. **Earliest Finish Time**: Select the movie that ends the earliest.
    

**Correct Algorithm:**

- Select the movie with the earliest finishing time.
    
- Remove all overlapping movies.
    
- Repeat until no movies remain.
    

**Key Lesson**: Intuition can be misleading; formal reasoning ensures correctness.

## Algorithm Correctness

Correctness means the algorithm solves the problem correctly for all valid inputs.

### Methods to Establish Correctness:

- **Formal Proofs**: Use mathematical induction and logical deductions.
    
- **Counterexamples**: Identify inputs that break the algorithm.
    

**Key Techniques for Finding Counterexamples:**

- Test minimal cases.
    
- Explore edge cases and extremes.
    
- Investigate scenarios with ties.
    

**Example**: The nearest-neighbor heuristic fails in cases where points are symmetrically distributed.

### Induction & Recursion:

- Inductive reasoning proves properties hold for all natural numbers.
    
- Recursive algorithms often lend themselves to inductive proofs.
    

## Modeling Problems

Algorithm design often involves abstracting real-world applications to standard computational problems.

**Common Abstract Structures:**

- **Permutations**: Sequences or orderings.
    
- **Subsets**: Combinations of elements.
    
- **Trees**: Hierarchical relationships.
    
- **Graphs**: Networks of interconnected elements.
    
- **Points**: Geometric coordinates.
    
- **Polygons**: Shapes and regions.
    
- **Strings**: Character sequences.
    

**Takeaway**: Accurate modeling simplifies algorithm design and implementation.

## War Story: Psychic Modeling

### Context:

A company sought help to optimize lottery ticket purchases based on psychic predictions.

**Challenge**: Minimize tickets while ensuring coverage of predicted numbers.

**Key Lessons:**

- Validate models with small test cases.
    
- Use abstractions to manage complexity.
    

**Outcome**: After refining the model, the company successfully implemented an efficient ticket selection system.

## Additional Insights

- **Estimation**: Approximate performance and resource requirements.
    
- **Proof by Contradiction**: Assume the opposite to demonstrate falsehood.
    
- **Recursive Structures**: Identify patterns in self-similar data structures.
    

**Final Thought**: Algorithm design blends creativity, logical reasoning, and empirical validation.