# Mathematics Concepts Library

This folder contains mathematical concepts and tricks used in different
Data Structures & Algorithms problems.

The goal is to build a **personal pattern library** of reusable ideas
that appear in competitive programming and coding interviews.

Each concept file should contain:
- Intuition behind the idea
- Explanation of the concept
- C++ implementation (if applicable)
- Example problems where the concept is used

---

# Concepts

## 1. Cantor's Diagonal Argument

Cantor's Diagonal Argument is a technique used to construct an element
that differs from every element in a given list.

### Key Idea

Given **n binary strings of length n**, we can create a new binary string
by flipping the diagonal bits.

For each index `i`:

- If `nums[i][i] == '0'` → put `'1'`
- If `nums[i][i] == '1'` → put `'0'`

This guarantees that the constructed string differs from:

- `nums[0]` at index `0`
- `nums[1]` at index `1`
- `nums[2]` at index `2`
- ...
- `nums[n-1]` at index `n-1`

Therefore, the constructed string **cannot be equal to any string in the list**.

### Time Complexity
O(n)

### Example Problem

- LeetCode 1980 — Find Unique Binary String

---

# Notes
Over time this folder will grow into a **complete mathematics reference
for algorithmic problem solving**.
