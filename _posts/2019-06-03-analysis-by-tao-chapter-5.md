---
layout: post
title: "Analysis by Tao Chapter 5"
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

## 柯西序列

**5.1.1**

**证明：**

根据柯西序列的定义，设 $N \in \mathbb{N+}, j, k \geq N, d(a_j, a_k) \leq \varepsilon$ 现在取 $N = 1$ 那么可以将柯西数列划分为两个部分：

一个有限序列 $(a)_{n = 1}^{N}$ 此序列是有界的，不妨设他有上界 $x$ 。

一个无限序列 $(a)_{n = N}^{\infty}$ 是 $1-$ 稳定的。那么$ \forall n, n \geq N, d(a_N, a_n) \leq 1, a_n \leq a_N + 1$ 

那么这个序列 $\forall n \in N, a_n \leq max(x, a_N + 1)$ 它是有界的。得证。

下界同理。



## 等价的柯西序列

**5.2.1**

**证明：**

首先由于 $(a_n)_{n = 1}^{\infty}$ 是柯西序列，所以对于任意的 $ \varepsilon \in \Q^+, \exists n_1 \in \N, \forall i, j > n_1,d(a_i, a_j) < \varepsilon$ 

又因为 $(a_n)_{n = 1}^{\infty}, (b_n)_{n = 1}^{\infty}$ 为无限接近的。那么相对于 $\exists n_2 \in \N, i > n_2, d(a_i, b_i) < \varepsilon$

$|b_i - b_j| \leq |b_i - a_i| + |a_i - a_j| + |a_j - b_j| <3\varepsilon$

由于 $ \forall \varepsilon \in \Q$ 所以 $\varepsilon$ 可以取任意值，取 $\varepsilon' = 3\varepsilon, \varepsilon' \in \Q$ 得证。



**5.2.2**

**证明：**

首先假设 $(b_n)_{n = 1}^{\infty}$ 是无界的情况下，$ (a_n)_{n = 1}^{\infty} $ 是有界的。

$\exists I \in \N^+, \forall n \in N^+,(a_n)_{n = 1}^{\infty} \leq I$ 

由于 $(a_n)_{n = 1}^{\infty}, (b_n)_{n = 1}^{\infty}$ 是最终 $\varepsilon-$ 接近的，可以将 $(b_n)_{n = 1}^{\infty}$ 分为两个部分。

$\exists N \in \N^+, \forall n_1 \geq N, d(a_{n_1}, b_{n_1}) < 1$

$(b_n)_{n = n_1}^{\infty} < I + 1$ 有界的。

而本身$(b_n)_{n = 0}^{n_1}$ 是有限序列，也是有界的， 设此序列有上界 $J$

那么 $(b_n)_{n = 0}^{\infty}$ 有上界 $max(I + 1, J)$ 得证。



 ## 实数的构造

**5.3.1**

**证明：**

如果 $x = y \Rightarrow LIM_{n \rightarrow \infty}a_n = LIM_{n \rightarrow \infty}b_n \Rightarrow (a_n)_{n =1}^\infty  (b_n)_{n = 1}^\infty$ 是等价的柯西序列。

即 $ \forall \varepsilon > 0, (a_n)_{n = 0}^\infty, (b_n)_{n = 0}^\infty$ 是 $\varepsilon-$ 接近的。

即 $\forall \varepsilon > 0, |a_n - b_n| \leq \varepsilon \Rightarrow |b_n - a_n| \leq \varepsilon$

那 $ \forall \varepsilon > 0, (b_n)_{n = 0}^\infty, (a_n)_{n = 0}^\infty$ 是 $\varepsilon-$ 接近的。

$\therefore y = x $

接下来证$x = y, y = z \Rightarrow x =z$

由已知得：$(a_n)_{n = 1}^\infty, (b_n)_{n =1}^\infty, (c_n)_{n = 1}^\infty$  具有以下的性质：

$\forall n \in \N^+, \forall \varepsilon, \delta > 0, d(a_n, b_n) < \varepsilon, d(b_n, c_n) < \delta, d(a_n, c_n) < \varepsilon + \delta$

任取 $\varepsilon' = \varepsilon + \delta$ 总能取到相应的 $\varepsilon, \delta > 0$ 

所以 $\forall \varepsilon' > 0, d(a_n, c_n) < \varepsilon'$ 所以 $(a_n)_{n = 0}^\infty, (c_n)_{n = 0}^\infty$ 是等价的柯西序列。

所以$x = z$ 得证。



**5.3.2**

**证明：**

$xy = LIM_{n \rightarrow \infty}, \because (a_n)_{n = 0}^\infty, (b_n)_{n = 0}^\infty$ 都是柯西序列

$\therefore \forall \varepsilon, \delta > 0,d(a_n, x) = \varepsilon, d(b_n, y) = \delta$

根据4.3.7的结论(g)，$(a_n\times b_n)_{n = 0}^\infty $ 与 $xy$ 是 $(|x|\delta + |y|\varepsilon + \varepsilon\delta)-$ 接近的，

因为取 $\varepsilon' =|x|\delta + |y|\varepsilon + \varepsilon\delta$ 时，可得 $(a_nb_n)_{n = 0}^\infty$ 是柯西序列，所以xy为实数。

根据之前的证明

$(a'_n \times b_n)_{n = 0}^\infty$ 与 $x'y$ 是 $((|x'|\delta + |y|\varepsilon + \varepsilon\delta)-)$ 接近的。

又因为 $x = x'$ 所以 $(a'_n \times b_n)_{n = 0}^\infty$ 与 $xy$ 是 $((|x|\delta + |y|\varepsilon + \varepsilon\delta)-)$ 接近的。

所以 $x'y$ 等价于 $xy$ 所以 $xy = x'y$。



**5.3.3**

**证明：**

假设他们两个不是等价的。

即存在 $\varepsilon  > 0, |a_n - b_n| > \varepsilon$ 

$a \neq b$ 矛盾，得证。



**5.3.4**

**证明：**

因为这两个序列是等价的，所以这两个序列是最终 $\varepsilon-$ 等价的，根据5.2.2的结论，所以它是有界的。



**5.3.5**

**证明：**

任取 $\varepsilon > 0, \exists n, |1 / n - 0 | < \varepsilon$

$n > 1/\varepsilon$ 即可。所以 $LIM_{n \rightarrow \infty}1/n$ 与 $LIM_{n\rightarrow \infty}0$ 是等价的。

所以 $LIM_{n\rightarrow \infty}1/n = 0$ 







































