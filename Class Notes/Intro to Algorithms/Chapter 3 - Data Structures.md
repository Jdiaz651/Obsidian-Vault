# Chapter 3: Data Structures

## 3.1 Contiguous vs. Linked Data Structures

### Contiguous Structures

- Arrays, matrices, heaps, and hash tables.
- Single memory slab.
- **Advantages**:
    - Constant-time index access.
    - Space-efficient: no extra links.
    - Cache-friendly.
- **Drawbacks**:
    - Fixed size.
    - Resizing requires copying.

### Linked Structures

- Lists, trees, and graph adjacency lists.
- Composed of distinct memory chunks.
- **Advantages**:
    - Dynamic size.
    - Insertion/deletion without shifting data.
- **Drawbacks**:
    - Extra memory for pointers.
    - Non-contiguous, less cache-friendly.

## 3.2 Containers: Stacks and Queues

### Stacks (LIFO)

- Operations: **push** (insert), **pop** (remove).
- Real-world analogy: Plate stack.

### Queues (FIFO)

- Operations: **enqueue** (insert), **dequeue** (remove).
- Real-world analogy: Checkout line.

**Implementation**: Arrays (fixed) or linked lists (dynamic).

## 3.3 Dictionaries

**Operations**:

- Search, Insert, Delete.
- Optional: Min, Max, Predecessor, Successor.

**Implementations**:

- **Unsorted arrays**: Fast insert, slow search.
- **Sorted arrays**: Fast search, slow insert.
- **Linked lists**: Efficient insertion/deletion.

## 3.4 Binary Search Trees (BST)

**Properties**:

- Left subtree < node < right subtree.
- Recursive structure.

**Operations**:

- **Search**: Traverse left/right.
- **Insertion**: Insert as leaf.
- **Deletion**: Handle cases with 0, 1, or 2 children.

**Performance**: O(h), where h = tree height.

**Balanced Trees**: Red-black, AVL ensure O(log n) height.

## 3.5 Priority Queues

**Operations**:

- Insert, Find-Minimum/Maximum, Delete-Minimum/Maximum.

**Applications**: Job scheduling, event handling.

**Implementations**:

- Unsorted arrays (slow retrieval),
- Sorted arrays (slow insertion),
- Heaps (balanced performance).

## 3.6 War Story: Stripping Triangulations

**Problem**: Optimize rendering by minimizing vertex transmissions.

- **Heuristic**: Longest strips first.
- **Data Structure**: Priority queue.
- **Insight**: Efficient data structures dramatically improve runtime.

## 3.7 Hashing

**Concept**: Map keys to indices via a hash function.

**Collision Handling**:

- **Chaining**: Linked lists per bucket.
- **Open addressing**: Sequential probing.

**Applications**:

- Document deduplication.
- Plagiarism detection.
- Cryptographic integrity.

## 3.8 Specialized Data Structures

- **Strings**: Suffix trees/arrays.
- **Geometric**: kd-trees.
- **Graphs**: Adjacency lists.
- **Sets**: Bit vectors.

## 3.9 War Story: String 'em Up

**Bioinformatics Challenge**: Efficiently detect DNA substrings.

**Solution**: Hash tables replaced BSTs for performance gains.

**Lesson**: Data structure selection critically impacts performance.