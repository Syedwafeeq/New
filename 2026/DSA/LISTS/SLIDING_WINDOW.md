# Sliding Window Technique

## What is Sliding Window?

The Sliding Window Technique is an optimization method used to solve problems involving:

- Arrays
- Strings
- Contiguous subarrays/substrings

Instead of recalculating values for every subarray using nested loops, we maintain a window that slides through the data structure and updates results efficiently.

This often reduces complexity from:

- `O(n²)` → `O(n)`

---

# Core Idea

A window represents a continuous portion of the array or string.

Instead of rebuilding the window every time:
- Add the new element entering the window
- Remove the old element leaving the window

This avoids unnecessary repeated calculations.

---

# Types of Sliding Window

# 1. Fixed Size Sliding Window

The size of the window remains constant.

## Example Problem

Find the maximum sum of any subarray of size `k`.

---

## Brute Force Approach

```python
def max_sum_bruteforce(arr, k):
    n = len(arr)
    max_sum = 0

    for i in range(n - k + 1):
        current_sum = 0

        for j in range(i, i + k):
            current_sum += arr[j]

        max_sum = max(max_sum, current_sum)

    return max_sum


arr = [2, 1, 5, 1, 3, 2]
k = 3

print(max_sum_bruteforce(arr, k))
```

### Time Complexity

```text
O(n × k)
```

---

## Optimized Sliding Window Approach

```python
def max_sum_sliding_window(arr, k):
    n = len(arr)

    # First window sum
    window_sum = sum(arr[:k])
    max_sum = window_sum

    # Slide the window
    for i in range(k, n):
        window_sum += arr[i] - arr[i - k]
        max_sum = max(max_sum, window_sum)

    return max_sum


arr = [2, 1, 5, 1, 3, 2]
k = 3

print(max_sum_sliding_window(arr, k))
```

### Time Complexity

```text
O(n)
```

---

# 2. Variable Size Sliding Window

The window size changes dynamically based on conditions.

---

## Example Problem

Find the length of the longest substring without repeating characters.

---

## Python Solution

```python
def longest_unique_substring(s):
    left = 0
    seen = set()
    max_length = 0

    for right in range(len(s)):

        while s[right] in seen:
            seen.remove(s[left])
            left += 1

        seen.add(s[right])
        max_length = max(max_length, right - left + 1)

    return max_length


s = "abcabcbb"

print(longest_unique_substring(s))
```

### Time Complexity

```text
O(n)
```

---

# General Sliding Window Templates

## Fixed Window Template

```python
window_sum = sum(arr[:k])

for i in range(k, len(arr)):
    window_sum += arr[i]
    window_sum -= arr[i - k]
```

---

## Variable Window Template

```python
left = 0

for right in range(len(arr)):

    # Expand window

    while condition_breaks:
        # Shrink window
        left += 1

    # Update answer
```

---

# How to Identify Sliding Window Problems

A problem likely uses sliding window if:

- It involves:
  - Subarrays
  - Substrings
  - Contiguous elements

- The question asks for:
  - Maximum/minimum
  - Longest/shortest
  - Count/frequency
  - Target sum

- Brute force requires nested loops

---

# Common Sliding Window Problems

## Fixed Size Window

- Maximum sum subarray of size K
- First negative integer in every window
- Count distinct elements in every window

---

## Variable Size Window

- Longest substring without repeating characters
- Minimum window substring
- Longest subarray with given sum
- Fruits into baskets
- Permutation in string

---

# Why Sliding Window is Powerful

## Advantages

- Efficient
- Reduces redundant work
- Suitable for large inputs
- Frequently used in coding interviews

---

# Complexity Comparison

| Approach | Time Complexity |
|---|---|
| Brute Force | O(n²) / O(n³) |
| Sliding Window | O(n) |

---

# Important Concepts Used with Sliding Window

## 1. Two Pointers

Most sliding window problems use:
- `left` pointer
- `right` pointer

---

## 2. HashMap / Set

Useful for:
- Frequency counting
- Duplicate checking
- Character tracking

---

## 3. Dynamic Window Adjustment

Expand or shrink the window depending on constraints.

---

# Dry Run Example

## Problem

Find maximum sum subarray of size `3`.

```python
arr = [2, 1, 5, 1, 3, 2]
k = 3
```

---

## Step 1: First Window

```text
[2, 1, 5] → Sum = 8
```

---

## Step 2: Slide Window

Remove `2`, add `1`

```text
[1, 5, 1] → Sum = 7
```

Remove `1`, add `3`

```text
[5, 1, 3] → Sum = 9
```

Remove `5`, add `2`

```text
[1, 3, 2] → Sum = 6
```

---

# Real-World Applications

- Network packet analysis
- Streaming data
- Time-series analysis
- Real-time monitoring
- Pattern matching
- CPU scheduling

---

# Summary

The Sliding Window Technique is one of the most important DSA patterns used to optimize problems involving contiguous data.

It works by:
- Maintaining a moving window
- Updating values incrementally
- Avoiding repeated calculations
