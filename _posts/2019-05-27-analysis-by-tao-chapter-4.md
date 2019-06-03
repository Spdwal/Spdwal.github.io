---
layout: post
title: "Analysis by Tao Chapter 4"
category: 
tags: [Math]
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



## 绝对值和指数运算

**4.3.1**

**证明：**

1. 首先根据三歧性，x只有以下3种可能：$x > 0, x = 0, x < 0$。

   根据定义可得：当 $x > 0$ 时，$|x| = x > 0$ ，当 $x < 0$ 时，$|x| = -x > 0$ 。 当 $x = 0$ 时，$|x| = x = 0$ 得证。

2. 当 $x \geq 0, y \geq 0$ 时，$|x + y| = x + y = |x| + |y|$

   当 $x < 0, y \geq 0$ 时，$|x + y| < y - x = |x|  + |y|$

   当 $x \geq 0, y < 0$ 时，证明同上。

   当 $x <0, y< 0$ 时，$|x+y| = (-x) + (-y) = |x| + |y|$ 得证

3. 首先根据不等式得知 $y \geq 0$

   当$x \geq 0$ 时，$|x| = x, y \geq x \Rightarrow y \geq |x|$

   当 $x < 0$ 时，$-y \leq x < 0, y \geq (-x) > 0 ,|x| = -x \Rightarrow y \geq |x|$ 

   当 $x \geq 0, |x| = x , x \leq |x|$

   当 $x < 0, |x| = -x, x = -|x|, x \geq -|x|$ 得证。

4. $x \geq 0, y \geq 0$ 时，$|xy| = xy = |x||y|$ 

   $x < 0, y \geq 0$ 时，$|xy| = (-x)y = |x||y|$

   $x \geq0, y < 0$ 时，同上。

   $x < 0, y < 0$ 时，$|xy| = (-x)(-y) = |x||y|$ 

5. 根据此题第一问可得，$d(x,y) = |x - y| \geq 0$ ，且 $|x - y| = 0 \Leftrightarrow x - y = 0, x = 0$ 得证。

6. $d(x, y) = |x - y| , d(y, x) = |y - x|$

   当 $x \geq y$ 时，$|x - y| = x - y, |y - x| = -(y - x) = x - y \Rightarrow |x - y| = |y - x|$

   当 $x < y$ 时，证明同上。

7. 原题可转化为 $|x - z| \leq |x - y| + |y - z|$

   根据本题第二小问。$|(x - y) + (y - z)| \leq |x - y| + |y  - z| \Rightarrow |x - z| \leq |x -y| + |y - z|$ 得证。



**4.3.2**

**证明：**

1. $\because x = y, d(x, y) = 0, \forall \varepsilon \in \mathbb{Q+}, \varepsilon > 0 = d(x, y)$ 第一问得证。

   接下来证明第二问，假设 $x \neq y, d(x, y) = \vartheta > 0$

   当 $\varepsilon = \vartheta / 2 \Rightarrow \varepsilon > 0$  得证。

2. $|y - x| = |x - y| \leq \varepsilon$  得证。

3. $|x - y| \leq \varepsilon, |y - z| \leq \vartheta, |(x - y) + (y - z)| \leq |x - y| + |y - z| = \varepsilon + \vartheta$ 得证。

4. $ |x - y| \leq \varepsilon, |w -z| \leq \vartheta, |(x + z) - (y + w)| = |(x - y) + (z - w)| \leq |x - y| + |w - z| = \varepsilon + \vartheta$ 第一问得证。

   $|( x- z) - (y - w)| = |(x - y) - (w - z)| \leq \varepsilon + \vartheta$ 得证。

5. $|x - y| \leq \varepsilon < \varepsilon' \Rightarrow |x - y| < \varepsilon$ 得证。

6. $y \leq w \leq z \Rightarrow -y \geq -w \geq -z \Rightarrow x - y \geq x - w \geq x - z$

   同理，或者有 $x - z \geq x - w \geq x - y$ 

   $d = max(d(x, z), d(x, y)), -d \leq x - w \leq d, d \leq \varepsilon$

   $\Rightarrow |x - w| \leq \varepsilon$ 得证。

7. $|x - y| \leq \varepsilon, z \neq 0$

   $|zx - zy| = |z||x - y| \leq |z|\varepsilon$	 得证。



**4.3.3**

**证明：**

1. 利用数学归纳法：

   当 $n = 0, x^mx^0 = x^m \times 1 = x^m = x^{m + 0}$

   设当 $n = k$ 时，$x^mx^n = x^{mk}$ 成立。

   当 $ n = k + 1$时，$x^mx^{k+1} = x^mx^k \times x = x^{mk + 1}$ 得证。

   当 $m = 0$ 时，$(x^n)^0 = 1 = x^{n \times 0}$

   设当 $m = k$ 时，$(x^n)^k = x^{nk}$

   当$m = k + 1$ 时，$(x^n)^{k + 1} = (x^n)^k \times x^n = x^{nk} \times x^n = x^{nk + n} = x^{n(k+1)}$ 得证。

   当 $n = 0$ 时，$(xy)^n = 1 = x^0y^0$

   设当 $n = k$ 时，$(xy)^k = x^ky^k$

   当 $n = k + 1$ 时， $(xy)^{k+1} = (xy)^k \times xy = x^ky^k \times xy = x^{k+1}y^{k+1}$ 得证。

2. 当$n = 1, x^1 = x = 0$ 显然成立。

   $x^n = x^{n - 1} \times x = 0$ 显然有 $x^{n - 1} = 0 \vee x = 0$ 将 $x^{n - 1}$ 无穷分解下去，可到 $x^2 = 0 \Rightarrow x \times x = 0 \Rightarrow x = 0$  得证。

3. 当 $n = 1$ 时， $x \geq y  \geq 0$ 

   设当 $n = k$ 时，$x^k \geq y^k \geq 0$

   当 $n = k + 1$ 时，$x^{k + 1}= x^k \times x, y^{k+1} = y^k \times y, \because x^k \geq y^k \geq 0, x \geq y \geq 0$

   $\Rightarrow x^{k+1} \geq y^{k+1} \geq 0$

   第二问同理可证。

4. 当$n = 0$ 时，$|x|^0 = |x^0|$

   设 $n = k$ 时，$|x^k| = |x|^k$

   当$n = k + 1, |x^{k+1}| = |x^k \times x| = |x^k| |x| = |x|^k|x| = |x|^{k+1}$ 得证。



**4.3.4**

**证明：**

1. 设 $m = a - b, n = c -d,a, b, c, d \in \mathbb{N^+} $$x^nx^m = x^{a - b}x^{c - d} = (x^a/x^b) \times (x^c/x^d) = (x^ax^c)/(x^bx^d) = x^{a + c}/x^{b + d}$

   $= x^{a + c - b -d} =  x^{m + n}$ 

   $(x^n)^m = (x^{c - d})^{a - b} = (x^c/x^d)^{a - b} = (x^c/x^d)^a/(x^c/x^d)^b = (x^{ac}/x^{ad}) \times(x^{bd }/x^{bc})$

   $= (x^{ac + bd}) /(x^{ad + bc}) = x^{ac+bd-ad-bc} = x^{(a-b)(c-d)} = x^{mn}$ 得证。

   $(xy)^{c - d} = (xy)^c/(xy)^d = x^c/x^d \times y^c/y^d = x^{c- d}y^{c-d} = x^ny^n$ 得证。

2. 当 $n$ 为正数时，显然成立。

   当 $n  < 0$ 时，设 $n = -p, p \in \mathbb{N^+}$

   如果 $x = y, 1/x^p = 1/y^p, \because 1/x > 0, 1/y > 0, \therefore 1/x^p = 1/y^p >0$ 

   当 $x > y, (1/xy) > 0, x(1/xy) > y(1/xy) > 0, (1/y) > (1/x) > 0 \Rightarrow (1/y)^p > (1/x)^p >0$ 得证。

3. 当 $n > 0$ 时显然成立。

   当 $n < 0$ 设 $n = -p, p \in \mathbb{N^+} (1/x)^p = (1/y)^p \Rightarrow 1/x = 1/y \Rightarrow x = y$  得证。

4. 当 $n >=0$ 显然成立。

   当 $n < 0$ 时， 设 $n = -p, p \in \mathbb{N^+}$

   $1/|x^p| = 1/|x^p| \Rightarrow |x^p| = |x|^p $得证。



**4.3.5**

**证明：**

当 $N = 1$ 时， $2^1 = 2 > 1$

设当 $N = k$ 时， $2^k \geq k$

当 $N = k + 1$ 时，$2^{k + 1} = 2\times 2^k = 2 ^k  + 2^k > 2^k + 1 \geq k + 1$ 得证。

 

## 有理数中的间隙

**4.4.1**

**证明：**

 当 $x > 0$ 时，设 $x = a / b, a = bn + q, q < b, a, b,q \in \mathbb{N^+}$

$x = n + q/b, \because q < b \therefore q/b < 1, \Rightarrow n \leq n + q/b < n + 1$

当 $x < 0$ 时，设 $x = a / b$ 不妨设 $a \in \mathbb{N^-}, b \in \mathbb{N^+}, q < b, q \in \mathbb{N^+}$

$x = -n + q/b, n \in \mathbb{N^+} \Rightarrow -n \leq -n + q/b < -n+1$

当 $x = 0$ 显然 $0 \leq 0 < 1$ 得证。



**4.4.2**

**证明：**

1. 假设存在无穷递归的自然数列，假设 $\forall k \in \mathbb{N^+}, n \in \mathbb{N^+}, a_n \geq k$

   不妨设$K \in \mathbb{N^+}, a_n \geq K, a_n = K+1, a_{n+1} < a_n = K + 1$

   $a_{n+1} \leq K, a_{n+2} < K$ 当取 $K = 0$ 必然存在 $a_n < K = 0$ 此时 $a_n \notin \mathbb{N}$ 与自然数列矛盾，得证。

2. 如果换成整数数列的话，成立，因为存在 $a_n < K = 0, a \in \mathbb{Z}$ 矛盾不成立。

   如果换成正有理数，还是成立。

   可以假设 $a_n = 1/n , n\in \mathbb{N^+}$

   $a_1 = 1, a_n = 1/n, a_{n+1} = 1/(n+1), a_n - a_{n+1} = 1/[(n+1)n] >0$ 得证。



**4.4.3**

**证明：**

1. 此题需证明自然数不能既是奇数又是偶数。

   假设存在这样的数 $p, p = 2k_1, p = 2k_2 + 1, p, k_1, k_2 \in \mathbb{N}$

   两式相减 $0 = 2(k_1 - k_2) - 1, k_1 - k_2 = 1/2$ 与两自然数相减为一个整数矛盾。所以自然数不能即是奇数又是偶数

2. 设 $p = 2k + 1, p^2 = 4k^2 + 2k + 1$ 令 $K = 2k^2 + k, p^2 = 2K + 1$ 得证。

3. $p^2 - q^2 = q^2 \geq 0, p^2 \geq q^2 p,q\in \mathbb{N^+}, p \geq q$ 等号只有在$q^2 = 0, q= 0$ 时才成立，由于 $p, q \in \mathbb{N^+}$

   所以等号不成立，得证。

   

