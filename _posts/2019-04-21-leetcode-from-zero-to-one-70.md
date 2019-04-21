---
layout: post
title: "[Leetcode from zero to one] 70"
category: 
tags: []
---

# 70 - Climbing Stairs

You are climbing a stair case. It takes *n* steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

**Note:** Given *n* will be a positive integer.

**Example 1:**

```
Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

**Example 2:**

```
Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

最开始用了一种很蠢的方法，最后超时了- -。。。。

```
class Solution {
public:
    int climbStairs(int n) {
        int result = 0;
        helperHelper(n, &result);
        return result;
    }
    
    void helperHelper(int c, int *result){
            climbStairsHelper(1, c, result);
            climbStairsHelper(2, c, result);
    }
    void climbStairsHelper(int a, int n, int *result){
        if(n == a){
            *result += 1;
            return;
        }else if(n < a){
            return ;
        }else{
            int c = n - a;
            helperHelper(c, result);
        }     
    }
};
```

看了一种解答，这是fibnacci的一种变体：

```c++
class Solution {
public:
    int climbStairs(int n) {
        if(n == 1){
             return 1;
        }
        if(n == 2){
            return 2;
        }
        return climbStairs(n - 1) + climbStairs(n - 2);
    }
};
```

继续超时。。。猜测是因为使用了愚蠢的fibnacci做法导致的。

```c++
class Solution {
public:
    int climbStairs(int n) {
        int next  = 1;
        int pre = 0;
        int ret = 0;
        for(int i = 0; i < n; i++){
            ret = next + pre;
            pre = next;
            next = ret;
        }
        return ret;
    }
};
```

最后使用递归版本的c++fibnacci函数得以ac。

