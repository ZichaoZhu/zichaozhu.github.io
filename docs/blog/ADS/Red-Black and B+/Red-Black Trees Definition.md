# Red-Black Trees Definition

## The definition of a Red-Black Trees

<img src="../assets/image-20240917192436095.png" alt="image-20240917192436095" style="zoom:80%;display:block;margin:0 auto;" />

* In the red-black tree, we consider every NULL pointer, every NIL, as a leaf node, and thier colr is black.
* real tree node -> "internal node"
* NIL node -> External node(leaf node)

> Ex
>
> <img src="../assets/image-20240917193003811.png" alt="image-20240917193003811" style="zoom:80%;display:block;margin:0 auto;" />
>
> A

## The black-height of Red-Black Trees(bh)

### Definition

<img src="../assets/image-20240917193809288.png" alt="image-20240917193809288" style="zoom:80%;display:block;margin:0 auto;" />

* Notice that x is not included.

## Lemma

A red-black tree with $N$ internal nodes has height at most $2\ln (N+1)$

### Proof

<img src="../assets/image-20240917204719017.png" alt="image-20240917204719017" style="zoom:80%;display:block;margin:0 auto;" />

* sizeof(x): the Number of internal nodes in the subtree rooted at x
* 根据红黑树定义的第四条，我们知道树中的某一路径的黑色节点数肯定比红色节点数多

## Problem

### 1

<img src="../assets/image-20240917205931972.png" alt="image-20240917205931972" style="zoom:80%;display:block;margin:0 auto;" />

> A
>
> 构造最短路经，路径上只有黑节点；构造最长路径，路径上是一红一黑

### 2

<img src="../assets/image-20240917210240988.png" alt="image-20240917210240988" style="zoom:80%;display:block;margin:0 auto;" />

> A
>
> 根据定义即可