---
layout: post
title: "[Leetcode from zero to one] 509"
category: 
tags: []
---

# 509 - Fibonacci Number

The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
```

Given `N`, calculate `F(N)`.

居然。。。最普通的fibnacci算法可以过，我以为会栈溢出来着。

```c++
class Solution {
public:
    int fib(int n) {
        if(n == 1)
            return 1;
        if(n == 0) 
            return 0;
        return fib(n - 1) + fib(n - 2);
    }
};
```

以下为尾递归版本，出处为SICP，时间约等于第一个版本的1/4。

```c++
class Solution {
public:
    int fib(int n) {
        return fibHelper(0, 1, n);
    }
    
    int fibHelper(int current, int next, int n){
        if(n == 0){
            return current;
        }else{
            return fibHelper(next, current + next, n - 1);
        }
    }
};
```

