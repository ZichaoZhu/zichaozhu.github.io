# Leftist Heap: Definition

## Target

我们都知道，数据结构中学习过的Heap已经让我们的查找、删除、插入操作变为了**$\log(N)$**级别的。而Leftist Heaps诞生的最大目的是为了加快merging(合并)这一操作($O(N)$)

> Qustion: How fast can we merge two heaps if we simplt use the orignal heap structure?
>
> $\Theta(N)$
>
> 我们可以将两个heap先放在一个数组中，然后再调用Buildheap，这一操作的时间复杂度是$\Theta(N)$

### 特点

* 还具备着和heap一样的性质（键值最小或者最大）
* 还是一个二叉树，但是是**unbalanced**，而且向左偏

## Properties

### null path length, Npl(X) 

<img src="../assets/image-20241006201622712.png" alt="image-20241006201622712" style="zoom:80%;display:block;margin:0 auto;" />
$$
Npl(X)=min\{\;Npl(C)+1\;for\;all\;C\;as\;children\;of\;X\; \}
$$

## Definition of Leftist Heaps

<img src="../assets/image-20241006202022844.png" alt="image-20241006202022844" style="zoom:80%;display:block;margin:0 auto;" />

* The tree is biased(偏向的) to get deep toward the left.

> Theorem:
>
> <img src="../assets/image-20241006202942335.png" alt="image-20241006202942335" style="zoom:80%;display:block;margin:0 auto;" />

## Problem

### 1

<img src="../assets/image-20241006212153767.png" alt="image-20241006212153767" style="zoom:80%;display:block;margin:0 auto;" />

> A.
>
> 使用递归。假设r的时候成立，当是r+1的时候，我们知道右子树的Npl必定是r，因此右子树至少有$2^r-1$个节点。我们知道$Npl_{left}\geq Npl_{right}$，所以左边也至少有$2^r-1$个节点，于是总共就有节点
> $$
> 2^r-1+2^r-1+1=2^{r+1}-1
> $$