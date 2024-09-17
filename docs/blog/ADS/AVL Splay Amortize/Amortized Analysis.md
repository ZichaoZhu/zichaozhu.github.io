# Amortized Analysis

## Target

Any M consecutive tree operations starting from an empty tree take at most $O(M \log N)$ time.

We have this:
$$
worst\; case\; bound \geq amortized\; bound \geq average \; case\; bound
$$

## Aggregate Analysis(总量分析)

### Idea

<img src="../assets/image-20240917133457666.png" alt="image-20240917133457666" style="zoom:67%;display:block;margin:0 auto;" />

## Accounting method(会计法)

<img src="../assets/image-20240917141031263.png" alt="image-20240917141031263" style="zoom:67%;display:block;margin:0 auto;" />

*Notice that：*

<img src="../assets/image-20240917141201082.png" alt="image-20240917141201082" style="zoom:50%;display:block;margin:0 auto;" />

> Ex: Stack with  MultiPop
>
> <img src="../assets/image-20240917141722891.png" alt="image-20240917141722891" style="zoom:67%;display:block;margin:0 auto;" />

**BUT: The most difficult part of amortized method is to guess the amortized cost**

## Potential method(势能法)

### Idea

<img src="../assets/image-20240917142147461.png" alt="image-20240917142147461" style="zoom:80%;display:block;margin:0 auto;" />

* 所以究竟什么是信用？信用是这个操作把问题结构改变了多少

<img src="../assets/image-20240917142836925.png" alt="image-20240917142836925" style="zoom:67%;display:block;margin:0 auto;" />

* we have to guess a good potantial function for the current problem structure
* So a good potential function requires that the first element  $\phi(D_0)$

> Ex: Stack with MultiPop(int k, Stack S)
>
> <img src="../assets/image-20240917144158959.png" alt="image-20240917144158959" style="zoom:40%;display:block;margin:0 auto;" />

### Ex: Splay Trees

<img src="../assets/image-20240917145515661.png" alt="image-20240917145515661" style="zoom:50%;display:block;margin:0 auto;" />

<img src="../assets/image-20240917145615208.png" alt="image-20240917145615208" style="zoom:67%;display:block;margin:0 auto;" />
$$
\hat{c_i} \leq 1+3(R_2(X)-R_1(X))
$$

* 所以总和最大就是$1+3(R_N(X)-R_1(X))$，也就是$O(\log N)$

## Problem

## 1

> When doing amortized analysis, which one of the following statements is FALSE?
>
> <img src="../assets/image-20240917152122823.png" alt="image-20240917152122823" style="zoom:80%;display:block;margin:0 auto;" />

> B
>
> The "maximum" is wrong, it should be "minimum".

## 2

> <img src="../assets/image-20240917190833469.png" alt="image-20240917190833469" style="zoom:80%;display:block;margin:0 auto;" />
>
> A. The number of items currently in the buffer
>
> B. The opposite number of items currently in the buffer
>
> C. The number of available blocks currently in the buffer
>
> D. The opposite number of available blocks in the buffer

> D
>
> <img src="../assets/image-20240917190918369.png" alt="image-20240917190918369" style="zoom:80%;display:block;margin:0 auto;" />
