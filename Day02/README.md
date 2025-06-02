# 📅 Day 02 - [135. Candy](https://leetcode.com/problems/candy/)

**Level**: Hard  
**Tags**: Greedy, Array  

---

## 🧾 Problem Statement

There are `n` children standing in a line. Each child is assigned a rating value given in the integer array `ratings`.

You are giving candies to these children subject to the following rules:

1. Each child must have **at least one candy**.
2. Children with a **higher rating** get **more candies** than their neighbors.

Return the **minimum number of candies** you need to distribute.
---

## 💡 Approach

This problem can be solved using a **greedy two-pass approach**, but the given solution smartly processes the array in segments:

### 🔍 Key Observations:

- The candy distribution must increase in ascending sequences and decrease in descending sequences.
- The idea is to process segments with increasing or decreasing ratings and track the **extra candies** needed.
- The function `processSegment` computes how many extra candies are needed from the current index and returns the next index to process.

### 🧠 Trick:
To avoid **double-counting the peak** between ascending and descending sequences, we subtract the `min(up, down)` from the total extra candies.

---

## 🧠 Time & Space Complexity

- **Time Complexity**: O(n)  
- **Space Complexity**: O(1)

---
