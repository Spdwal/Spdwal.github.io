---
layout: post
title: "[Leetcode from zero to one] 643"
category: 
tags: []
---

# 643 - Maximum Average Subarray I

Given an array consisting of `n` integers, find the contiguous subarray of given length `k` that has the maximum average value. And you need to output the maximum average value.

**Example 1:**

```
Input: [1,12,-5,-6,50,3], k = 4
Output: 12.75
Explanation: Maximum average is (12-5-6+50)/4 = 51/4 = 12.75
```

 

**Note:**

1. 1 <= `k` <= `n` <= 30,000.
2. Elements of the given array will be in the range [-10,000, 10,000].

 没啥好说的，非常简单的一道题，利用滑动窗口可以解。

```c++
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        double sum = 0;
        double res = INT_MIN;
        for(int i = 0; i < nums.size(); ++i){
            if(i < k){
                sum += nums[i];
            }else{
                res = max(sum, res);
                sum += nums[i];
                sum -= nums[i - k];
            }
        }
        res = max(sum, res);
        return res/k;
    }
};
```

