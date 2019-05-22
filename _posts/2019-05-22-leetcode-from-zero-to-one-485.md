---
layout: post
title: "[Leetcode from zero to one] 485"
category: 
tags: []
---

# 485 - Max Consecutive Ones

Given a binary array, find the maximum number of consecutive 1s in this array.

**Example 1:**

```
Input: [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s.
    The maximum number of consecutive 1s is 3.
```



**Note:**

- The input array will only contain `0` and `1`.
- The length of input array is a positive integer and will not exceed 10,000

题目挺简单的，但是同时我的解法也挺蠢的- -b。

```c++
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int pre = nums[0];
        int consecutive = nums[0] ? 1 : 0;
        int maxCon = consecutive;
        for(int i = 1; i < nums.size(); i++){
            if(nums[i] == pre && pre == 1){
                consecutive++;
            }else{
                pre = nums[i];
                consecutive = nums[i] ? 1 : 0;
            }
            if(consecutive > maxCon){
                maxCon = consecutive;
            }
        }
        return maxCon;
    }
};
```

disscuss中的解答。。。我的代码能力和人家没法比呀。。。

```c++
  int findMaxConsecutiveOnes(vector<int>& nums) {
        int max_cnt = 0, cnt = 0;
        for (auto n : nums) {
            if (n == 1) max_cnt = max(++cnt, max_cnt);
            else cnt = 0;
        }
        return max_cnt;
  }
```

