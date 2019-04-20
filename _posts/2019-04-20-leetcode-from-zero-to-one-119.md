---
layout: post
title: "[Leetcode from zero to one] 119"
category: 
tags: []
---

# 119 - Pascal's Triangle II

Given a non-negative index *k* where *k* ≤ 33, return the *k*th index row of the Pascal's triangle.

Note that the row index starts from 0.

**Follow up:**

Could you optimize your algorithm to use only *O*(*k*) extra space?

本来想用递归来做，但是在传入29的时候，超时了。失败，这个答案是看的discuss做的。。。失败。。

```c++
class Solution {
public:
    vector<int> getRow(int rowIndex) {
        vector<int> ivec(rowIndex + 1);
        ivec[0] = 1;
        for(int i = 0; i <= rowIndex; i++){
            for(int j = i; j >= 1; j--){
                ivec[j] = ivec[j] + ivec[j - 1];
            }
        }
        return ivec;
    }
};
```

