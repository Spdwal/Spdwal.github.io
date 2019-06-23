---
layout: post
title: "[Leetcode from zero to one] 88"
category: 
tags: []
---

# 88 - Merge Sorted Array

Given two sorted integer arrays *nums1* and *nums2*, merge *nums2* into *nums1* as one sorted array.

**Note:**

- The number of elements initialized in *nums1* and *nums2* are *m* and *n* respectively.
- You may assume that *nums1* has enough space (size that is greater or equal to *m* + *n*) to hold additional elements from *nums2*.

**Example:**

```
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
```

注意一点，不需要再考虑i不为0的情况，因为他本身就在res数组里面了。

```c++
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int res = nums1.size() - 1;
        while(i >= 0 && j >= 0){
            if(nums1[i] < nums2[j]){
                nums1[res--] = nums2[j--];
            }else{
                nums1[res--] = nums1[i--];
            }
        }
        
        while(j >= 0){
            nums1[res--] = nums2[j--];
        }
    }
};
```

