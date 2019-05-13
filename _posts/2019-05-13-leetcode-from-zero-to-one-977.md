---
layout: post
title: "[Leetcode from zero to one] 977"
category: 
tags: []
---

# 977 - Squares of a Sorted Array

Given an array of integers `A` sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.

 

**Example 1:**

```
Input: [-4,-1,0,3,10]
Output: [0,1,9,16,100]
```

**Example 2:**

```
Input: [-7,-3,2,3,11]
Output: [4,9,9,49,121]
```



```c++
class Solution {
public:
    vector<int> sortedSquares(vector<int>& A) {
        for(int & a: A){
            a *= a;
        }
        
        sort(A.begin(), A.end());
        
        return A;
    }
};
```

运行时间挺不理想的= =b。

```c++
class Solution {
public:
    vector<int> sortedSquares(vector<int>& A) {
      vector<int> res(A.size());
      for (int pn = 0, pp = A.size() - 1, pos = A.size() - 1; pn <= pp; --pos)
        res[pos] = pow(abs(A[pn]) < abs(A[pp]) ? A[pp--] : A[pn++], 2);
      return res;
    }  
};
```

这个解法的思路是使用左右两个指针，然后对比大小进行排序，不过不具有普适性，这建立在这个数组本来就是被排序好的基础之上。