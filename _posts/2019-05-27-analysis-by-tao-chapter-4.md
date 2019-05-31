---
layout: post
title: "Analysis by Tao Chapter 4"
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

## 整数

**4.1.1**

**证明：**

自反性：$a — b = a —b \Rightarrow a + b = a + b$ 显然得证。

对称性：$a —b = c —d \Rightarrow a + d = c + b \Rightarrow c + b = a + d \Rightarrow c —d = a — b$ 得证。



**4.1.2**

**证明：**

$a — b = a' —b' \Rightarrow a' + b = a + b' \Rightarrow b + a' = b' + a \Rightarrow b —a = b' — a'$

$\Rightarrow -(a—b) = - (a' — b')$ 得证。



**4.1.3**

**证明：**

如果 $a$ 为正数。

$(-1) \times a = (-1) \times (a — 0) = (0–1) \times (a — 0) = 0 - a = -a$

如果 $a$ 为 $0$

$(-1) \times 0 = 0$  得证。

如果 $a$ 为负数。

$(-1) \times a = (0 — 1) \times (0 — b) = b = -a$ 得证。



**4.1.4**

**证明：**

$x + y = y + x$:

$(a — b) + (c — d) = (a + c) — (b + d) = (c + a) — (d + b) = (c — d) + (a — b) = y + x$

$(x + y) + z = x + (y + z)$:

$[(a — b) + (c —d)] + (e—f)= [(a +c) — (b + d)] + (e — f) = (a + c + e) — (b + d + f) = (a — b) + [(c + e) — (d + f)] = x + (y + z)$

$x + 0 = 0 + x = x$:

$(a — b) + 0 = (a — b) + (0 — 0) = (a + 0) — (b + 0) = ( 0 + a) — (0 + b) = (0 — 0) + (a — b) = 0 + (a — b) = (a — b) = x$

$x + (-x) = (a — b) + (b — a) = (a + b) — (a + b) = (b — a) + (a — b) = 0 = (-x) + x$

$xy = (a — b)\times (c —d) = (ac + bd) — (ad + bc) = (c — d) \times (a — b) = yx$

$1x = (a — b) \times (1 — 0) = (a + 0) — (b + 0) = (1 — 0) \times (a  — b) = x1$ 

$x(y + z) = xy + xz = (a —b)\times [(c — d) + (e — f)] = (a — b) \times [(c + e) — (d + f)]$

$ =[a \times (c + e) + b \times (d + f)] — [ b \times (c + e) + a \times(d + f)] $

$ = (a — b) \times (c + e) — (a — b) \times (d + f) = xy + xz$

$(y + z) x = x(y + z) = xy + xz = yx + zx$



**4.1.5**

**证明：**

假设 $ab = 0, a \neq 0, b \neq 0$

当 $a , b \in \mathbb{N}$ 时，显然 $a, b$ 中必然有一个为0。

当 $a, b \in \mathbb{-N}$ 时，也显然 $a, b$ 中必然有一个为0。

当 $a \in \mathbb{N}, b \in \mathbb{-N}, ab = 0, b' = -b, b' \in \mathbb{N}$

$ab = 0 = -0 = - ab = ab', a, b'$中必须有一个为0,得证。



**4.1.6**

**证明：**

$ac = bc \Rightarrow  ac — bc = 0 \Rightarrow c(a —  b) = 0, c \neq 0 \Rightarrow a — b = 0, a = b$ 得证。



**4.1.7**

**证明：**

$a > b \Rightarrow a \neq b, a = b + m, m \in \mathbb{N^+}, a - b = m$ 得证。

$a = b + m, m \in \mathbb{N^+}, a + c = b + c + m, \Rightarrow a + c > b+ c$

$a > b, a = b + m, m \in \mathbb{N^+}, ac = bc + cm, \because c \in \mathbb{N^+} \therefore cm \in \mathbb{N^+}, ac > bc$ 

$a > b, a = b + m, m \in \mathbb{N^+}, - a = - b - m,  -a + m = -b, -a < -b$ 得证。

$a > b, b > c, a = b + m, b = c + n, m, n \in \mathbb{N^+}, \therefore m + n \in \mathbb{N^+} a = c + n+m$ 得证。

$a - b = a + (-b)$ 那么必然有以下三者之一：

$a - b = 0, a - b < 0, a - b > 0$ 得证。



**4.1.8**

**证明：**

$n = 0$ 时 $P(0)$ 成立，

 $n = k$ 时,  $P(k)$ 成立， $P(k++)$ 成立，但是这个推倒不出来 $P(-1)$成立，因为 $0$ 不是任何自然数的后继。



## 有理数

**4.2.1**

**证明：**

$a//b  = c //d \Rightarrow ad = bc \Rightarrow bc = ad \Rightarrow c//d = a//b$ 对称性得证。

$ab = ab, a//b = a//b$ 自反性得证。

$a//b = c//d, c//d = e//f, ad = bc, cf = ed \Rightarrow c = ed//f, ad = b\times (ed //f) = bed //f$

$a = be //f , a//b = e//f$ 得证。



**4.2.2**

**证明：**

需证明：$(a'//b') \times (c//d) = (a'c) //(b'd) = (ac)// (bd)$

$a'cbd = b'dac \because a'b = ab' /therefore a'b \times cd = ab' \times cd. \square$  

要证明：$-(a // b) = :(-a) // b$

首先 $a//b + [-(a//b)] = 0$

$a // b + (-a)//b = [a + (-a)] // b = 0$

显然 $a //b = a // b \therefore -(a//b) = (-a) // b$



**4.2.3**

**证明：**

此题目下，统一设定 $x = a //b, y = c //d, z = e // f$

$x + y = a//b + c //d = (ad + bc) // bd = (bc + ad)// db = c//d + a//b = y + x$

$x + 0 = a//b + 0//g = (ag + 0)// bg = a // b = x$

由上一问，$x + 0 = 0 + x$

$(a//b) \times (c//d) = ac // bd = ca //db = yx$

$(xy)z = x(yz) \Rightarrow (ac//bd)\times(e//f) = ace//bdf = (a//b) \times(ce//bd) = x(yz)$

$1 \times x = (1//1)\times (a//b) = a // b = x = x \times 1$

$x(y + z) = (a//b) \times [(cf + ed)// df] = [(acf + aed)] // bdf = acf // bdf + aed // bdf = ac//bd + ae//bf = xy + xz$

根据4.2.4.5 $x(y+z) = (y + z)x = xy + xz = yz + zx$

若 $x \neq 0 \Rightarrow a//b \neq 0 \Rightarrow a \neq 0$

$a // b \times (b // a) = ab // ab = 1$ 得证。



**4.2.4**

**证明：**

根据有理数的定义，有 $x = a // b$

我们有以下几种情况。$a > 0, a = 0, a < 0, b > 0, b < 0$ 进行排列组合。

设 $\exist m, n \in \mathbb{N^+} $

$a > 0, b > 0$ 时，$a = m, b = n, m//n >0$

$a < 0, b < 0$ 时，$a = -m, b = -n, a //b = (-m)// (-n) = m //n > 0$

$a = 0, b > 0$ 或者 $a = 0, b < 0$ 时， $a // b = 0$ 显然成立。

$a > 0, b < 0$ 时，$a = m, b = -n, a //b = m // (-n) < 0$

$a < 0, b > 0$ 时，$a = -m, b = n, a// b = (-m) // n < 0$ 成立。



**4.2.5**

**证明：**

1. 令 $x - y = z$ ,$z \in \mathbb{Q}, z > 0 \vee z < 0 \vee z =0$

   $\therefore  when\  z = 0, x = y, when\ z < 0, x < y, when\ z > 0, x > y$ 得证。

2. $x < y \Rightarrow x - y = z, z \in \mathbb{Q}, z < 0 \Rightarrow y - x = (-z), (-z) > 0, y > x$ 得证。

3. $x < y \Rightarrow y - x = p, p \in \mathbb{Q^+}, y < z \Rightarrow z - y = q, q \in \mathbb{Q^+}$

   $z - x = p + q, \because p \in \mathbb{Q^+}, q \in \mathbb{Q^+} \Rightarrow p + q \in \mathbb{Q^+}$ 得证。

4. 设 $x = a // b, y = c //d, a, b, c, d \in \mathbb{Z}$

   $y - x = (cb - ad) // bd, bd > 0, cb -ad > 0$

   $(x + z) - (y + z) = (x - y) -( z - z) = x - y = (ad -cb) // bd < 0$ 得证。

5. $x < y, y - x = p, p \in \mathbb{Q^+}$

   $z = c // d, pz = (a // b)  \times (c // d) > 0$ 得证。



**4.2.6**

**证明：**

令 $ z = (-e)// f, z < 0$ 

$x < y, y - x =p > 0, p \in \mathbb{Q^+}, z(y -z) = p \times z = (a // b) \times (-e) // f = (-ad) // bf$

$bf > 0, ad > 0, -ad < 0 \Rightarrow pz < 0 \Rightarrow zy < xz$ 得证。









 



