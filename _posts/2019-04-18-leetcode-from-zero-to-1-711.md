---
layout: post
title: "[Leetcode from zero to 1] 711"
category: 
tags: []
---

# 711 - Jewels and Stones

You're given strings `J` representing the types of stones that are jewels, and `S` representing the stones you have.  Each character in `S` is a type of stone you have.  You want to know how many of the stones you have are also jewels.

The letters in `J` are guaranteed distinct, and all characters in `J` and `S` are letters. Letters are case sensitive, so `"a"` is considered a different type of stone from `"A"`.

简单的说，即是在1个名为stones的字符串里面找到jewels字符串里面的所有字母。首先我是想用字符串的算法进行暴力破解。代码如下：

 ```C++
class Solution {
public:
    int numJewelsInStones(string J, string S) {
        int jCount = 0;
        std::string::size_type n = 0;
        for(const auto & jch : J){
            string STemp = S;
            while ((n = STemp.find(jch)) != std::string::npos){
                jCount ++;
                STemp = STemp.substr(n);
            }
        }
        return jCount;
    }
};
 ```

华丽丽的超时，分析了一下，主要的问题应该是在for循环里多次复制字符串S，并且Stemp的substr赋值，也挺要时间的。在网上看了看分析，重新解答如下：

```C++
class Solution {
public:
    int numJewelsInStones(string J, string S) {
        int jCount = 0;
        set<char> mySet;
        for(int i = 0; i < J.size(); i++){
            mySet.insert(J[i]);
        }
        for(int i = 0; i < S.size(); i++){
            if(mySet.count(S[i])){
                jCount++;
            }
        }
        return jCount;
    }
};
```

Runtime: 4 ms, faster than 100.00% of C++ online submissions for Jewels and Stones.

Memory Usage: 8.6 MB, less than 98.31% of C++ online submissions for Jewels and Stones.