---
layout: post
title: "[Leetcode from zero to one] 238"
category: 
tags: []
---

# 238 -  Product of Array Except Self

Given an array `nums` of *n* integers where *n* > 1,  return an array `output` such that `output[i]` is equal to the product of all the elements of `nums` except `nums[i]`.

**Example:**

```
Input:  [1,2,3,4]
Output: [24,12,8,6]
```

**Note:** Please solve it **without division** and in O(*n*).

**Follow up:**
Could you solve it with constant space complexity? (The output array **does not** count as extra space for the purpose of space complexity analysis.)

限定了不能使用除法。。。还挺难的。。。

```c++
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int fromBegin = 1;
        int fromLast  = 1;
        int sz = nums.size();
        vector result(sz, 1);
        
        for(int i = 0; i < sz; ++i){
            result[i] *= fromBegin;
            fromBegin *= nums[i];
            result[sz - i - 1] *= fromLast;
            fromLast *= nums[sz - i - 1];
        }
        
        return result;
    }
};
```

