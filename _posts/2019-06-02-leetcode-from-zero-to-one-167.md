---
layout: post
title: "[Leetcode from zero to one] 167"
category: 
tags: []
---

# 167 - Two Sum II - Input array is sorted

Given an array of integers that is already **sorted in ascending order**, find two numbers such that they add up to a specific target number.

The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2.

**Note:**

- Your returned answers (both index1 and index2) are not zero-based.
- You may assume that each input would have *exactly* one solution and you may not use the *same* element twice.

**Example:**

```
Input: numbers = [2,7,11,15], target = 9
Output: [1,2]
Explanation: The sum of 2 and 7 is 9. Therefore index1 = 1, index2 = 2.
```

使用快慢指针法。

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int Left = 0;
        int Right = numbers.size() - 1;
        while(true){
            if(Left >= Right){
                return {};
            }
            if(numbers[Left] + numbers[Right] == target){
                return {Left+1, Right+1};
            }
          	// 如果和比较小的话，那么就左边指针往前走，越来越大
            if(numbers[Left] + numbers[Right] < target){
                Left++;
            // 如果和比较大，那么右边指针往后走，越来越小。
            }else if(numbers[Left] + numbers[Right] > target){
                Right--;
            }
        }
    }
};
```

