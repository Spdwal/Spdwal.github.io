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



## 对实数排序

**5.4.1**

**证明：**

假设 $ x \neq 0, $ 柯西序列 $ (a_n)_{n = 0}^\infty = x$ 

因为它是一个柯西序列，所以它是有界的，设 $\forall m, n \in \Q, mn > 0,\exists N \in \N^+ m \leq (a_n)_{n = N}^\infty \leq n$

若 $mn < 0$ 那么会得 $(a_n)_{n = N}^\infty = x = 0$ 与题设矛盾。

因为有理数的三岐性，且 $ mn > 0, \therefore m > 0, n > 0 \vee m < 0, n < 0$ 

当 $m > 0, n > 0$ 时候，$(a_n)_{n = 0}^\infty$ 为正远离0的。

当 $m < 0, n < 0$ 时候，$(a_n)_{n = 0}^\infty$ 为负远离0的。

得证。

若 $x , y$ 为正的，那么 $x \geq c_1, y \geq c_2,c_1 > 0, c_2 > 0, x + y \geq c_1 + c_2 > 0$

$xy \geq c_1c_2 > 0$ 得证。



**5.4.2**

**证明：**

1. 令 $z = x - y$, 由5.4.4可得：$z > 0, z = 0, z < 0$ 三者必取其一，即 $x > y, x = y, x < y$ 三者必取其一。
2. $y - x = z > 0, -z < 0, x - y = -z < 0 \Rightarrow  y > x$
3. $y - x = z_1 > 0, z - y = z_2 > 0, z_1 + z_2 > 0, z - x > 0, z > x$
4. $y - x = a > 0, (y + z) - (x + z) = y - x = a > 0 \Rightarrow y + z > x + z$



**5.4.3**

**证明：**

令 $x = LIM_{n \rightarrow \infty}b_n$

由4.4.1可得，$N \leq b_n < N+ 1$

设 $b_n = a_n + N$

$\exists N' \in \Q, n > N', 0 \leq a_n < 1$

根据5.4.1，$LIM_{n \rightarrow \infty} a_n$ 有两种状态，即正远离0与等于0。

分别可得出来，$N < x < N + 1 \vee  x = N$

可得 $\exists N \in \Q, N \leq x < N$



**5.4.4**

**证明：**

$\exists n, n = x^{-1}, xn = 1$ 令 $N = \lfloor n \rfloor + 1$

$n < N, xN > 1, x > 1/N$



**5.4.5**

**证明：**

设 $z = y - x > 0$

则必然 $\exists N, z > 1/N > 0$

$n \leq xN < n + 1, \frac{n}{N} \leq x < \frac{n + 1}{N}$

$y - x > 1/N, y > x + 1/N \geq \frac{n + 1}{N} > x$ 得证。



**5.4.6**

**证明：**

$y - \varepsilon < x < y + \varepsilon \Rightarrow y - x < \varepsilon \wedge x - y < \varepsilon \Rightarrow  |x - y| < \varepsilon$

$|x - y| < \varepsilon \Rightarrow -\varepsilon < x - y < \epsilon  \Rightarrow y - \varepsilon < x < y + \varepsilon$

$|x - y| = \varepsilon \Leftrightarrow -\varepsilon = x - y \vee x - y = \varepsilon$

$\Leftrightarrow x = y - \varepsilon \vee x = y + \varepsilon$ 得证。



**5.4.7**

**证明：**

1. 假设 $x > y$ 那么 $x - y = z > 0, x - y > z/2$ 与题设矛盾。

2. 当 $x = y$ 时，显然 $|x - y| \leq \varepsilon , \forall \varepsilon > 0$ 成立。

   由 $|x - y| \leq \varepsilon ,\forall \varepsilon \in \R$  成立。$x - y \leq \varepsilon, y - x \leq \varepsilon \Rightarrow x \leq y + \varepsilon, y \leq x + \varepsilon$

   $x \leq y, y \leq x, x = y$ 得证。



**5.4.8**

**证明：**

1. 假设 $LIM_{n \rightarrow \infty} a_n > x$  设 $b_n = a_n - x$

   由假设得：$LIM_{n \rightarrow \infty} b_n$ 为正远离0得，

   那么必然存在 $n', b_{n'} > 0, b_{n'} = a_{n'} - x > 0, a_{n'} > x$ 与题设相反，得证。

2. 证法同上。



## 最小上界性质

**5.5.1**

**证明：**

$\because M = sup(E), \forall x \in E, M > x \Rightarrow \forall x \in E, -M < -x$

所以 $-M$ 是 $-E$ 的下界。

假设 $A$ 是一个 $-E$ 的下界。并且 $A > -M$ 

$(-x \in -E) \Rightarrow -x \geq A \Rightarrow x \leq -A$

$\therefore A > -M, -A < M$ 与 $M$ 是最小上界矛盾，所以 $A \leq -M$



**5.5.2**

**证明：**

假设不存在这样的整数 $L$ 和 $K$, 也就是对于 $L < m \leq K$ 要么 $m/n, (m - 1)/n$ 都是 $E$ 的上界，要不都是不是 $E$ 的上界。

先证都不是上界的情况。

当 $m = L + 1$ 的时候，$[(m  + 1) -1] / n, (m + 1)/ n$ 都不是 $E$ 的上界，

利用数学归纳法 $m = L + 2, L + 3…. \infty$ 的时候，没有 $L' > m$ 使得 $L < m \leq K， L/n$ 为上界不成立。

在证都不是下界的情况。

当 $m = K，\forall x \in E, m/n > x \Rightarrow (m - 1)/n$ 也成立。

利用数学归纳法，可证明不存在 $K, L < m \leq K， K/n < x, \forall x \in E$。证明成立。



**5.5.3**

**证明：**

由 5.5.9，必然有一个最小上界 $M$ 则存在一个 $N$ 使得 $N + 1 < M \leq N, N + 1$ 是 $E$ 的上界，$N$ 是 $E$ 的下界。假设存在 $N', N'+1$ 是 $E$ 的上界，$N \neq N'$ 此时可得 $N' + 1 < M \leq N'$ 

同时由 习题 5.4.3,可得 $N = N'$



**5.5.4**

**证明：**

$\forall \varepsilon > 0, \exists N, N > 1/\varepsilon, 1/N < \varepsilon$

当 $n, n' > N$时，$|q_n - q_{n'}| \leq 1/N < \varepsilon$ 得证。

$S = \{q_M\}_{n \rightarrow \infty}$

$|q_m - S|$ 也是一个柯西序列。

可以柯西序列去掉前面有限项之后得到的序列是与原序列等价的。

所以设 $p_n = |q_M - S|$ 那么 $|q_M - S| = \{p_n\}_{n \rightarrow \infty}$

对任意的正整数n，都有 $p_n \leq 1/M$ 得证。

















