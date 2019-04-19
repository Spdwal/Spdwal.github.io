---
layout: post
title: "CodeWar from zero to one Maximum Length Difference"
category: 
tags: []
---

# Maximum Length Difference

You are given two arrays `a1` and `a2` of strings. Each string is composed with letters from `a` to `z`. Let `x` be any string in the first array and `y` be any string in the second array.

```
Find max(abs(length(x) − length(y)))
```

If `a1` and/or `a2` are empty return `-1` in each language except in Haskell (F#) where you will return `Nothing` (None).

这道题的坑点就是没有坑点，可以充分的看出自己的傻逼程度。

```c++
#include <cmath>
#include <algorithm>

class MaxDiffLength
{
public:
    static int mxdiflg(std::vector<std::string> &a1, std::vector<std::string> &a2){
        int maxX = 0; 
        int maxY = 0;
        if(a1.size() == 0 || a2.size() == 0){
            return -1;
        }
        int minX = a1[0].size();
        int minY = a2[0].size();
        for(auto & str: a1){
            if(str.size() > maxX){
                maxX = str.size();
            }
            if(str.size() < minX){
                minX = str.size();
            }
        }
        
        for(auto &str: a2){
            if(str.size() > maxY){
                maxY = str.size();
            }
            if(str.size() < minY){
                minY = str.size();
            }
        }
        
        return std::max(std::abs(maxX - minY), 
                        std::abs(maxY - minX));
        
    }
};

```

