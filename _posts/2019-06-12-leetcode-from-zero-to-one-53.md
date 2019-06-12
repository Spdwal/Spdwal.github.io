---
layout: post
title: "[Leetcode from zero to one] 53"
category: 
tags: []
---

# 53 - Maximum Subarray

Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

**Example:**

```
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

**Follow up:**

If you have figured out the O(*n*) solution, try coding another solution using the divide and conquer approach, which is more subtle.

使用动态规划来做：

```c++
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int sz = nums.size();
        vector<int> dp(sz);
        
        dp[0] = nums[0];
        int Max = nums[0];
        
        for(int i = 1; i < sz; ++i){
            dp[i] = nums[i] + (dp[i - 1] > 0 ? dp[i - 1] : 0);
            Max = max(dp[i], Max);
        }
        
        return Max;
    }
};
```

