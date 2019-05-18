---
layout: post
title: "[Leetcode from zero to one] 442"
category: 
tags: []
---

# 442 - Find All Duplicates in an Array

Given an array of integers, 1 ≤ a[i] ≤ *n* (*n* = size of array), some elements appear **twice** and others appear **once**.

Find all the elements that appear **twice** in this array.

Could you do it without extra space and in O(*n*) runtime?



**Example:**

```
Input:
[4,3,2,7,8,2,3,1]

Output:
[2,3]
```



这道题完全没有思路，看了discuss里的解法之后感觉人和人之间的差距太大了。

解答者将本身的Array作为一个bit数组，翻转1次为负数，翻转2次为正数，不过这个解法不具有普适性，只能针对这个题目，对于会出现多次以上的数组没有办法解答。



```c++
class Solution {
public:
    vector<int> findDuplicates(vector<int>& nums) {
        vector<int> res;
        for(int i = 0; i < nums.size(); i ++){
            nums[abs(nums[i])-1] = -nums[abs(nums[i])-1];
            if(nums[abs(nums[i])-1] > 0) res.push_back(abs(nums [i]));
        }
        return res;
    }
};
```

