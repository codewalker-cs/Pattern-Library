# Two Pointer Pattern

## 📌 Overview
The Two Pointer pattern is a technique where we use **two indices (pointers)** to traverse a data structure efficiently.

Instead of using nested loops, we move pointers intelligently to reduce time complexity — often from **O(n²)** to **O(n)**.

This pattern is extremely common in:
- Arrays
- Strings
- Linked Lists
- Sorted data

---

# 🧠 Core Idea

Use two pointers that move according to some condition.

Common setups:

- One pointer at the start, one at the end
- Both pointers moving forward
- Fast & slow pointers
- Left & right boundaries

Example:

```text
[left ........ right]
```

We move pointers strategically instead of checking every pair manually.

---

# 🚀 When to Use Two Pointers

Use this pattern when:

- Array/string is sorted
- Need pairs/triplets
- Searching for a target sum
- Reversing elements
- Removing duplicates
- Comparing elements from both ends
- Detecting cycles
- Problems mention:
  - "pair"
  - "sorted"
  - "in-place"
  - "remove duplicates"
  - "palindrome"

---

# 🔁 Types of Two Pointer Techniques

## 1. Opposite Direction Pointers

One pointer starts from left, another from right.

Used mostly in sorted arrays.

### Example Problems
- Two Sum II
- Container With Most Water
- Valid Palindrome

```cpp
int left = 0, right = n - 1;

while(left < right) {

    if(condition satisfied)
        return answer;

    else if(need bigger value)
        left++;

    else
        right--;
}
```

---

## 2. Same Direction Pointers

Both pointers move forward.

Usually:
- one pointer explores
- one pointer maintains valid position

### Example Problems
- Remove duplicates
- Move zeroes

```cpp
int i = 0;

for(int j = 0; j < n; j++) {

    if(valid element) {
        swap(arr[i], arr[j]);
        i++;
    }
}
```

---

## 3. Fast & Slow Pointer

One pointer moves faster than the other.

Mostly used in linked lists.

### Example Problems
- Detect cycle
- Find middle node
- Happy number

```text
slow -> 1 step
fast -> 2 steps
```

If fast meets slow → cycle exists.

---

# ⏱ Complexity Benefit

| Approach | Time Complexity |
|----------|----------------|
| Brute Force | O(n²) |
| Two Pointer | O(n) |

We avoid unnecessary repeated comparisons.

---

# ✅ Basic Templates

## Opposite Direction Template

```cpp
int left = 0, right = n - 1;

while(left < right) {

    int sum = arr[left] + arr[right];

    if(sum == target) {
        // found answer
        break;
    }
    else if(sum < target)
        left++;

    else
        right--;
}
```

---

## Same Direction Template

```cpp
int i = 0;

for(int j = 0; j < n; j++) {

    if(condition true) {
        swap(arr[i], arr[j]);
        i++;
    }
}
```

---

## Fast & Slow Template

```cpp
ListNode* slow = head;
ListNode* fast = head;

while(fast && fast->next) {

    slow = slow->next;
    fast = fast->next->next;
}
```

At the end:
- `slow` → middle node

---

# 🧩 Classic Problems

## Opposite Direction
- Two Sum II
- Container With Most Water
- Valid Palindrome
- 3Sum

## Same Direction
- Remove Duplicates from Sorted Array
- Move Zeroes
- Sort Colors

## Fast & Slow
- Linked List Cycle
- Middle of Linked List
- Happy Number

---

# ⚠️ Common Mistakes

## Forgetting sorted requirement
Many two-pointer solutions work only on sorted arrays.

---

## Infinite loops

Always ensure pointers move.

### Bad Example

```cpp
while(left < right) {
    // forgot to move pointers
}
```

---

## Out of bounds

Carefully check:

```cpp
fast && fast->next
```

---

# 🎯 Key Takeaway

Two Pointers =  
Use pointer movement intelligently instead of checking all combinations.

The pattern helps:
- reduce nested loops
- optimize space
- solve array/string problems efficiently

---

# ⭐ Final Intuition

Think of two pointers as:
- two people searching from different sides
- one fast scout + one slow tracker
- one writer + one reader

Instead of restarting work repeatedly, pointers continue from where previous work ended.

Master Two Pointers → many medium-level interview problems become simple.
