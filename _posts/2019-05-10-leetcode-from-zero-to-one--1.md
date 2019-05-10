---
layout: post
title: "[Leetcode from zero to one]  1"
category: 
tags: []
---

# 1 - Two Sum



Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have **exactly** one solution, and you may not use the *same* element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

 暴力解法会超时，只能用hash来解决这个了。

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> imap;
        for(int i = 0; i < nums.size(); ++i){
            imap[nums[i]] = i;
        }
        int a = 0;
        int i = 0;
        for(i = 0; i < nums.size(); ++i){
            a = target - nums[i];
            if(imap.count(a) != 0 && imap[a] != i){
                break;
            }
        }
        return vector<int>{i, imap[a]};
    }
};
```

