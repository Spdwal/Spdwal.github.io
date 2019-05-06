---
layout: post
title: "[Leetcode from zero to one] 50"
category: 
tags: []
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# 50 - Pow(x, n)

Implement [pow(*x*, *n*)](http://www.cplusplus.com/reference/valarray/pow/), which calculates *x* raised to the power *n* (xn).

**Example 1:**

```
Input: 2.00000, 10
Output: 1024.00000
```

**Example 2:**

```
Input: 2.10000, 3
Output: 9.26100
```

**Example 3:**

```
Input: 2.00000, -2
Output: 0.25000
Explanation: 2-2 = 1/22 = 1/4 = 0.25
```

**Note:**

- -100.0 < *x* < 100.0
- *n* is a 32-bit signed integer, within the range $[-2^{31}, 2^{31} - 1]$



首先想着用迭代的方法去做：

```c++
class Solution {
public:
    double myPow(double x, int n) {
        double ret = 1;
        if(n == 0){
            ret = static_cast<double>(1);
        }
        if(n > 0){
            while(n != 0){
                ret *= x;
                n--;
            }
        }
        if(n < 0){
            while(n != 0){
                ret /= x;
                n++;
            }
        }
        return ret;
    }
};
```

结果超时了。。。看了一下是一个大数点上超时

```
Last executed input:
0.00001
2147483647
```

所以就想用之前primer的筛法那样去除一些冗余的计算。

```c++
class Solution {
public:
    double myPow(double x, int n) {
        double ret = 1;
        if(n == 0){
            ret = static_cast<double>(1);
        }
        long long pow = n;
        if(n < 0){
            x = 1/x;
            pow = -pow;
        }
        
        while(pow != 0){
            if(pow % 2 == 0){
                x *= x;
                pow /= 2;
            }else{
                ret *= x;
                pow--;
            }
        }
        return ret;
    }
};
```

此处还有一个坑点，如果直接用 n = -n来赋值，会超过int的范围，需要进行类型转换。

