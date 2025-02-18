# Chapter 2: Algorithm Analysis

## Overview

Algorithm analysis allows us to evaluate algorithms' efficiency independently of language or hardware.

**Key Tools:**

1. RAM Model of Computation
2. Asymptotic Analysis (Big Oh Notation)

## 2.1 RAM Model of Computation

A theoretical model to measure algorithm performance.

**Assumptions:**

- Simple operations (+, *, -, =, if) take one time step.
- Loops and subroutines are composed of basic operations.
- Memory access takes one step; unlimited memory available.

**Key Insight:** Simplifies algorithm analysis while remaining practically relevant.

## 2.1.1 Complexity Analysis

- **Best Case:** Minimum steps required.
- **Worst Case:** Maximum steps required.
- **Average Case:** Expected steps over all inputs.

**Practical Focus:** Worst-case analysis provides reliable performance guarantees.

## 2.2 Big Oh Notation

A mathematical notation to describe upper bounds of running times.

**Definitions:**

- **O(g(n))**: Upper bound.
- **Ω(g(n))**: Lower bound.
- **Θ(g(n))**: Tight bound.

**Examples:**

- f(n)=3n2−100n+6=O(n2)f(n) = 3n^2 - 100n + 6 = O(n^2)
- f(n)=2n+1=Θ(2n)f(n) = 2n + 1 = Θ(2n)

**Takeaway:** Focuses on growth rates rather than constants.

## 2.3 Growth Rates and Dominance

**Growth Order:**

- n!n! > 2n2^n > n3n^3 > n2n^2 > nlog⁡nn \log n > nn > log⁡n\log n > 1

**Implications:**

- Factorial growth quickly becomes impractical.
- Linear and logarithmic algorithms scale well.

## 2.4 Working with Big Oh

### Basic Operations:

- **Addition:** Dominated by the larger function.
- **Multiplication:** Product of complexities.
- **Transitivity:** If f(n)=O(g(n))f(n) = O(g(n)) and g(n)=O(h(n))g(n) = O(h(n)), then f(n)=O(h(n))f(n) = O(h(n)).

## 2.5 Efficiency Analysis

### Selection Sort (Θ(n²))

- Compares elements to find the minimum.

**Time Complexity:**

- T(n)=n(n−1)/2T(n) = n(n-1)/2

### Insertion Sort (Θ(n²))

- Inserts elements into sorted positions.

### String Matching (Θ(nm))

- Checks substring presence using brute force.

### Matrix Multiplication (Θ(n³))

- Multiplies matrices via nested loops.

## 2.6 Summations

Summations simplify running time analysis.

**Examples:**

- Arithmetic series: \sum_{i=1}^n i = rac{n(n+1)}{2}
- Geometric series: \sum_{i=0}^n a^i = rac{a^{n+1}-1}{a-1}

## 2.7 Logarithms in Algorithms

**Applications:**

- **Binary Search:** O(log n)
- **Tree Height:** O(log n) for binary trees.
- **Bit Complexity:** w=log⁡2nw = \log_2 n

**Key Property:** Logarithms grow slowly, even for large inputs.

## 2.8 Logarithmic Properties

- \log_b x = rac{\log_c x}{\log_c b}
- Base differences are insignificant in Big Oh analysis.

## 2.9 War Story: Mystery of the Pyramids

A case study illustrating the impact of algorithmic improvements over raw hardware power.

**Key Lesson:** Efficient algorithms outperform hardware upgrades.

## 2.10 Advanced Analysis

**Esoteric Functions:**

- Inverse Ackermann function: α(n)\alpha(n)
- Double log: log⁡log⁡n\log \log n
- Square root growth: n\sqrt{n}

**Takeaway:** Mastering asymptotic analysis enables better algorithm design.