---
layout: post
title: "[Leetcode from one to zero] 118"
category: 
tags: []
---

# 118 - Pascal‘s Triangle

Given a non-negative integer *numRows*, generate the first *numRows* of Pascal's triangle.

就是做一个杨辉三角形的数组出来。很简单来着，但是递归的话，感觉并不好做，主要问题是效率太低了。

```c++
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ret(numRows);
        for(int rows = 0; rows < numRows; rows++){
            for(int cols = 0; cols <= rows; cols++){
                if(cols == 0 || cols == rows){
                    ret[rows].push_back(1);
                }else{
                    int num = ret[rows - 1][cols - 1] + ret[rows - 1][cols];
                    ret[rows].push_back(num);
                }
            }
        }
        return ret;
    }
};
```

