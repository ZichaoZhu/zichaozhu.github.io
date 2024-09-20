# B+ Trees

## Definition

A B+ tree of order M is a tree with the following structural properties:
<img src="../assets/image-20240920155800064.png" alt="image-20240920155800064" style="zoom:80%;display:block;margin:0 auto;" />

* 我们不能有一个根加一个孩子的结构
* 这棵树是从下往上构建的，而非从上往下

## Operation

### Insertion

* Simple spliting method
* find a not full sibling($\times$)

<img src="../assets/image-20240920165325557.png" alt="image-20240920165325557" style="zoom:80%;display:block;margin:0 auto;" />

* 从中我们可以看到，叶子节点元素个数**最多有M**个

## Deletion

与插入相似，但在一个节点失去两个孩子后，需要删掉它

## Analysis

<img src="../assets/image-20240920165520696.png" alt="image-20240920165520696" style="zoom:80%;display:block;margin:0 auto;" />

因为在最坏的情况下，每个节点只有M/2个节点

<img src="../assets/image-20240920170023112.png" alt="image-20240920170023112" style="zoom:80%;display:block;margin:0 auto;" />

## Problem

### 1

<img src="../assets/image-20240920192741785.png" alt="image-20240920192741785" style="zoom:80%;display:block;margin:0 auto;" />

D

> Don't know.

### 2

<img src="../assets/image-20240920192922468.png" alt="image-20240920192922468" style="zoom:80%;display:block;margin:0 auto;" />

A

> 很简单，定义