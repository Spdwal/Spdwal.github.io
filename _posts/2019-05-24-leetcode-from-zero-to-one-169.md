---
layout: post
title: "[Leetcode from zero to one] 169"
category: 
tags: []
---

# 169 - Majority Element

Given an array of size *n*, find the majority element. The majority element is the element that appears **more than** `⌊ n/2 ⌋`times.

You may assume that the array is non-empty and the majority element always exist in the array.

**Example 1:**

```
Input: [3,2,3]
Output: 3
```

**Example 2:**

```
Input: [2,2,1,1,1,2,2]
Output: 2
```

以下是我的解答，但是时间和空间利用率，都很不尽人意。

```c++
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        return nums[nums.size()/2];
    }
};
```

这是discuss里的解答：

```c++
class Solution {
    public:
    int majorityElement(vector<int> &num) {

        int major=num[0], count = 1;
        for(int i= 1; i<num.size();i++){
            if(count==0){
                count++;
                major=num[i];
            }else if(major==num[i]){
                count++;
            }else count--;
            
        }
        return major;
    }
};
```

具体用的是摩尔投票法。

思路就是将两个不同的数字两两抵消掉，最后剩下的数字就是所得的数字，注意这个只有在数字出现次数大于数组的一半的时候才能够使用。