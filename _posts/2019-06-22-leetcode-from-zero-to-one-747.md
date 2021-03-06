---
layout: post
title: "[Leetcode from zero to one] 747"
category: 
tags: []
---

# 747 - Largest Number At Least Twice of Others

In a given integer array `nums`, there is always exactly one largest element.

Find whether the largest element in the array is at least twice as much as every other number in the array.

If it is, return the **index** of the largest element, otherwise return -1.

**Example 1:**

```
Input: nums = [3, 6, 1, 0]
Output: 1
Explanation: 6 is the largest integer, and for every other number in the array x,
6 is more than twice as big as x.  The index of value 6 is 1, so we return 1.
```

 

**Example 2:**

```
Input: nums = [1, 2, 3, 4]
Output: -1
Explanation: 4 isn't at least as big as twice the value of 3, so we return -1.
```

 

**Note:**

1. `nums` will have a length in the range `[1, 50]`.
2. Every `nums[i]` will be an integer in the range `[0, 99]`.

注意输入数组长度为1或者为0的情况。



```c++
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        if(nums.empty()){
            return -1;
        }
        if(nums.size() == 1){
            return 0;
        }
        int Biggest = 0;
        int secondBiggest = 0;
        if(nums[0] > nums[1]){
            Biggest = 0;
            secondBiggest = 1;
        }else{
            Biggest = 1;
            secondBiggest = 0;
        }
        
        for(int i = 2; i < nums.size(); ++i){
            if(nums[i] > nums[Biggest]){
                secondBiggest = Biggest;
                Biggest = i;
            }else if(nums[i] > nums[secondBiggest]){
                secondBiggest = i;
            }
        }
        
        if(nums[Biggest] >= (2 * nums[secondBiggest])) {
            return Biggest;
        }else{
            return -1;
        }
    }
           
};
```

