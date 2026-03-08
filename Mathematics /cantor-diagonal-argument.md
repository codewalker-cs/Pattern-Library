# Cantor's Diagonal Argument

## 1. Mathematical Explanation

Cantor's Diagonal Argument is a proof technique introduced by the mathematician **Georg Cantor** in set theory. It is fundamental in establishing that some infinite sets are "larger" than others.

The most famous application of this argument is proving that the set of **real numbers** is **uncountable**, meaning they cannot be mapped one-to-one with the natural numbers ($1, 2, 3, \dots$).

### The Proof Idea

Assume for the sake of contradiction that we *can* list all real numbers between 0 and 1. The list might look like this:

1. $\rightarrow 0.\mathbf{a_{11}} a_{12} a_{13} a_{14} \dots$
2. $\rightarrow 0.a_{21} \mathbf{a_{22}} a_{23} a_{24} \dots$
3. $\rightarrow 0.a_{31} a_{32} \mathbf{a_{33}} a_{34} \dots$
4. $\rightarrow 0.a_{41} a_{42} a_{43} \mathbf{a_{44}} \dots$
   $\dots$

Now, focus on the **diagonal digits** ($a_{11}, a_{22}, a_{33}, \dots$). We construct a new number by changing every digit along this diagonal.

**Construction Rule:**
For the $i$-th digit of our new number $b$:
- If $a_{ii} = 5$, set $b_i = 4$
- Otherwise, set $b_i = 5$

This creates a new number:
$$B = 0.b_{1} b_{2} b_{3} b_{4} \dots$$

Where:
- $b_1 \neq a_{11}$
- $b_2 \neq a_{22}$
- $b_3 \neq a_{33}$
- ...and so on.

### Why This Works
The constructed number $B$ differs from:
- The **1st** number in the list at the **1st** digit.
- The **2nd** number in the list at the **2nd** digit.
- The **$n$-th** number in the list at the **$n$-th** digit.

Therefore, **$B$ cannot be equal to any number in the list.** This contradicts the assumption that our list contained *all* real numbers. Thus, the real numbers are uncountably infinite.

---

## 2. Core Idea of the Technique

If we have a list of elements:
$x_0, x_1, x_2, \dots, x_{n-1}$

We can construct a new element that differs from every element $x_i$ specifically at position $i$. By ensuring a difference at just one position for every item, the new element is guaranteed to be unique.

This specific method of generating a counter-example is called **diagonalization**.

---

## 3. Application in Algorithms

In computer science and competitive programming, Cantor's diagonal argument is used when:
1. We have **$n$ elements**.
2. Each element has **length $n$**.
3. We need to construct a new element **not present in the list**.

By modifying the **diagonal positions** (element $i$ at index $i$), we guarantee the result is unique.

### LeetCode Example: 1980. Find Unique Binary String
**Problem:** Given an array of strings `nums` containing $n$ unique binary strings each of length $n$, return a binary string of length $n$ that does not appear in `nums`.

### Solution Logic
We don't need to check every possible string. We just need to ensure our result string `ans`:
- Differs from `nums[0]` at index `0`.
- Differs from `nums[1]` at index `1`.
- Differs from `nums[i]` at index `i`.

### C++ Implementation

```cpp
string constructDifferentString(vector<string>& nums) {
    int n = nums.size();
    string ans = "";

    for(int i = 0; i < n; i++) {
        // Diagonal Strategy:
        // If the character at the diagonal (nums[i][i]) is '0', pick '1'.
        // If it is '1', pick '0'.
        if(nums[i][i] == '0') {
            ans += '1';
        } else {
            ans += '0';
        }
    }

    return ans;
}
```

### Key Takeaway

Cantor’s diagonal argument teaches us that to create something unique, we don't need to compare against everything fully. We only need to differ from the $i$-th item at the $i$-th specific feature.
