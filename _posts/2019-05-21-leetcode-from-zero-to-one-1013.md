---
layout: post
title: "[Leetcode from zero to one] 1013"
category: 
tags: []
---

# 1013 - Partition Array Into Three Parts With Equal Sum

Given an array `A` of integers, return `true` if and only if we can partition the array into three **non-empty** parts with equal sums.

Formally, we can partition the array if we can find indexes `i+1 < j` with `(A[0] + A[1] + ... + A[i] == A[i+1] + A[i+2] + ... + A[j-1] == A[j] + A[j-1] + ... + A[A.length - 1])`

 

**Example 1:**

```
Input: [0,2,1,-6,6,-7,9,1,2,0,1]
Output: true
Explanation: 0 + 2 + 1 = -6 + 6 - 7 + 9 + 1 = 2 + 0 + 1
```

**Example 2:**

```
Input: [0,2,1,-6,6,7,9,-1,2,0,1]
Output: false
```

**Example 3:**

```
Input: [3,3,6,5,-2,2,5,1,-9,4]
Output: true
Explanation: 3 + 3 = 6 = 5 - 2 + 2 + 5 + 1 - 9 + 4
```

 

**Note:**

1. `3 <= A.length <= 50000`
2. `-10000 <= A[i] <= 10000`

这道题目主要问题就是在我思路太僵化了。。。。想要动态的求sum，最后做出来 $O(n^2)$ 的时间复杂度，其实想通了的话，非常简单。

```c++
class Solution {
public:
    bool canThreePartsEqualSum(vector<int>& A) {
        int total = accumulate(A.begin(), A.end(), 0);
        if(total % 3 != 0) return false;
        int partSum = total / 3;
        int flag = 0;
        int sum = 0;
        for(int i = 0; i < A.size(); ++i){
            sum += A[i];
            if(sum == partSum){
                sum = 0;
                flag++;
            }
        }
        if(sum == 0 && flag == 3){
            return true;
        }
        return false;
    }
};
```

