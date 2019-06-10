---
layout: post
title: "CLRS Appendix A"
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

# 求和

**A. 1-1**

**解：**

$\sum\limits_{k = 1}^{n}(2k - 1) = 2\sum\limits^{n}_{k = 1}k + \sum\limits^{n}_{k = 1}1 = n(n+1) + n = n^2 + n + 1 $



**A. 1-2**

**证明：**

$\frac{1}{2}\sum\limits^{n}_{k = 1}\frac{1}{k} = \frac{1}{2}ln(n) + O(1)$

$\sum\limits^{n}_{k = 1}\frac{1}{2k - 1} + \sum\limits^{n}_{k = 1}\frac{1}{2k} = \sum\limits^{2n}_{k = 1}\frac{1}{k} = \ln(2n) + O(1)$

$\sum\limits_{k = 1}^{n}\frac{1}{2k - 1} = ln(2n) + O(1) - \frac{1}{2}ln(n) + O(1) = ln 2 + ln(n) - ln(\sqrt{n}) + O(1) = ln2 + ln(\sqrt{n}) + O(1) = ln(\sqrt{n}) + O(1)$



**A. 1-3**

**证明：**

利用对 A.8 公式再次求微分。

$\frac{x'(1-x)^2 + 2x(1-x)}{(1-x)^4} = \frac{(x + 1)}{(1 - x)^3}$

再乘 $x$ 得 $\frac{x(1+1)}{(1-x)^3}$



**A. 1-4**

**证明：**

$\sum\limits_{k = 0}^\infty\frac{(k-1)}{2^k} = \sum\limits_{k = 0}^\infty\frac{k}{2^k} - \sum\limits_{k = 0}^\infty\frac{1}{2^k} = \frac{\frac{1}{2}}{(1- \frac{1}{2})^2} - 2 = 0$ 得证。



**A. 1-5**

**证明：**

$\sum\limits_{k = 1}^\infty y^k = \frac{y}{1-y}$

$\sum\limits_{k =1}^\infty(x^2)^k = \frac{x^2}{1-x^2}$ 

$\sum\limits_{k = 1}^\infty xx^{2k}= \frac{x^3}{1-x^2}$

求微分

$\sum\limits_{k = 1}^\infty (2k+1)x^{2k} = \frac{3x^2(1-x^2) + 2x^4}{(1-x^2)^2}$

$= \frac{3x^2 - x^4}{(1-x^2)^2}$



**A. 1-6**

**证明：**

设 $g_1, g_2, … g_n, g_k(i) - O(f_k(i))$  根据 $O$ 的定义可得：

$\exists c_1, c_2, … c_n , g_k(i) \leq c_kf_k(i)$

令 $c = max_{1\leq k \leq n}c_k$

$\sum\limits_{k= 1}^n g_k(i) \leq \sum\limits_{k = 1}^n c_kf_k(i) \leq c\sum\limits_{k = 1}^n f_k(i) = O(\sum\limits_{k = 1}^nf_k(i))$



**A. 1-7**

**解：**

$\lg(\prod\limits_{k = 1}^n2 \times 4^k) = \sum\limits_{k = 1}^n\lg(2 \times 4^k) = \sum\limits_{k = 1}^n \lg(2) + \lg(4)\sum\limits_{k = 1}^n k$

$ = \lg(2)n + \lg(4)\frac{n(n + 1)}{2} = n(n+2)$

注：此处 $lg = log_2$



**A. 1-8**

**解：**

$\prod\limits_{k = 2}^n\frac{(k + 1)(k - 1)}{k^2} = \frac{1 \times 3}{2 \times 2} \times \frac{2 \times 4}{3 \times 3} \times …… \times \frac{(n - 1)(n + 1)}{n ^2}$

$ = \frac{n + 1}{2n}$













