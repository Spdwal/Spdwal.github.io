---
layout: post
title: "[Leetcode from zero to one] 724"
category: 
tags: []
---

# 724 - Find Pivot Index

Given an array of integers `nums`, write a method that returns the "pivot" index of this array.

We define the pivot index as the index where the sum of the numbers to the left of the index is equal to the sum of the numbers to the right of the index.

If no such index exists, we should return -1. If there are multiple pivot indexes, you should return the left-most pivot index.

**Example 1:**

```
Input: 
nums = [1, 7, 3, 6, 5, 6]
Output: 3
Explanation: 
The sum of the numbers to the left of index 3 (nums[3] = 6) is equal to the sum of numbers to the right of index 3.
Also, 3 is the first index where this occurs.
```

 

**Example 2:**

```
Input: 
nums = [1, 2, 3]
Output: -1
Explanation: 
There is no index that satisfies the conditions in the problem statement.
```

 

**Note:**

- The length of `nums` will be in the range `[0, 10000]`.
- Each element `nums[i]` will be an integer in the range `[-1000, 1000]`.

挺简单的一道题目：

```c++
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        if(nums.empty()){
            return -1;
        }
        int i = 1;
        int sum_right = accumulate(nums.begin(), nums.end(), 0) - nums[0];
        int sum_left = 0;
        if(sum_right == sum_left){
            return 0;
        }
        while(i < nums.size()){
            sum_right -= nums[i];
            sum_left += nums[i - 1];
            if(sum_right == sum_left){
                return i;
            }
            i++;
        }
        
        return -1;
    }
};
```

