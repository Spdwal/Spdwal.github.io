---
layout: post
title: "[Leetcode from zero to one] 628"
category: 
tags: []
---

# 628 - Maximum Product of Three Numbers

Given an integer array, find three numbers whose product is maximum and output the maximum product.

**Example 1:**

```
Input: [1,2,3]
Output: 6
```

 

**Example 2:**

```
Input: [1,2,3,4]
Output: 24
```

 

**Note:**

1. The length of the given array will be in range [3,104] and all elements are in the range [-1000, 1000].
2. Multiplication of any three numbers in the input won't exceed the range of 32-bit signed integer.



没啥好说的，可以通过遍历，将时间复杂度缩减到O(n)，懒得写了。

```c++
class Solution {
public:
    int maximumProduct(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int end = nums.size() - 1;
        int a = nums[end] * nums[end - 1] * nums[end - 2];
        int b = 0;
        if(nums[0] < 0 && nums[1] < 0){
            b = nums[0] * nums[1] * nums[end];
        }
        
        return max(a, b);
    }
};
```

