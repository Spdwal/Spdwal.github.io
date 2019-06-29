---
layout: post
title: "[Leetcode from zero to one] 665"
category: 
tags: []
---

# 665 - Non-decreasing Array

Given an array with `n` integers, your task is to check if it could become non-decreasing by modifying **at most** `1` element.

We define an array is non-decreasing if `array[i] <= array[i + 1]` holds for every `i` (1 <= i < n).

**Example 1:**

```
Input: [4,2,3]
Output: True
Explanation: You could modify the first 4 to 1 to get a non-decreasing array.
```



**Example 2:**

```
Input: [4,2,1]
Output: False
Explanation: You can't get a non-decreasing array by modify at most one element.
```



**Note:** The `n` belongs to [1, 10,000].

首先数字改变有两种情况，一种是增大`nums[i - 1]` 一种是减小 `nums[i]` 。

当增大`nums[i - 1]` 时候,`nums[i - 1] = num[i]` 。

当减小`nums[i]` 时候，`nums[i] = num[i - 1]`

使用 prev 来保存 `nums[i - 1]` 。

如果是需要增大`nums[i - 1]` 的话，那么 `prev = nums[i]` 更新 `prev`。

 如果是必须减小 `nums[i]` 的话，那么那么跳过更新prev，`prev`保存的还是`nums[i - 1]`的值。

```c++
class Solution {
public:
    bool checkPossibility(vector<int>& nums) {
        int flag = false;
        int prev = nums[0];
        for(int i = 1; i < nums.size(); ++i){
            if(nums[i] < prev && flag++){
                return false;
            }
            if(nums[i] < prev && i > 1 && nums[i] < nums[i - 2]){
                continue;
            }
            prev = nums[i];
            
        }
        return true;
    }
};
```

