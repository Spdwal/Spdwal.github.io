---
layout: post
title: "[Leetcode from zero to one] 283"
category: 
tags: []
---

# 283 - Move Zeroes

Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Example:**

```
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

**Note**:

1. You must do this **in-place** without making a copy of the array.
2. Minimize the total number of operations.

题目我没理清，他还要保持非0数据的顺序来着，之后就很简单了。

```c++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i = 0;
        int j = 0;
        while(i < nums.size()){
            if(nums[i] != 0){
                nums[j++] = nums[i];
            }
            i++;
        }
        
        for(; j < nums.size(); ++j){
            nums[j] = 0;
        }
    }
};
```

