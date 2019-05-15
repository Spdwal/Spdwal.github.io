---
layout: post
title: "[Leetcode from zero to one] 922"
category: 
tags: []
---

# 922 - Sort Array By Parity II

Given an array `A` of non-negative integers, half of the integers in A are odd, and half of the integers are even.

Sort the array so that whenever `A[i]` is odd, `i` is odd; and whenever `A[i]` is even, `i` is even.

You may return any answer array that satisfies this condition.

 

**Example 1:**

```
Input: [4,2,5,7]
Output: [4,5,2,7]
Explanation: [4,7,2,5], [2,5,4,7], [2,7,4,5] would also have been accepted.
```

解答如下，非常简单：

```c++
class Solution {
public:
    vector<int> sortArrayByParityII(vector<int>& A) {
        int i = 0; 
        int j = 1;
        vector<int> ivec(A.size(), 0);
        for(auto num : A){
            if(num % 2 == 0){
                ivec[i] = num;
                i += 2;
            }else{
                ivec[j] = num;
                j += 2;
            }
        }
        
        return ivec;
    }
};
```

