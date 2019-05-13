---
layout: post
title: "[Leetcode from zero to one] 905"
category: 
tags: []
---

# 905 - Sort Array By Parity

Given an array `A` of non-negative integers, return an array consisting of all the even elements of `A`, followed by all the odd elements of `A`.

You may return any answer array that satisfies this condition.

 

**Example 1:**

```
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```

解答如下：

```c++
class Solution {
public:
    vector<int> sortArrayByParity(vector<int>& A) {
        int i = 0;
        int j = 0;
        int end = A.size() - 1;
        
        for(; j < end; j++){
            if(A[j] %2 == 0){
                swap(A[i++], A[j]);
            }
        }
        
        return A;
    }
};
```

用一种类似快慢指针的思路来解。



另外在discuss中看到使用标准库的解答：

```c++
vector<int> sortArrayByParity(vector<int>& A) {
    auto is_even = [] (auto e) { return e % 2 == 0; };
    partition (A.begin (), A.end (), is_even);
    return A;
}
```

