# Brian Kernighan Algorithm

## Overview

Brian Kernighan’s Algorithm is used to count the number of **set bits (1s)** in the binary representation of a number.

It is much faster than checking every bit one by one because it removes the **rightmost set bit** in each iteration.

This algorithm is widely used in:
- Bit Manipulation problems
- Competitive Programming
- Low-level optimizations
- Interview questions

---

## Intuition

A number `n` can remove its last set bit using:

```cpp
n = n & (n - 1)
```

Why does this work?

- `n - 1` flips:
  - the rightmost `1` bit to `0`
  - all bits after it to `1`
- Performing `AND` with original `n` removes that rightmost set bit.

So each operation removes exactly one `1`.

---

## Algorithm Logic

Repeat until `n` becomes `0`:

```cpp
n = n & (n - 1)
count++
```

The number of iterations equals the number of set bits.

---

## Basic Structure (C++)

```cpp
int countSetBits(int n) {
    int count = 0;

    while(n) {
        n = n & (n - 1);
        count++;
    }

    return count;
}
```

---

## Example

### Input

```cpp
n = 13
```

### Binary Representation

```cpp
13 = 1101
```

### Iterations

```cpp
1101 → 1100
1100 → 1000
1000 → 0000
```

Total operations = `3`

### Output

```cpp
3
```

---

## Dry Run

| Iteration | n (Binary) | Operation |
|---|---|---|
| 1 | 1101 | 1101 & 1100 = 1100 |
| 2 | 1100 | 1100 & 1011 = 1000 |
| 3 | 1000 | 1000 & 0111 = 0000 |

Count = `3`

---

## When to Use Brian Kernighan Algorithm

Use this algorithm when:

- You need to count set bits efficiently
- The number may have very few set bits
- Bit manipulation optimization is required
- Solving XOR / subset / mask problems

---

## Common Applications

1. **Counting Set Bits**
2. **Checking Power of Two**
   ```cpp
   n > 0 && (n & (n - 1)) == 0
   ```
3. **Bitmask Problems**
4. **Subset Generation**
5. **Hamming Distance Problems**

---

## Variations

### Count Set Bits in All Numbers from `1` to `N`
Use DP or bit manipulation tricks.

### Remove Lowest Set Bit

```cpp
n = n & (n - 1)
```

### Get Lowest Set Bit

```cpp
n & (-n)
```

---

## Edge Cases

- `n = 0` → answer is `0`
- Large integers
- Negative numbers (depends on representation)

---

## Complexity

- Time Complexity: O(Number of Set Bits)
- Worst Case: O(log N)
- Space Complexity: O(1)

---

## Key Takeaway

Brian Kernighan’s Algorithm works on the idea:

> Every operation removes the rightmost set bit from the number.

This makes it extremely efficient for bit manipulation problems.
