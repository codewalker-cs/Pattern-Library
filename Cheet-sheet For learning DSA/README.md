# 📘 Time & Space Complexity Patterns

A quick reference guide for identifying time complexity patterns in loops and recursion.  
Designed for coding interviews and DSA preparation.

---

# 🔹 Loop Complexity Patterns

## 📌 Basic Loop Patterns

| Pattern | Example | Time Complexity |
|----------|----------|----------------|
| Linear increment | `for(int i=0; i<n; i++)` | **O(n)** |
| Increment by constant | `for(int i=0; i<n; i+=k)` | **O(n)** |
| Exponential growth | `for(int i=1; i<n; i*=2)` | **O(log n)** |
| Exponential shrink | `for(int i=n; i>0; i/=2)` | **O(log n)** |

---

## 📌 Nested Loop Patterns

| Pattern | Explanation | Time Complexity |
|----------|------------|----------------|
| Independent nested loops | `for(i<n) for(j<n)` | **O(n²)** |
| Triangular loop | `for(i<n) for(j<i)` | **O(n²)** |
| n × log n | Outer O(n), inner O(log n) | **O(n log n)** |

---

## 📌 Special Summation Pattern

### 1 + 2 + 4 + 8 + … + n

This is a geometric progression.

Total sum = `2n - 1`

Therefore:

**Time Complexity = O(n)**

Even though values double each time, total work is linear.

---

# 🔹 Recursion Complexity Patterns

Understanding recursion requires analyzing:

- Number of recursive calls
- Size reduction per call
- Work done per call

---

## 📌 Basic Recurrence Patterns

| Pattern | Recurrence | Time Complexity |
|----------|------------|----------------|
| Linear recursion | `f(n-1)` | **O(n)** |
| Divide by 2 | `f(n/2)` | **O(log n)** |
| Two calls reducing by 1 | `2 * f(n-1)` | **O(2^n)** |
| Two calls reducing by half | `2 * f(n/2)` | **O(n)** |
| Fibonacci type | `f(n-1) + f(n-2)` | **Exponential (≈ O(2^n))** |

---

# 🔹 Why These Complexities Occur

## ✅ f(n-1)

- Recursion depth = n  
- Each call does constant work  
- Total time = **O(n)**  

---

## ✅ f(n/2)

- Input size halves every step  
- Number of steps = log₂n  
- Total time = **O(log n)**  

---

## ✅ 2 × f(n/2)

Recursion tree:

Level 0 → 1 call  
Level 1 → 2 calls  
Level 2 → 4 calls  
...  
Depth = log n  

Total nodes = 1 + 2 + 4 + … + n  

**Total time = O(n)**

---

## ✅ f(n-1) + f(n-2)

This generates a Fibonacci recursion tree.

Nodes grow exponentially.

Time complexity ≈ **O(2^n)**

---

# 🔹 Quick Recognition Guide

If code has:

- One loop → O(n)
- Loop inside loop → O(n²)
- Loop doubling variable → O(log n)
- Recursion splitting into two halves → O(n)
- Recursion reducing by 1 with two branches → Exponential

---

# 🎯 Interview Tip

Before solving any DSA problem:

1. Predict brute force complexity.
2. Optimize approach.
3. Recalculate complexity.
4. Justify why it improved.

If you cannot explain complexity clearly,
you are not interview-ready.
