# 📅 Day 01 - [2929. Distribute Candies Among Children II](https://leetcode.com/problems/distribute-candies-among-children-ii/)

**Level**: Medium  
**Tags**: Math, Combinatorics  

---

## 🧾 Problem Statement

You are given two positive integers `n` and `limit`.  
Return the total number of ways to distribute `n` candies among **3 children** such that **no child gets more than `limit` candies**.

---

## 💡 Approach

This is a combinatorics problem simplified using a smart iteration.

Let:
- `x`, `y`, `z` be the number of candies given to each child.  
- We need to find all non-negative integer triplets (x, y, z) such that:  
  - `x + y + z = n`  
  - `x ≤ limit`, `y ≤ limit`, `z ≤ limit`  

### To solve:
- Fix `x` in its feasible range:  
  `max(0, n - 2 * limit)` ≤ x ≤ `min(limit, n)`
- For each `x`, calculate how many (y, z) combinations are valid:
  - Remaining = `n - x`  
  - Count pairs `(y, z)` such that 0 ≤ y ≤ limit and 0 ≤ z ≤ limit and `y + z = remaining`  
  - That count is:  
    `(min(remaining, limit) - max(0, remaining - limit) + 1)`

---

## 🧠 Time & Space Complexity

- **Time Complexity**: O(limit) (at most iterating over [0..limit])  
- **Space Complexity**: O(1)

---
