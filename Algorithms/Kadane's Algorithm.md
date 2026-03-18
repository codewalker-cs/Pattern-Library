# Kadane's Algorithm

## Overview

Kadane's Algorithm is used to find the **maximum sum of a contiguous subarray** within a given array of integers.

It is one of the most important algorithms in dynamic programming and is widely used in coding interviews and competitive programming.

---

## Intuition

At every index, we decide:

- Either **start a new subarray** from the current element
- Or **extend the previous subarray**

We always keep track of:
- Current subarray sum
- Maximum sum found so far

  ---

## Algorithm Logic

For each element `arr[i]`:
current_sum = max(arr[i], current_sum + arr[i])
max_sum = max(max_sum, current_sum)

---

## Basic Structure (C++)

```cpp
int kadane(vector<int>& arr) {
    int current_sum = arr[0];
    int max_sum = arr[0];

    for(int i = 1; i < arr.size(); i++) {
        current_sum = max(arr[i], current_sum + arr[i]);
        max_sum = max(max_sum, current_sum);
    }

    return max_sum;
}
```

---

## Example

**Input:**
arr = [-2,1,-3,4,-1,2,1,-5,4]
**Output:**
6
**Explanation:**
Subarray `[4, -1, 2, 1]` has the maximum sum.

---

## When to Use Kadane's Algorithm

Use Kadane when:

- You are asked for **maximum subarray sum**
- The subarray must be **contiguous**
- You need an **O(N)** solution
- The array may contain **negative numbers**

---

## Variations

1. **Minimum Subarray Sum**
   - Replace `max` with `min`
2. **Maximum Circular Subarray Sum**
   - Combine Kadane with total sum trick
3. **Maximum Product Subarray**
   - Track both max and min products
4. **Print the Subarray**
   - Track start and end indices
  
---

## Edge Cases

- All elements negative → return the largest element
- Single element array
- Large input size (ensure O(N))

---

## Complexity

- Time Complexity: O(N)
- Space Complexity: O(1)

---

## Key Takeaway

Kadane's Algorithm is based on:

> At each step, choose whether to extend the current subarray or start fresh.
