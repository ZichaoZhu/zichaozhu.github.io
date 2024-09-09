# AVL Trees

## Why we need AVL Trees?

### Target of AVL Trees

The target of AVL Trees is to speed up searching, especially to handle dynamic searching.

#### What is dynamic searching?

Dynamic searching is a searching with **insertion** and **deletion**.

**The data set is not fixed. It's dynamic**.

> Ex: Binary search tree.
>
> In some case, we would get a skew tree which skew to one side.(也就是一棵向一边偏的树) 

### Average search time

每个节点的高度（最上方为0）+1之和/节点数

### The function of AVL tree

The function of AVL tree is to keep the tree dynamically balanced.

If the tree is not balanced, then we let them become balanced.

## The definition of AVL tree

<img src="../assets/image-20240909212116870.png" alt="image-20240909212116870" style="zoom:80%;display:block;margin:0 auto;" />

### BF (Balance factor)

<img src="../assets/image-20240909212559215.png" alt="image-20240909212559215" style="zoom:80%;display:block;margin:0 auto; />

## Single rotations

<img src="../assets/image-20240909213453301.png" alt="image-20240909213453301" style="zoom:80%;display:block;margin:0 auto;" />

### Trouble finder

The trouble finder is the first node that signals the trouble.

> Ex
>
> <img src="../assets/image-20240909214239961.png" alt="image-20240909214239961" style="zoom:80%;display:block;margin:0 auto;" />
>
> In this example, trouble finder is Mar.

## Double rotation

<img src="../assets/image-20240909215238405.png" alt="image-20240909215238405" style="zoom:80%;display:block;margin:0 auto" />
