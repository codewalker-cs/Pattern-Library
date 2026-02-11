# Sliding Window Pattern

## 📌 Overview
The Sliding Window pattern is a technique used to efficiently process a range (window) of elements in an array or string.  
Instead of recalculating values for every subarray from scratch, we reuse previous computations while moving the window.

This reduces time complexity from **O(n²)** to **O(n)** in many problems.

---

## 🧠 Core Idea
Maintain a window defined by two pointers:

left → start of window  
right → end of window  

Expand or shrink the window depending on the condition of the problem.

```
[left ... right]
```

We slide the window across the array while updating only what changes.

---

## 🚀 When to Use Sliding Window
Use this pattern when:

- Working with **subarrays / substrings**
- Looking for **maximum / minimum length**
- Maintaining a **running sum**
- Tracking **frequency of characters**
- Problems say:
  - "longest"
  - "shortest"
  - "at most k"
  - "exactly k"
  - "contiguous segment"

---

## 🔁 Types of Sliding Window

### 1. Fixed Size Window
Window size stays constant.

Example:
- Maximum sum of subarray of size k

```
window_sum += arr[right]
window_sum -= arr[left]
```

---

### 2. Variable Size Window
Window expands and shrinks dynamically.

Example:
- Longest substring without repeating characters
- Smallest subarray with sum ≥ target

```
while (condition breaks)
    shrink window from left
```

---

## ⏱ Complexity Benefit

| Approach | Time Complexity |
|----------|----------------|
Brute Force | O(n²) |
Sliding Window | O(n) |

We avoid recomputing entire ranges.

---

## ✅ Basic Template

### Fixed Window Template

```cpp
int windowSum = 0;
for(int i = 0; i < k; i++)
    windowSum += arr[i];

for(int i = k; i < n; i++) {
    windowSum += arr[i];
    windowSum -= arr[i-k];
}
```

---

### Variable Window Template

```cpp
int left = 0;
for(int right = 0; right < n; right++) {

    // expand window

    while(condition not valid) {
        // shrink window
        left++;
    }

    // update answer
}
```

---

## 🧩 Classic Problems

- Maximum sum subarray of size k
- Longest substring without repeating characters
- Minimum window substring
- Fruit into baskets
- Subarray sum equals k
- Longest repeating character replacement

---

## 🎯 Key Takeaway

Sliding window = reuse work instead of recomputing.

You move the window one step at a time and update only what changed.

This pattern is essential for interviews and competitive programming.

---

⭐ Master sliding window → solve many array & string problems efficiently.
