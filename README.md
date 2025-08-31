# 🤖 Maximum Walls Destroyed by Robots – LeetCode Contest Solution

This repository contains a Python solution to **Maximum Walls Destroyed by Robots**, featured in [LeetCode Weekly Contest 464](https://leetcode.com/contest/weekly-contest-464/problems/maximum-walls-destroyed-by-robots/).

---

## 🧠 Problem Summary

You are given three integer arrays:

- `robots[i]`: the position of the i-th robot
- `distance[i]`: the maximum distance the i-th robot's bullet can travel
- `walls[j]`: the position of the j-th wall

Each robot can fire one bullet either to the left or right, up to `distance[i]` meters. A bullet destroys every wall in its path that lies within range. However:

- Bullets stop immediately if they hit another robot.
- Robots are not destroyed.
- Walls and robots may share the same position.

Your task is to return the **maximum number of unique walls** that can be destroyed by the robots.

---

## ✅ Approach

This solution uses a **sweep-line strategy with binary search** to:

- Sort robots and walls by position
- Simulate left and right firing ranges while respecting robot collisions
- Count walls within each robot’s valid firing interval using `bisect_left` and `bisect_right`
- Handle overlapping intervals and avoid double-counting walls

### Key Techniques

- Binary search for wall counting in intervals
- Interval merging and overlap detection
- Greedy DP to maximize cumulative destruction

---

## 📊 Complexity

```markdown
Time Complexity: O(n log n + m log n)
- n = number of robots
- m = number of walls

Space Complexity: O(n + m)
- Sorted arrays and interval tracking
