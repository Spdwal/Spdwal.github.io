---
layout: post
title: "[Leetcode from zero to one] 717"
category: 
tags: []
---

# 717 - 1-bit and 2-bit Characters

We have two special characters. The first character can be represented by one bit `0`. The second character can be represented by two bits (`10` or `11`).

Now given a string represented by several bits. Return whether the last character must be a one-bit character or not. The given string will always end with a zero.

**Example 1:**

```
Input: 
bits = [1, 0, 0]
Output: True
Explanation: 
The only way to decode it is two-bit character and one-bit character. So the last character is one-bit character.
```



**Example 2:**

```
Input: 
bits = [1, 1, 1, 0]
Output: False
Explanation: 
The only way to decode it is two-bit character and two-bit character. So the last character is NOT one-bit character.
```



**Note:**

`1 <= len(bits) <= 1000`.

`bits[i]` is always `0` or `1`.

这道题的难点。。还是在题目不好理解。

这道题目的大意是：数组中存在两种字符，一种是一个字节的，一种是2个字节的，一个字节的只有0，2个字节的有11，10两种，现在看能不能正确的吧数组分组，并且最后一个是一个一字节的字符。

```c++
class Solution {
public:
    bool isOneBitCharacter(vector<int>& bits) {
        bool res;
        for(int i = 0; i < bits.size();){
            if(bits[i] == 1){
                res = false;
                i += 2;
            }else{
                res = true;
                i++;
            }
        }
        return res;
    }
};
```

