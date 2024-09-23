# Red-Black Trees Operation

[红黑树- 插入、删除 流程详解，末尾附完整代码，及高清过程图_添加的过程讲解完毕。改天在跟大家讲删除-CSDN博客](https://blog.csdn.net/m0_52383454/article/details/126393163)

## Insertion

 <img src="../assets/image-20240917211658164.png" alt="image-20240917211658164" style="zoom:80%;display:block;margin:0 auto;" />

## Deletion

<img src="../assets/image-20240917212918333.png" alt="image-20240917212918333" style="zoom:80%;display:block;margin:0 auto;" />

## Number of rotations

<img src="../assets/image-20240917214636145.png" alt="image-20240917214636145" style="zoom:80%;display:block;margin:0 auto;" />

* When using **insertion**, AVL trees are recommended.

## Problem

### 1

In the worst case the DELETE operation in a RED-BLACK tree of *n* nodes requires Ω(log*n*) rotations.

F.

> rotation最多3次就可以了