---
layout: post
title: "CodeWar from zero to one Consecutive strings"
category: 
tags: []
---

# Consecutive strings

You are given an array `strarr` of strings and an integer `k`. Your task is to return the **first** longest string consisting of k **consecutive** strings taken in the array.

# Example:

longest_consec(["zone", "abigail", "theta", "form", "libe", "zas", "theta", "abigail"], 2) --> "abigailtheta"

n being the length of the string array, if `n = 0` or `k > n` or `k <= 0` return "".

翻译一下题目，就是找出数组中的**最长的连续**字符串。

```c++
#include <string>
#include <vector>
#include <numeric>


class LongestConsec
{
public:
    static std::string longestConsec(std::vector<std::string> &strarr, int k){
      	// 排除错误情况，可能回出现段错误的参数。
        if(k > strarr.size() || k <= 0){
            return "";
        }
        
        auto it = strarr.begin();
        
        std::string  ret;
      	// 直到找到末尾位置。
        while(it + k <= strarr.end()){
          	// 构建连续字符串
            std::string temp = std::accumulate(it, it+k, std::string());
            // 如果比现在的保存的最长连续字符串更长的话，替换。
            if(ret.size() < temp.size()){
                ret = temp;
            }
          	// 迭代器往前走。
            it++;
        }
        
        return ret;
    }
};
```

总体效率较低，有机会再优化吧- -b。。。