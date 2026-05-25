# Recursion - Take / Not Take Model

## Definition

The **Take / Not Take** model is a recursion pattern where for every element we make two decisions:

1. Take the element
2. Do not take the element

This helps us generate all possible combinations, subsequences, or subsets.

---

# What is Take / Not Take?

For every element in an array or string:

```text
Take it
OR
Skip it
```

Both choices are explored using recursion.

Example:

```python
arr = [1, 2]
```

Possible choices:

```text
[]
[1]
[2]
[1, 2]
```

---

# When to Use

Use this pattern when problems involve:

- Subsequences
- Subsets
- Combination generation
- Pick / Not Pick decisions
- Backtracking problems

---

# Why to Use

This pattern helps us:

- Explore every possible choice
- Generate all answers
- Solve brute force recursive problems
- Build the foundation for backtracking

---

# How to Use

## General Template

```python
def generate(index, curr):

    if index == len(arr):
        print(curr)
        return

    # Not Take
    generate(index + 1, curr)

    # Take
    curr.append(arr[index])

    generate(index + 1, curr)

    curr.pop()
```

---

# How It Works

For every element:

```text
1. Ignore the element
2. Include the element
```

The recursion continues until:

```python
index == len(arr)
```

which means all elements are processed.

---

# Example 1 - Generate All Subsequences

## Problem

Generate all subsequences of a string.

---

## Solution

```python
s = "abc"

result = []

def generate(index, curr):

    if index == len(s):
        result.append(curr)
        return

    # Not Take
    generate(index + 1, curr)

    # Take
    generate(index + 1, curr + s[index])

generate(0, "")

print(result)
```

---

## Output

```python
['', 'c', 'b', 'bc', 'a', 'ac', 'ab', 'abc']
```

---

# Example 2 - Generate All Subsets

## Problem

Generate all subsets of an array.

---

## Solution

```python
nums = [1, 2, 3]

result = []

def generate(index, curr):

    if index == len(nums):
        result.append(curr.copy())
        return

    # Not Take
    generate(index + 1, curr)

    # Take
    curr.append(nums[index])

    generate(index + 1, curr)

    curr.pop()

generate(0, [])

print(result)
```

---

## Output

```python
[[], [3], [2], [2, 3], [1], [1, 3], [1, 2], [1, 2, 3]]
```

---

# Example 3 - Subsequence Sum Equals Target

## Problem

Find all subsequences whose sum equals target.

---

## Solution

```python
nums = [1, 2, 3]

target = 3

result = []

def generate(index, curr):

    if index == len(nums):

        if sum(curr) == target:
            result.append(curr.copy())

        return

    # Not Take
    generate(index + 1, curr)

    # Take
    curr.append(nums[index])

    generate(index + 1, curr)

    curr.pop()

generate(0, [])

print(result)
```

---

## Output

```python
[[3], [1, 2]]
```

---

# Important Notes

## Why `curr.pop()`?

```python
curr.pop()
```

is used for backtracking.

After recursion returns, it removes the last added element so the next recursive call starts correctly.

---

## Why `index == len(arr)`?

This is the base case.

It means:

```text
All elements are processed
```

So recursion stops there.

---

# Time Complexity

```text
O(2^N)
```

because every element has two choices:

```text
Take
Not Take
```

---

# Key Takeaway

The Take / Not Take model is about making decisions recursively.

For every element:

```text
Choose it
OR
Skip it
```

This pattern is one of the most important recursion and backtracking techniques in DSA.
