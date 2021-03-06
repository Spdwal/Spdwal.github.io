---
layout: post
title: "[Leetcode from zero to one] 414"
category: 
tags: []
---

# 414 - Third Maximum Number

Given a **non-empty** array of integers, return the **third** maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O(n).

**Example 1:**

```
Input: [3, 2, 1]

Output: 1

Explanation: The third maximum is 1.
```



**Example 2:**

```
Input: [1, 2]

Output: 2

Explanation: The third maximum does not exist, so the maximum (2) is returned instead.
```



**Example 3:**

```
Input: [2, 2, 3, 1]

Output: 1

Explanation: Note that the third maximum here means the third maximum distinct number.
Both numbers with value 2 are both considered as second maximum.
```



测试点里特地放了`INT_MIN` 有点小恶心。

```c++
class Solution {
public:
    int thirdMax(vector<int>& nums) {
        long long max1 = LLONG_MIN;
        long long max2 = LLONG_MIN;
        long long max3 = LLONG_MIN;

        for(int i = 0; i < nums.size(); ++i){
            if(nums[i] > max1){
                max3 = max2;
                max2 = max1;
                max1 = nums[i];
            }else if(nums[i] > max2 && nums[i] != max1){
                max3 = max2;
                max2 = nums[i];
            }else if(nums[i] > max3 && nums[i] != max2 && nums[i] != max1){
                max3 = nums[i];
            }
        }

        return max3 == LLONG_MIN ? max1 : max3;
    }
};
```



