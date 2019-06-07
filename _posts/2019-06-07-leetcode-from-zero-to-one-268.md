---
layout: post
title: "[Leetcode from zero to one] 268"
category: 
tags: []
---

# 268 - Missing Number

Given an array containing *n* distinct numbers taken from `0, 1, 2, ..., n`, find the one that is missing from the array.

**Example 1:**

```
Input: [3,0,1]
Output: 2
```

**Example 2:**

```
Input: [9,6,4,2,3,5,7,0,1]
Output: 8
```

**Note**:
Your algorithm should run in linear runtime complexity. Could you implement it using only constant extra space complexity?



利用位运算， i^i = 0 来做。

```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int res = nums.size();
        for(int i = 0; i < nums.size(); i++){
            res ^= nums[i];
            res ^= i;
        }
        return res;
    }
};
```

