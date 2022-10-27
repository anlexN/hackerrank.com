### [Lego Blocks](https://www.hackerrank.com/challenges/one-month-preparation-kit-lego-blocks/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-four)

[Lego Blocks - Dynamic Programming](https://stackoverflow.com/questions/15424945/lego-blocks-dynamic-programming)

First, let's see how many $M * N$ walls can we build if we neglect the need to keep them connected:

We can treat each row separately, and then multiply the counts since they are independent.

There is only one way to tile a $0 * 1$ or a $1 * 1$ wall, and the number of ways to tile an $n * 1$ is the total of the number of ways to tile $\{n-1\} * 1...\{n-4\} * 1$-sized walls, the reason being these walls can be obtained by removing the last tile of the $n*1$ wall.

> 铺设 $0 * 1$ 或 $1 * 1$ 墙的方法只有一种，铺设 n*1 的方法是铺设{n-1} * 1...{n-4} * 1 大小的墙的方法的总和，原因是这些墙可以通过移除 $n * 1$ 墙的最后一块瓷砖得到。

This gives rise to a tetranacci sequence, [OEIS A000078](http://oeis.org/A000078). The number of all $W * H$ walls is $a(w,h)=T(w)^h$.

> 这就产生了一个特拉纳奇序列，[OEIS A000078](http://oeis.org/A000078)。所有 $W * H$ 墙的数量是 $a(w,h)=T(w)^h$。

Now, to count the number of solid walls. MBo's answer already contains the basic premise:

Branch on the leftmost place where the wall is not connected. The number of All $W * H$ walls is the number of Solid $X * H$ walls times the number of All $\{W - X\} * H$ walls, summed across all possible values of $X$, plus the number of Solid $W * H$ walls:

```javascript
A(W,H) = sum{X=1..{W-1}}(S(X,H)*A(W-X,H)) + S(W,H)
```

As a last step, we separate $S(M,H)$ term, which is the value we want to calculate, and repeat the previous formulas:

```javascript
S(W,H) = A(W,H) - sum_x( S(X,H)*A(W-X,H) ) //implicitly, S(1,H)=1

A(W,H) = T(W)^H

T(X)   = X > 0: T(X-1)+T(X-2)+T(X-3)+T(X-4)
         X = 0: 1
         X < 0: 0
```         
(proving MBo's formula correct).

This also provides an `O(W^2)` algorithm to compute `S` (assuming proper memoization and constant-time arithmetic operations)

[combination problem on Lego blocks](https://math.stackexchange.com/questions/1841028/combination-problem-on-lego-blocks)

> You have 4 types of lego blocks, of sizes given in $length \times width \times height$ as $1 \times 1 \times 1$, $2 \times 1 \times 1$, $3 \times 1 \times 1$, and $4 \times 1 \times 1$. Assume that you have an infinite number of blocks of each type.
> Using these blocks, you want to make a wall that is rectangular parallelepiped of height N and length M and width 1 without any holes and notches. The wall you build should be one solid structure. A solid structure can be interpreted in one of the following ways:
> It should not be possible to separate the wall along any vertical cut without cutting any lego block used to build the wall.
> You cannot make a vertical cut from top to bottom without cutting one or more lego blocks.
> The blocks can only be placed in such a way that the lenght, width and height of a block are parallel to the length, width and height of the wall. In how many ways can the wall be built?

From this follows that the third dimension of the wall is $1$ because it is explicitly mentioned. I think one cannot get this from the original text if one does not make some assumptions based on the experience with building lego walls in the childhood.

Because the problem is not affected by the width it can be view as a two dimensional tiling problem, And because height dimension of the blocks also does not affect the problem, it can be viewed as one dimensional problem.

[based on official editorial](https://www.hackerrank.com/challenges/one-month-preparation-kit-lego-blocks/editorial)
By projecting the wall onto 2D plane, the question becomes how to use $1 \times 1, 1 \times 2, 1 \times 3$ and $1 \times 4$ lego blocks to solidly cover a $H \times W$ rectangle without any holes or overlapping.

Please refer to the figure below for an example of the first test case, where the first three embeddings are valid, but the last is not since it is not solid.

#### $n: 2 \quad m: 2$

Good layouts

![n 2 m 2 good layouts](./n%202%20m%202/good.png)

Bad layouts

![n 2 m 2 bad layouts](./n%202%20m%202/bad.png)

Before solving this problem, let's consider a simpler version, which ignores the solid condition for a while. Now, the problem is decomposable, i.e., each row is an independent (same) subproblem. In other words, if we use $f[i]$ to denote # of ways to cover a $1 \times i$ bar, and let $g[i]$ be # of ways to cover a $N \times i$ rectangle ignoring the "solid" condition. Then,

$\Large g[i] = f[i]^N$

**Recurrence of $f[i]$**

Since there cannot be any holes for the embedding, we have to put a lego-slice (**_note that_**, we only have 4 types of lego blocks $1 \times 1, 1 \times 2, 1 \times 3$ and $1 \times 4$), say $1 \times k$ (**_so that_** $k \in 1, 2, 3, 4$), at the very left of the bar. Then, the length of the uncovered bar becomes $i \times k$, and obviously we have $f[i - k]$ different ways to cover. Therefore,

![f[i] formula](./f%5Bi%5D%20formula.png)

Let's list some cases:

![f[1]](./f%5B1%5D.png)

![f[2]](./f%5B2%5D.png)

![f[3]](./f%5B3%5D.png)

![f[4]](./f%5B4%5D.png)

![f[5]](./f%5B5%5D.png)

Now you should understand why this formula is true, why $f[0] = 1$. These two why are very important. If you don't still understand. please tell me.

**Back to the primal problem**

$g[M]$ gives us # of ways to embed a $N \times M$ block without the "solid" condition. However, we can easily remove those invalid (unsolid) cases from $g[M]$. Let $h[i]$ denote # of solid embedding of a $N \times i$ retangle.

For those unsolid embedding of $N \times i$ size , we enumerate all the leftmost cuts that split the wall into two parts without damaging any lego-slices. Assume the block to the left of the cut has width $j$. the current cut (see the figure below), and consequently, the one to the right has width $i - j$. Since the cut we just made is assumed to be the leftmost one, the left block has to be a solid (valid) one, and hence has $h[j]$ different ways of embedding. On the other hand, there is no particular constraint on the right one, and thus $g[i - j]$ choices.

![Back to the primal problem](61b.png)

In such a case, the rule of product applies, and therefore

$h[i] = g[i] - \displaystyle\sum_{j=1}^{i-1} h[j] * g[i-j]$

1. $g[i] = h[i] + \displaystyle\sum_{j=1}^{i-1} h[j] * g[i-j]$
2. $g[1] = h[1] = 1$ (no matter what $N$ is).

> Note
>
> In the real life,
> * we only have 2 ways to divide lego block: from the left to right or from the right to left. Now we choose "**from the left to right**". Because if you divide from the two side, we can not eliminate counting of repetitive variants or say it is very difficult task.
> * now we only can divide intact part that is solid structure.

Let's list some cases: $N = 1,2,3,4,5$ for $H[1]$ from left to right.

![H[1]](./H%5B1%5D.png)


You only can place $1 \times 1$ one by one to make a wall to shape height $N$, we have no less than $1 \times 1$ lego blocks, and we can not divide $1 \times 1$ lego block. so it is solid. so the number of valid $ N \times 1$ wall is $1$.

**Let's list some cases: $N = 3$ for $H[2]$.**

*Good layouts:*

(you can not divide intact part for $ 3 \times 1$, or say it can not be divided vertically across all rows.)

![n 3 m 2 good layouts](./n%203%20m%202/good.png)

*Bad layouts:*

you can divide intact part for $ 3 \times 1$ from the leftmost, or say it can be divided vertically across all rows from the leftmost.

![n 3 m 2 good layouts](./n%203%20m%202/bad.png)

so the number of valid $N = 3$ for $H[2]$ is $7$.


**Let's list some cases: $N = 2$ for $H[3]$.**

*Good layouts*

![n 2 m 3 good layouts](./n%202%20m%203/good.png)


*Bad layouts:*

We have has $4$ different ways to divide in $j = 1$.

![n 2 m 3 bad layouts j 1](./n%202%20m%203/bad/j%201.png)

We have has $3$ different ways to divide in $j = 2$.

![n 2 m 3 bad layouts j 1](./n%202%20m%203/bad/j%202.png)

so the number of valid $N = 2$ for $H[3]$ is $9$.

The final answer will be $h[M]$, and be careful to deal with modulo when subtraction exists. :smile:

> you must use BigInt, like 0n, 1n, 1000000007n, because question compute big number and this is a javascript feature that different than other languages like c++, python and pay attention to data overflow, seek mod first, and then check it again, because the negative balance in Python will automatically become an integer, such as -5 % 3 = 1 but java and javascript not.

```js
function legoBlocks(n, m) {
  let mod = 1000000007n,
      f = new Array(m + 1).fill(1).map(_ => 1n),
      g = new Array(m + 1).fill(0).map(_ => 0n),
      h = new Array(m + 1).fill(1).map(_ => 1n);

  f[2] = 2n, f[3] = 4n;
  
  for (let i = 4; i < m + 1; i++) {
    f[i] = (f[i - 1] + f[i - 2] + f[i - 3] + f[i - 4]) % mod
  }


  for (let i = 1; i < m + 1; i++) g[i] = power(f[i], n);

  for (let i = 2; i < m + 1; i++) {
    h[i] = g[i];

    for (let j = 1; j < i; j++) {
      h[i] -= h[j] * g[i - j];
      h[i] %= mod;
      h[i] = (h[i] + mod) % mod;
    }
  }

  return h[m];

  function power(base, exponent) {
    let ans = 1n;
    base = BigInt(base);

    while (exponent) {
      // I think because question need be moduled, these two steps is time consumed.
      // if (exponent % 2) ans = ans * base;
      // base = base * base;

      if (exponent % 2) ans = ans * base % mod;
      base = base * base % mod;
      exponent = parseInt(exponent / 2);
    }

    return ans;
  }

}
```