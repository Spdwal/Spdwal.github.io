---
layout: post
title: "[Leetcode from zero to one] 697"
category: 
tags: []
---

# 697 - Degree of an Array

Given a non-empty array of non-negative integers `nums`, the **degree** of this array is defined as the maximum frequency of any one of its elements.

Your task is to find the smallest possible length of a (contiguous) subarray of `nums`, that has the same degree as `nums`.

**Example 1:**

```
Input: [1, 2, 2, 3, 1]
Output: 2
Explanation: 
The input array has a degree of 2 because both elements 1 and 2 appear twice.
Of the subarrays that have the same degree:
[1, 2, 2, 3, 1], [1, 2, 2, 3], [2, 2, 3, 1], [1, 2, 2], [2, 2, 3], [2, 2]
The shortest length is 2. So return 2.
```



**Example 2:**

```
Input: [1,2,2,3,1,4,2]
Output: 6
```



**Note:**

`nums.length` will be between 1 and 50,000.

`nums[i]` will be an integer between 0 and 49,999.

这个例子举的有点让人懵圈，但是理解了之后解题思路还是很直接的，就是暴力破解。



```c++
class Solution {
public:
    int findShortestSubArray(vector<int>& nums) {
      	// first 保存的这个数字的第一个位置。
      	// count 保存的这个数字出现了几次，用以设定degree的大小。
        unordered_map<int, int> first, count;
        int res = 0;
        int degree = 0;
        for(int i = 0; i < nums.size(); ++i){
          	// 如果第一次出现，就保存住他的index
            if(first.count(nums[i]) == 0){
                first[nums[i]] = i;
            }
            // 更新degree
            if(++count[nums[i]] > degree){
                degree = count[nums[i]];
              	// 更新 result
                res = i - first[nums[i]] + 1;
            }else if(count[nums[i]] == degree){
                res = min(res, i - first[nums[i]] + 1);
            }
        }
        return res;
    }
};
```

