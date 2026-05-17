# Data Structures and Algorithms in Python: Complete A to Z Notes

> These notes are written for GitHub upload.

---

## Table of Contents

1. [What is DSA?](#1-what-is-dsa)
2. [Why DSA Matters](#2-why-dsa-matters)
3. [Python Basics Needed for DSA](#3-python-basics-needed-for-dsa)
4. [Time and Space Complexity](#4-time-and-space-complexity)
5. [Big O, Big Omega, and Big Theta](#5-big-o-big-omega-and-big-theta)
6. [Arrays and Lists](#6-arrays-and-lists)
7. [Strings](#7-strings)
8. [Linked Lists](#8-linked-lists)
9. [Stacks](#9-stacks)
10. [Queues and Deques](#10-queues-and-deques)
11. [Hashing, Dictionaries, and Sets](#11-hashing-dictionaries-and-sets)
12. [Recursion](#12-recursion)
13. [Backtracking](#13-backtracking)
14. [Searching Algorithms](#14-searching-algorithms)
15. [Sorting Algorithms](#15-sorting-algorithms)
16. [Two Pointers](#16-two-pointers)
17. [Sliding Window](#17-sliding-window)
18. [Prefix Sum and Difference Array](#18-prefix-sum-and-difference-array)
19. [Bit Manipulation](#19-bit-manipulation)
20. [Trees](#20-trees)
21. [Binary Trees](#21-binary-trees)
22. [Binary Search Trees](#22-binary-search-trees)
23. [Heaps and Priority Queues](#23-heaps-and-priority-queues)
24. [Tries](#24-tries)
25. [Graphs](#25-graphs)
26. [Graph Traversal: BFS and DFS](#26-graph-traversal-bfs-and-dfs)
27. [Shortest Path Algorithms](#27-shortest-path-algorithms)
28. [Minimum Spanning Tree](#28-minimum-spanning-tree)
29. [Topological Sorting](#29-topological-sorting)
30. [Union Find / Disjoint Set Union](#30-union-find--disjoint-set-union)
31. [Greedy Algorithms](#31-greedy-algorithms)
32. [Dynamic Programming](#32-dynamic-programming)
33. [Common DP Patterns](#33-common-dp-patterns)
34. [Advanced Data Structures](#34-advanced-data-structures)
35. [Algorithmic Problem-Solving Strategy](#35-algorithmic-problem-solving-strategy)
36. [Python DSA Cheat Sheet](#36-python-dsa-cheat-sheet)
37. [Common Mistakes Beginners Make](#37-common-mistakes-beginners-make)
38. [Practice Roadmap](#38-practice-roadmap)
39. [Final Revision Checklist](#39-final-revision-checklist)

---

# 1. What is DSA?

DSA stands for **Data Structures and Algorithms**.

A **data structure** is a way to store and organize data so that we can use it efficiently.

An **algorithm** is a step-by-step method to solve a problem.

Think of data structures as containers and algorithms as instructions. If data is your raw material, then DSA is the machinery that helps you process it without burning the whole factory down.

Example:

If you want to store a list of student marks, you can use an array/list.

```python
marks = [80, 95, 67, 88]
```

If you want to find the highest mark, you use an algorithm:

```python
marks = [80, 95, 67, 88]

highest = marks[0]
for mark in marks:
    if mark > highest:
        highest = mark

print(highest)
```

Output:

```text
95
```

The list is the data structure. The loop that finds the highest value is the algorithm.

---

# 2. Why DSA Matters

DSA matters because real-world software is not only about writing code that works. It is about writing code that works efficiently.

A slow program can feel broken even if it gives the correct answer.

Suppose you have 10 numbers. A bad algorithm may still work fine. But if you have 10 million numbers, the same bad algorithm may become painfully slow.

DSA helps you answer questions like:

* How fast is my code?
* How much memory does it use?
* Can it handle large input?
* Which data structure should I use?
* Can I reduce nested loops?
* Can I avoid repeated work?

DSA is important for:

* Coding interviews
* Competitive programming
* Backend development
* Databases
* Operating systems
* Search engines
* AI and machine learning systems
* Real-world scalable applications

---

# 3. Python Basics Needed for DSA

Before learning DSA in Python, you should be comfortable with these basics.

## Variables

```python
x = 10
name = "Tanush"
```

## Conditions

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

## Loops

```python
for i in range(5):
    print(i)
```

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

## Functions

```python
def add(a, b):
    return a + b

print(add(3, 4))
```

## Lists

```python
nums = [1, 2, 3, 4]
nums.append(5)
print(nums)
```

## Dictionaries

```python
student = {
    "name": "Aman",
    "age": 20
}

print(student["name"])
```

## Sets

```python
unique_numbers = {1, 2, 3, 3, 4}
print(unique_numbers)
```

Output:

```text
{1, 2, 3, 4}
```

## Tuples

```python
point = (2, 3)
print(point[0])
```

## List Comprehension

```python
squares = [x * x for x in range(5)]
print(squares)
```

Output:

```text
[0, 1, 4, 9, 16]
```

---

# 4. Time and Space Complexity

When we write code, we care about two major things:

1. **Time complexity**: How much time the algorithm takes as input grows.
2. **Space complexity**: How much extra memory the algorithm uses as input grows.

We do not usually measure exact seconds because different computers have different speeds. Instead, we measure growth.

If input size is `n`, we ask:

> What happens when `n` becomes very large?

## Example 1: Constant Time

```python
def get_first(arr):
    return arr[0]
```

This always takes one step, no matter how large the array is.

Time complexity: `O(1)`

## Example 2: Linear Time

```python
def print_all(arr):
    for item in arr:
        print(item)
```

If the array has 10 elements, the loop runs 10 times. If it has 1,000 elements, the loop runs 1,000 times.

Time complexity: `O(n)`

## Example 3: Quadratic Time

```python
def print_pairs(arr):
    for i in arr:
        for j in arr:
            print(i, j)
```

If there are `n` elements, the outer loop runs `n` times and the inner loop also runs `n` times.

Total operations: `n * n = n²`

Time complexity: `O(n²)`

---

# 5. Big O, Big Omega, and Big Theta

## Big O

Big O describes the **upper bound** of an algorithm. It tells us the worst-case growth.

Example:

```python
def search(arr, target):
    for item in arr:
        if item == target:
            return True
    return False
```

Worst case: target is at the end or not present.

Time complexity: `O(n)`

## Big Omega

Big Omega describes the **lower bound**. It tells us the best-case growth.

For the same search example, best case is when the target is the first element.

Best-case complexity: `Ω(1)`

## Big Theta

Big Theta describes a tight bound. It means the algorithm grows at the same rate in best, average, and worst cases.

Example:

```python
def print_all(arr):
    for item in arr:
        print(item)
```

This always prints all elements.

Complexity: `Θ(n)`

## Common Complexities

| Complexity | Name         | Example                 |
| ---------- | ------------ | ----------------------- |
| O(1)       | Constant     | Accessing array element |
| O(log n)   | Logarithmic  | Binary search           |
| O(n)       | Linear       | Loop through array      |
| O(n log n) | Linearithmic | Merge sort              |
| O(n²)      | Quadratic    | Nested loops            |
| O(2ⁿ)      | Exponential  | Recursive subsets       |
| O(n!)      | Factorial    | Permutations            |

---

# 6. Arrays and Lists

In Python, the most commonly used array-like structure is the **list**.

```python
nums = [10, 20, 30, 40]
```

A list stores elements in order. Each element has an index.

```python
nums = [10, 20, 30, 40]
print(nums[0])
print(nums[2])
```

Output:

```text
10
30
```

## Common List Operations

```python
nums = [1, 2, 3]

nums.append(4)        # Add at end
nums.insert(1, 10)    # Insert at index 1
nums.pop()            # Remove last element
nums.remove(10)       # Remove value 10
```

## Time Complexity of List Operations

| Operation             | Complexity   |
| --------------------- | ------------ |
| Access by index       | O(1)         |
| Append at end         | O(1) average |
| Insert at beginning   | O(n)         |
| Delete from beginning | O(n)         |
| Search by value       | O(n)         |

## Why Insert at Beginning is O(n)

If you insert an element at the beginning, all existing elements need to shift one position to the right.

```python
nums = [2, 3, 4]
nums.insert(0, 1)
print(nums)
```

Output:

```text
[1, 2, 3, 4]
```

Behind the scenes, Python shifts elements. That shifting takes time.

## Common Array/List Problems

* Find maximum and minimum
* Reverse an array
* Rotate an array
* Remove duplicates
* Find missing number
* Find duplicate number
* Merge two sorted arrays
* Move zeroes to end
* Kadane's algorithm for maximum subarray sum

## Maximum Element

```python
def find_max(arr):
    maximum = arr[0]
    for num in arr:
        if num > maximum:
            maximum = num
    return maximum
```

Time complexity: `O(n)`

## Reverse a List

```python
def reverse_list(arr):
    left = 0
    right = len(arr) - 1

    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1

    return arr
```

Time complexity: `O(n)`

Space complexity: `O(1)`

## Kadane's Algorithm

Kadane's algorithm finds the maximum sum of a contiguous subarray.

```python
def max_subarray_sum(nums):
    current_sum = nums[0]
    max_sum = nums[0]

    for i in range(1, len(nums)):
        current_sum = max(nums[i], current_sum + nums[i])
        max_sum = max(max_sum, current_sum)

    return max_sum
```

Example:

```python
nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
print(max_subarray_sum(nums))
```

Output:

```text
6
```

The subarray is `[4, -1, 2, 1]`.

---

# 7. Strings

A string is a sequence of characters.

```python
s = "hello"
```

Strings in Python are **immutable**. This means once created, they cannot be changed directly.

```python
s = "hello"
# s[0] = "H"  # This gives an error
```

If you want to modify a string, you usually create a new string.

```python
s = "hello"
s = "H" + s[1:]
print(s)
```

Output:

```text
Hello
```

## Common String Operations

```python
s = "hello world"

print(len(s))
print(s.upper())
print(s.lower())
print(s.split())
print(s.replace("world", "Python"))
```

## String Reversal

```python
s = "hello"
print(s[::-1])
```

Output:

```text
olleh
```

## Palindrome Check

A palindrome reads the same forward and backward.

Examples:

* madam
* racecar
* level

```python
def is_palindrome(s):
    left = 0
    right = len(s) - 1

    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1

    return True
```

## Character Frequency

```python
from collections import Counter

s = "banana"
freq = Counter(s)
print(freq)
```

Output:

```text
Counter({'a': 3, 'n': 2, 'b': 1})
```

## Anagram Check

Two strings are anagrams if they contain the same characters with the same frequency.

```python
from collections import Counter

def is_anagram(s, t):
    return Counter(s) == Counter(t)
```

---

# 8. Linked Lists

A linked list is a linear data structure where elements are stored in nodes.

Each node contains:

1. Data
2. Reference to the next node

Unlike arrays, linked list elements are not stored continuously in memory.

## Node Structure

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

## Creating a Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

first = Node(10)
second = Node(20)
third = Node(30)

first.next = second
second.next = third
```

The linked list looks like:

```text
10 -> 20 -> 30 -> None
```

## Traversing a Linked List

```python
def print_list(head):
    current = head
    while current:
        print(current.data)
        current = current.next
```

## Insert at Beginning

```python
def insert_at_beginning(head, data):
    new_node = Node(data)
    new_node.next = head
    return new_node
```

## Insert at End

```python
def insert_at_end(head, data):
    new_node = Node(data)

    if head is None:
        return new_node

    current = head
    while current.next:
        current = current.next

    current.next = new_node
    return head
```

## Delete a Node by Value

```python
def delete_node(head, value):
    if head is None:
        return None

    if head.data == value:
        return head.next

    current = head
    while current.next and current.next.data != value:
        current = current.next

    if current.next:
        current.next = current.next.next

    return head
```

## Reverse a Linked List

```python
def reverse_linked_list(head):
    prev = None
    current = head

    while current:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node

    return prev
```

## Linked List Complexity

| Operation           | Complexity        |
| ------------------- | ----------------- |
| Access by index     | O(n)              |
| Search              | O(n)              |
| Insert at beginning | O(1)              |
| Insert at end       | O(n) without tail |
| Delete known node   | O(1)              |

---

# 9. Stacks

A stack follows **LIFO**.

LIFO means **Last In, First Out**.

The last element added is the first one removed.

Real-life example: a stack of plates. You put a plate on top and remove the top plate first.

## Stack Operations

* Push: Add element
* Pop: Remove top element
* Peek/Top: View top element
* Is Empty: Check if stack is empty

## Stack Using List

```python
stack = []

stack.append(10)
stack.append(20)
stack.append(30)

print(stack.pop())
print(stack[-1])
```

Output:

```text
30
20
```

## Valid Parentheses Problem

```python
def is_valid_parentheses(s):
    stack = []
    pairs = {
        ')': '(',
        '}': '{',
        ']': '['
    }

    for char in s:
        if char in pairs.values():
            stack.append(char)
        elif char in pairs:
            if not stack or stack[-1] != pairs[char]:
                return False
            stack.pop()

    return len(stack) == 0
```

## When to Use Stack

Use a stack when you need to process the most recent item first.

Common stack problems:

* Valid parentheses
* Undo/redo feature
* Browser history
* Next greater element
* Evaluate postfix expression
* Monotonic stack problems

---

# 10. Queues and Deques

A queue follows **FIFO**.

FIFO means **First In, First Out**.

The first element added is the first one removed.

Real-life example: people standing in a line.

## Queue Using deque

In Python, use `collections.deque` for efficient queue operations.

```python
from collections import deque

queue = deque()

queue.append(10)
queue.append(20)
queue.append(30)

print(queue.popleft())
print(queue.popleft())
```

Output:

```text
10
20
```

## Why Not Use List as Queue?

```python
queue = [1, 2, 3]
queue.pop(0)
```

`pop(0)` is `O(n)` because all elements shift left.

With `deque`, `popleft()` is `O(1)`.

## Deque

A deque means double-ended queue. You can insert and delete from both ends.

```python
from collections import deque

dq = deque()
dq.append(1)
dq.appendleft(0)
dq.append(2)

print(dq)
print(dq.pop())
print(dq.popleft())
```

---

# 11. Hashing, Dictionaries, and Sets

Hashing is a technique that maps data to a fixed-size value called a hash.

Python dictionaries and sets use hashing internally.

## Dictionary

A dictionary stores key-value pairs.

```python
student = {
    "name": "Aman",
    "age": 20
}

print(student["name"])
```

## Common Dictionary Operations

```python
freq = {}

for char in "banana":
    freq[char] = freq.get(char, 0) + 1

print(freq)
```

Output:

```text
{'b': 1, 'a': 3, 'n': 2}
```

## Set

A set stores unique values.

```python
nums = {1, 2, 3, 3, 4}
print(nums)
```

Output:

```text
{1, 2, 3, 4}
```

## Two Sum Problem

```python
def two_sum(nums, target):
    seen = {}

    for i, num in enumerate(nums):
        needed = target - num

        if needed in seen:
            return [seen[needed], i]

        seen[num] = i

    return []
```

Time complexity: `O(n)`

Space complexity: `O(n)`

## When to Use Hashing

Use hashing when you need fast lookup.

Common problems:

* Frequency count
* Detect duplicates
* Two sum
* Group anagrams
* Longest consecutive sequence
* Subarray sum equals k

---

# 12. Recursion

Recursion means a function calls itself.

A recursive function must have:

1. Base case
2. Recursive case

Without a base case, recursion never stops.

## Simple Recursion

```python
def countdown(n):
    if n == 0:
        return

    print(n)
    countdown(n - 1)
```

## Factorial

Factorial of `n`:

```text
n! = n * (n-1) * (n-2) * ... * 1
```

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1

    return n * factorial(n - 1)
```

## Fibonacci

```python
def fibonacci(n):
    if n == 0:
        return 0
    if n == 1:
        return 1

    return fibonacci(n - 1) + fibonacci(n - 2)
```

This simple Fibonacci is slow because it repeats work.

Time complexity: `O(2^n)`

Better Fibonacci using memoization:

```python
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]

    if n == 0:
        return 0
    if n == 1:
        return 1

    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]
```

## Recursion Call Stack

Every recursive call waits for the next call to finish. These waiting calls are stored in memory using the call stack.

If recursion goes too deep, Python may give a recursion depth error.

---

# 13. Backtracking

Backtracking is a problem-solving technique where we build a solution step by step. If a path does not work, we undo the last step and try another path.

Backtracking is basically controlled trial and error. Not chaotic trial and error. More like a disciplined detective with a notebook.

## General Backtracking Template

```python
def backtrack(path, choices):
    if goal_reached:
        result.append(path[:])
        return

    for choice in choices:
        if choice_is_valid:
            path.append(choice)
            backtrack(path, choices)
            path.pop()
```

## Subsets

```python
def subsets(nums):
    result = []

    def backtrack(index, path):
        if index == len(nums):
            result.append(path[:])
            return

        path.append(nums[index])
        backtrack(index + 1, path)

        path.pop()
        backtrack(index + 1, path)

    backtrack(0, [])
    return result
```

## Permutations

```python
def permutations(nums):
    result = []
    used = [False] * len(nums)

    def backtrack(path):
        if len(path) == len(nums):
            result.append(path[:])
            return

        for i in range(len(nums)):
            if used[i]:
                continue

            used[i] = True
            path.append(nums[i])

            backtrack(path)

            path.pop()
            used[i] = False

    backtrack([])
    return result
```

## Common Backtracking Problems

* Subsets
* Permutations
* Combinations
* N-Queens
* Sudoku solver
* Word search
* Generate parentheses

---

# 14. Searching Algorithms

Searching means finding an element in a collection.

## Linear Search

Linear search checks each element one by one.

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1
```

Time complexity: `O(n)`

## Binary Search

Binary search works on sorted arrays.

It repeatedly divides the search space into half.

```python
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1
```

Time complexity: `O(log n)`

## Binary Search on Answer

Sometimes binary search is not directly on an array. Instead, we binary search the answer.

Examples:

* Minimum eating speed
* Allocate books
* Ship packages within D days
* Find square root
* Aggressive cows

General idea:

```python
def can_do(x):
    pass

left = minimum_possible_answer
right = maximum_possible_answer

while left <= right:
    mid = (left + right) // 2

    if can_do(mid):
        answer = mid
        right = mid - 1
    else:
        left = mid + 1
```

---

# 15. Sorting Algorithms

Sorting means arranging data in order.

Usually ascending or descending.

## Bubble Sort

Bubble sort repeatedly compares adjacent elements and swaps them if they are in the wrong order.

```python
def bubble_sort(arr):
    n = len(arr)

    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]

    return arr
```

Time complexity: `O(n²)`

## Selection Sort

Selection sort repeatedly finds the minimum element and places it at the correct position.

```python
def selection_sort(arr):
    n = len(arr)

    for i in range(n):
        min_index = i

        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        arr[i], arr[min_index] = arr[min_index], arr[i]

    return arr
```

Time complexity: `O(n²)`

## Insertion Sort

Insertion sort builds the sorted array one element at a time.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1

        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key

    return arr
```

Time complexity: `O(n²)`

## Merge Sort

Merge sort uses divide and conquer.

It divides the array into halves, sorts both halves, and merges them.

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])

    return merge(left, right)


def merge(left, right):
    result = []
    i = 0
    j = 0

    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])

    return result
```

Time complexity: `O(n log n)`

Space complexity: `O(n)`

## Quick Sort

Quick sort chooses a pivot and partitions the array around it.

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]

    return quick_sort(left) + middle + quick_sort(right)
```

Average time complexity: `O(n log n)`

Worst-case time complexity: `O(n²)`

## Python Built-in Sorting

```python
nums = [3, 1, 4, 2]
nums.sort()
print(nums)
```

```python
nums = [3, 1, 4, 2]
sorted_nums = sorted(nums)
print(sorted_nums)
```

Python uses Timsort internally.

---

# 16. Two Pointers

Two pointers is a technique where we use two variables to move through data.

Usually, one pointer starts from the beginning and the other from the end.

## Reverse Array

```python
def reverse_array(arr):
    left = 0
    right = len(arr) - 1

    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1

    return arr
```

## Pair Sum in Sorted Array

```python
def pair_sum(arr, target):
    left = 0
    right = len(arr) - 1

    while left < right:
        current_sum = arr[left] + arr[right]

        if current_sum == target:
            return True
        elif current_sum < target:
            left += 1
        else:
            right -= 1

    return False
```

## When to Use Two Pointers

Use two pointers when:

* The array is sorted
* You need pairs
* You need to reverse something
* You need to compare from both ends
* You want to avoid nested loops

---

# 17. Sliding Window

Sliding window is used for problems involving subarrays or substrings.

Instead of recalculating every window from scratch, we slide the window and update the result.

## Fixed Size Window

Problem: Find maximum sum of subarray of size `k`.

```python
def max_sum_subarray(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum

    for i in range(k, len(nums)):
        window_sum += nums[i]
        window_sum -= nums[i - k]
        max_sum = max(max_sum, window_sum)

    return max_sum
```

Time complexity: `O(n)`

## Variable Size Window

Problem: Longest substring without repeating characters.

```python
def length_of_longest_substring(s):
    seen = set()
    left = 0
    max_length = 0

    for right in range(len(s)):
        while s[right] in seen:
            seen.remove(s[left])
            left += 1

        seen.add(s[right])
        max_length = max(max_length, right - left + 1)

    return max_length
```

## When to Use Sliding Window

Use sliding window when:

* Problem asks for subarray or substring
* You need maximum/minimum/longest/shortest
* Elements are contiguous
* Brute force uses nested loops over ranges

---

# 18. Prefix Sum and Difference Array

## Prefix Sum

Prefix sum stores cumulative sums.

```python
nums = [1, 2, 3, 4]
prefix = [0] * (len(nums) + 1)

for i in range(len(nums)):
    prefix[i + 1] = prefix[i] + nums[i]

print(prefix)
```

Output:

```text
[0, 1, 3, 6, 10]
```

To find sum from index `l` to `r`:

```python
range_sum = prefix[r + 1] - prefix[l]
```

## Subarray Sum Equals K

```python
def subarray_sum(nums, k):
    count = 0
    current_sum = 0
    prefix_count = {0: 1}

    for num in nums:
        current_sum += num
        needed = current_sum - k

        if needed in prefix_count:
            count += prefix_count[needed]

        prefix_count[current_sum] = prefix_count.get(current_sum, 0) + 1

    return count
```

## Difference Array

Difference array is useful for range updates.

Suppose you want to add a value to many ranges. Updating each element directly can be slow.

Difference array helps you update ranges in `O(1)` each.

```python
def range_update(n, updates):
    diff = [0] * (n + 1)

    for left, right, value in updates:
        diff[left] += value
        if right + 1 < n:
            diff[right + 1] -= value

    result = [0] * n
    current = 0

    for i in range(n):
        current += diff[i]
        result[i] = current

    return result
```

---

# 19. Bit Manipulation

Bit manipulation works directly with binary representation of numbers.

## Common Bit Operators

| Operator | Meaning     |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

## XOR Properties

```text
a ^ a = 0
a ^ 0 = a
```

## Find Single Number

Every number appears twice except one.

```python
def single_number(nums):
    result = 0

    for num in nums:
        result ^= num

    return result
```

## Check Even or Odd

```python
def is_even(n):
    return (n & 1) == 0
```

## Check if Power of Two

```python
def is_power_of_two(n):
    return n > 0 and (n & (n - 1)) == 0
```

---

# 20. Trees

A tree is a hierarchical data structure.

It contains nodes connected by edges.

Important terms:

* Root: Top node
* Parent: Node that has children
* Child: Node connected below another node
* Leaf: Node with no children
* Edge: Connection between nodes
* Height: Longest path from node to leaf
* Depth: Distance from root to node

---

# 21. Binary Trees

A binary tree is a tree where each node has at most two children.

```python
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None
```

## Tree Traversals

### Inorder Traversal

Left, Root, Right

```python
def inorder(root):
    if root is None:
        return

    inorder(root.left)
    print(root.val)
    inorder(root.right)
```

### Preorder Traversal

Root, Left, Right

```python
def preorder(root):
    if root is None:
        return

    print(root.val)
    preorder(root.left)
    preorder(root.right)
```

### Postorder Traversal

Left, Right, Root

```python
def postorder(root):
    if root is None:
        return

    postorder(root.left)
    postorder(root.right)
    print(root.val)
```

### Level Order Traversal

```python
from collections import deque

def level_order(root):
    if root is None:
        return []

    result = []
    queue = deque([root])

    while queue:
        node = queue.popleft()
        result.append(node.val)

        if node.left:
            queue.append(node.left)
        if node.right:
            queue.append(node.right)

    return result
```

---

# 22. Binary Search Trees

A Binary Search Tree, or BST, is a binary tree with this rule:

* Left subtree contains smaller values
* Right subtree contains larger values

## Search in BST

```python
def search_bst(root, target):
    if root is None:
        return False

    if root.val == target:
        return True
    elif target < root.val:
        return search_bst(root.left, target)
    else:
        return search_bst(root.right, target)
```

Average complexity: `O(log n)`

Worst case: `O(n)` if the tree becomes skewed.

## Insert in BST

```python
def insert_bst(root, value):
    if root is None:
        return TreeNode(value)

    if value < root.val:
        root.left = insert_bst(root.left, value)
    else:
        root.right = insert_bst(root.right, value)

    return root
```

---

# 23. Heaps and Priority Queues

A heap is a special tree-based data structure.

Python provides a min heap using the `heapq` module.

In a min heap, the smallest element is always at the top.

```python
import heapq

nums = [5, 2, 8, 1]
heapq.heapify(nums)

print(heapq.heappop(nums))
```

Output:

```text
1
```

## Push and Pop

```python
import heapq

heap = []
heapq.heappush(heap, 10)
heapq.heappush(heap, 5)
heapq.heappush(heap, 20)

print(heapq.heappop(heap))
```

Output:

```text
5
```

## Max Heap in Python

Python has min heap by default. For max heap, store negative values.

```python
import heapq

nums = [5, 2, 8, 1]
heap = []

for num in nums:
    heapq.heappush(heap, -num)

print(-heapq.heappop(heap))
```

Output:

```text
8
```

## Common Heap Problems

* K largest elements
* K smallest elements
* Merge k sorted lists
* Top k frequent elements
* Find median from data stream

---

# 24. Tries

A trie is a tree-like data structure used for storing strings.

It is useful for prefix-based searching.

Examples:

* Autocomplete
* Spell checker
* Dictionary search
* Prefix matching

## Trie Node

```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.is_end = False
```

## Trie Implementation

```python
class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        node = self.root

        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]

        node.is_end = True

    def search(self, word):
        node = self.root

        for char in word:
            if char not in node.children:
                return False
            node = node.children[char]

        return node.is_end

    def starts_with(self, prefix):
        node = self.root

        for char in prefix:
            if char not in node.children:
                return False
            node = node.children[char]

        return True
```

---

# 25. Graphs

A graph is a collection of nodes and edges.

Nodes are also called vertices.

Edges are connections between nodes.

Graphs are used everywhere:

* Maps
* Social networks
* Computer networks
* Recommendation systems
* Dependency systems

## Types of Graphs

### Undirected Graph

Edges have no direction.

If A is connected to B, then B is connected to A.

### Directed Graph

Edges have direction.

If A points to B, B does not necessarily point to A.

### Weighted Graph

Edges have weights or costs.

Example: distance between cities.

### Unweighted Graph

Edges do not have weights.

## Graph Representation

### Adjacency List

```python
graph = {
    0: [1, 2],
    1: [0, 3],
    2: [0],
    3: [1]
}
```

### Adjacency Matrix

```python
graph = [
    [0, 1, 1, 0],
    [1, 0, 0, 1],
    [1, 0, 0, 0],
    [0, 1, 0, 0]
]
```

Adjacency list is usually better for sparse graphs.

Adjacency matrix is useful when you need fast edge lookup.

---

# 26. Graph Traversal: BFS and DFS

## BFS

BFS stands for Breadth-First Search.

It explores level by level.

BFS uses a queue.

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    visited.add(start)

    while queue:
        node = queue.popleft()
        print(node)

        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

## DFS

DFS stands for Depth-First Search.

It goes deep before backtracking.

DFS can use recursion or stack.

### Recursive DFS

```python
def dfs(graph, node, visited=None):
    if visited is None:
        visited = set()

    visited.add(node)
    print(node)

    for neighbor in graph[node]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)
```

### Iterative DFS

```python
def dfs_iterative(graph, start):
    visited = set()
    stack = [start]

    while stack:
        node = stack.pop()

        if node not in visited:
            visited.add(node)
            print(node)

            for neighbor in graph[node]:
                if neighbor not in visited:
                    stack.append(neighbor)
```

## BFS vs DFS

| Feature        | BFS                               | DFS                          |
| -------------- | --------------------------------- | ---------------------------- |
| Data structure | Queue                             | Stack/Recursion              |
| Explores       | Level by level                    | Deep first                   |
| Good for       | Shortest path in unweighted graph | Connected components, cycles |
| Memory         | Can be high                       | Usually lower                |

---

# 27. Shortest Path Algorithms

## BFS for Unweighted Graph

If all edges have equal weight, BFS can find shortest path.

```python
from collections import deque

def shortest_path_unweighted(graph, start):
    distance = {start: 0}
    queue = deque([start])

    while queue:
        node = queue.popleft()

        for neighbor in graph[node]:
            if neighbor not in distance:
                distance[neighbor] = distance[node] + 1
                queue.append(neighbor)

    return distance
```

## Dijkstra's Algorithm

Dijkstra finds shortest paths in a weighted graph with non-negative weights.

```python
import heapq

def dijkstra(graph, start):
    distances = {node: float('inf') for node in graph}
    distances[start] = 0

    heap = [(0, start)]

    while heap:
        current_distance, node = heapq.heappop(heap)

        if current_distance > distances[node]:
            continue

        for neighbor, weight in graph[node]:
            distance = current_distance + weight

            if distance < distances[neighbor]:
                distances[neighbor] = distance
                heapq.heappush(heap, (distance, neighbor))

    return distances
```

## Bellman-Ford Algorithm

Bellman-Ford works even with negative weights, but it is slower.

It can also detect negative cycles.

```python
def bellman_ford(edges, n, start):
    distance = [float('inf')] * n
    distance[start] = 0

    for _ in range(n - 1):
        for u, v, w in edges:
            if distance[u] != float('inf') and distance[u] + w < distance[v]:
                distance[v] = distance[u] + w

    for u, v, w in edges:
        if distance[u] != float('inf') and distance[u] + w < distance[v]:
            return "Negative cycle detected"

    return distance
```

## Floyd-Warshall Algorithm

Floyd-Warshall finds shortest paths between all pairs of nodes.

```python
def floyd_warshall(graph):
    n = len(graph)
    dist = [row[:] for row in graph]

    for k in range(n):
        for i in range(n):
            for j in range(n):
                dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])

    return dist
```

Time complexity: `O(n³)`

---

# 28. Minimum Spanning Tree

A spanning tree connects all nodes in a graph without cycles.

A minimum spanning tree connects all nodes with minimum total edge weight.

MST works for connected, undirected, weighted graphs.

## Kruskal's Algorithm

Kruskal sorts edges by weight and picks the smallest edges without forming cycles.

It uses DSU.

```python
class DSU:
    def __init__(self, n):
        self.parent = list(range(n))
        self.rank = [0] * n

    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def union(self, x, y):
        root_x = self.find(x)
        root_y = self.find(y)

        if root_x == root_y:
            return False

        if self.rank[root_x] < self.rank[root_y]:
            self.parent[root_x] = root_y
        elif self.rank[root_x] > self.rank[root_y]:
            self.parent[root_y] = root_x
        else:
            self.parent[root_y] = root_x
            self.rank[root_x] += 1

        return True


def kruskal(n, edges):
    edges.sort(key=lambda x: x[2])
    dsu = DSU(n)
    mst_weight = 0

    for u, v, weight in edges:
        if dsu.union(u, v):
            mst_weight += weight

    return mst_weight
```

## Prim's Algorithm

Prim starts from one node and keeps adding the smallest edge that connects to a new node.

```python
import heapq

def prim(graph, start):
    visited = set()
    heap = [(0, start)]
    total_weight = 0

    while heap:
        weight, node = heapq.heappop(heap)

        if node in visited:
            continue

        visited.add(node)
        total_weight += weight

        for neighbor, edge_weight in graph[node]:
            if neighbor not in visited:
                heapq.heappush(heap, (edge_weight, neighbor))

    return total_weight
```

---

# 29. Topological Sorting

Topological sorting is used for directed acyclic graphs, also called DAGs.

It gives an order of nodes such that every dependency comes before the thing that depends on it.

Examples:

* Course schedule
* Build systems
* Task ordering
* Package installation

## Kahn's Algorithm

```python
from collections import deque

def topological_sort(n, edges):
    graph = [[] for _ in range(n)]
    indegree = [0] * n

    for u, v in edges:
        graph[u].append(v)
        indegree[v] += 1

    queue = deque()

    for i in range(n):
        if indegree[i] == 0:
            queue.append(i)

    order = []

    while queue:
        node = queue.popleft()
        order.append(node)

        for neighbor in graph[node]:
            indegree[neighbor] -= 1
            if indegree[neighbor] == 0:
                queue.append(neighbor)

    if len(order) != n:
        return []

    return order
```

---

# 30. Union Find / Disjoint Set Union

DSU is used to manage groups.

It supports two main operations:

1. Find: Find the representative of a group
2. Union: Merge two groups

```python
class DSU:
    def __init__(self, n):
        self.parent = list(range(n))
        self.size = [1] * n

    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def union(self, a, b):
        root_a = self.find(a)
        root_b = self.find(b)

        if root_a == root_b:
            return False

        if self.size[root_a] < self.size[root_b]:
            root_a, root_b = root_b, root_a

        self.parent[root_b] = root_a
        self.size[root_a] += self.size[root_b]

        return True
```

Common DSU problems:

* Detect cycle in undirected graph
* Number of connected components
* Kruskal's algorithm
* Accounts merge
* Redundant connection

---

# 31. Greedy Algorithms

A greedy algorithm makes the best choice at the current step.

It does not always work for every problem. It works only when local best choices lead to a global best answer.

## Activity Selection

Choose maximum number of non-overlapping activities.

```python
def activity_selection(activities):
    activities.sort(key=lambda x: x[1])

    count = 0
    last_end = float('-inf')

    for start, end in activities:
        if start >= last_end:
            count += 1
            last_end = end

    return count
```

## Coin Change Warning

Greedy works for some coin systems, but not all.

For coins `[1, 5, 10, 25]`, greedy works.

For coins `[1, 3, 4]` and amount `6`, greedy chooses `4 + 1 + 1`, which uses 3 coins. But optimal answer is `3 + 3`, which uses 2 coins.

So greedy is powerful, but it needs proof.

---

# 32. Dynamic Programming

Dynamic Programming, or DP, is used when a problem has:

1. Overlapping subproblems
2. Optimal substructure

## Overlapping Subproblems

The same smaller problems are solved again and again.

Example: Fibonacci.

## Optimal Substructure

The answer to the big problem can be built from answers to smaller problems.

## Memoization

Memoization means top-down DP. We use recursion and store results.

```python
def fib(n, memo={}):
    if n in memo:
        return memo[n]

    if n <= 1:
        return n

    memo[n] = fib(n - 1, memo) + fib(n - 2, memo)
    return memo[n]
```

## Tabulation

Tabulation means bottom-up DP. We build the answer iteratively.

```python
def fib(n):
    if n <= 1:
        return n

    dp = [0] * (n + 1)
    dp[1] = 1

    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]

    return dp[n]
```

## Space Optimized Fibonacci

```python
def fib(n):
    if n <= 1:
        return n

    prev2 = 0
    prev1 = 1

    for _ in range(2, n + 1):
        current = prev1 + prev2
        prev2 = prev1
        prev1 = current

    return prev1
```

---

# 33. Common DP Patterns

## 1D DP

Used when current answer depends on previous answers.

Example: Climbing stairs.

```python
def climb_stairs(n):
    if n <= 2:
        return n

    dp = [0] * (n + 1)
    dp[1] = 1
    dp[2] = 2

    for i in range(3, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]

    return dp[n]
```

## 2D DP

Used when there are two changing states.

Example: Longest common subsequence.

```python
def longest_common_subsequence(text1, text2):
    m = len(text1)
    n = len(text2)

    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if text1[i - 1] == text2[j - 1]:
                dp[i][j] = 1 + dp[i - 1][j - 1]
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

    return dp[m][n]
```

## Knapsack DP

0/1 knapsack means each item can be chosen once.

```python
def knapsack(weights, values, capacity):
    n = len(weights)
    dp = [[0] * (capacity + 1) for _ in range(n + 1)]

    for i in range(1, n + 1):
        for w in range(capacity + 1):
            if weights[i - 1] <= w:
                dp[i][w] = max(
                    dp[i - 1][w],
                    values[i - 1] + dp[i - 1][w - weights[i - 1]]
                )
            else:
                dp[i][w] = dp[i - 1][w]

    return dp[n][capacity]
```

## DP Problems to Practice

* Fibonacci
* Climbing stairs
* House robber
* Coin change
* Longest increasing subsequence
* Longest common subsequence
* Edit distance
* Unique paths
* Minimum path sum
* 0/1 knapsack

---

# 34. Advanced Data Structures

## Segment Tree

A segment tree is used for range queries and updates.

Example queries:

* Range sum
* Range minimum
* Range maximum

Basic range sum segment tree:

```python
class SegmentTree:
    def __init__(self, nums):
        self.n = len(nums)
        self.tree = [0] * (4 * self.n)
        self.build(nums, 0, 0, self.n - 1)

    def build(self, nums, node, start, end):
        if start == end:
            self.tree[node] = nums[start]
            return

        mid = (start + end) // 2
        self.build(nums, 2 * node + 1, start, mid)
        self.build(nums, 2 * node + 2, mid + 1, end)
        self.tree[node] = self.tree[2 * node + 1] + self.tree[2 * node + 2]

    def query(self, node, start, end, left, right):
        if right < start or end < left:
            return 0

        if left <= start and end <= right:
            return self.tree[node]

        mid = (start + end) // 2
        left_sum = self.query(2 * node + 1, start, mid, left, right)
        right_sum = self.query(2 * node + 2, mid + 1, end, left, right)

        return left_sum + right_sum

    def update(self, node, start, end, index, value):
        if start == end:
            self.tree[node] = value
            return

        mid = (start + end) // 2
        if index <= mid:
            self.update(2 * node + 1, start, mid, index, value)
        else:
            self.update(2 * node + 2, mid + 1, end, index, value)

        self.tree[node] = self.tree[2 * node + 1] + self.tree[2 * node + 2]
```

## Fenwick Tree / Binary Indexed Tree

Fenwick tree is used for prefix sums with updates.

```python
class FenwickTree:
    def __init__(self, n):
        self.n = n
        self.tree = [0] * (n + 1)

    def update(self, index, delta):
        index += 1
        while index <= self.n:
            self.tree[index] += delta
            index += index & -index

    def query(self, index):
        index += 1
        result = 0
        while index > 0:
            result += self.tree[index]
            index -= index & -index

        return result
```

## LRU Cache

LRU means Least Recently Used.

It removes the least recently used item when capacity is full.

Python has `OrderedDict` for this.

```python
from collections import OrderedDict

class LRUCache:
    def __init__(self, capacity):
        self.capacity = capacity
        self.cache = OrderedDict()

    def get(self, key):
        if key not in self.cache:
            return -1

        self.cache.move_to_end(key)
        return self.cache[key]

    def put(self, key, value):
        if key in self.cache:
            self.cache.move_to_end(key)

        self.cache[key] = value

        if len(self.cache) > self.capacity:
            self.cache.popitem(last=False)
```

---

# 35. Algorithmic Problem-Solving Strategy

When solving a DSA problem, do not jump directly into code.

Use this process:

## Step 1: Understand the Problem

Ask:

* What is the input?
* What is the output?
* Are there constraints?
* Are duplicates allowed?
* Can input be empty?
* Is the array sorted?
* Are negative numbers possible?

## Step 2: Try Examples

Use small examples.

```text
Input: [2, 7, 11, 15], target = 9
Output: [0, 1]
```

## Step 3: Think of Brute Force

Brute force is not useless. It helps you understand the problem.

## Step 4: Optimize

Ask:

* Am I repeating work?
* Can I use a hash map?
* Can sorting help?
* Can two pointers help?
* Can sliding window help?
* Can recursion/backtracking help?
* Is this a graph/tree problem?
* Is this DP?

## Step 5: Write Clean Code

Use meaningful variable names.

Bad:

```python
def f(a, b):
    pass
```

Better:

```python
def two_sum(nums, target):
    pass
```

## Step 6: Test Edge Cases

Common edge cases:

* Empty input
* Single element
* All elements same
* Negative numbers
* Already sorted input
* Reverse sorted input
* Very large input
* Duplicate values

---

# 36. Python DSA Cheat Sheet

## Useful Imports

```python
from collections import defaultdict, Counter, deque, OrderedDict
import heapq
import bisect
import math
import itertools
```

## defaultdict

```python
from collections import defaultdict

graph = defaultdict(list)
graph[0].append(1)
```

## Counter

```python
from collections import Counter

freq = Counter("banana")
```

## deque

```python
from collections import deque

queue = deque()
queue.append(1)
queue.popleft()
```

## heapq
