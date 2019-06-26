---
layout: post
title: "[Leetcode from zero to one] 581"
category: 
tags: []
---

# 581 - Shortest Unsorted Continuous Subarray

Given an integer array, you need to find one **continuous subarray** that if you only sort this subarray in ascending order, then the whole array will be sorted in ascending order, too.

You need to find the **shortest** such subarray and output its length.

**Example 1:**

```
Input: [2, 6, 4, 8, 10, 9, 15]
Output: 5
Explanation: You need to sort [6, 4, 8, 10, 9] in ascending order to make the whole array sorted in ascending order.
```



**Note:**

1. Then length of the input array is in range [1, 10,000].
2. The input array may contain duplicates, so ascending order here means **<=**.



想了很久，也想不出来怎么不使用额外空间。

```c++
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
        vector<int> sorted{nums};
        sort(sorted.begin(), sorted.end());
        int i = 0;
        int j = nums.size() - 1;
        
        for(; i < nums.size(); ++i){
            if(nums[i] != sorted[i]){
                break;
            }
        }
        
        for(; j >= 0 && i < j; j--){
            if(nums[j] != sorted[j]){
                break;
            }
        }
        
        return j - i + 1;
        
    }
};
```

