---
layout: post
title: "[Leetcode from zero to one] 189"
category: 
tags: []
---

# 189 - Rotate Array

Given an array, rotate the array to the right by *k* steps, where *k* is non-negative.

**Example 1:**

```
Input: [1,2,3,4,5,6,7] and k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

**Example 2:**

```
Input: [-1,-100,3,99] and k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

**Note:**

- Try to come up as many solutions as you can, there are at least 3 different ways to solve this problem.
- Could you do it in-place with O(1) extra space?

刚开始想暴力求解，但是超时了。

看了答案，感觉非常巧妙。

先翻转整个数组，然后分成两段翻转即可。

```c++
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        if(nums.empty()){
            return;
        }
        int sz = nums.size();
        k = k % sz;
        reverse(nums.begin(), nums.end());
        reverse(nums.begin(), nums.begin() + k);
        reverse(nums.begin() + k, nums.end());
    }
};
```

