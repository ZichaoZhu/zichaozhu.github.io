# Splay Trees

## Target

Any M consecutive tree operations starting from an empty tree take at most $O(M \log N)$ time.

*So AVL tree is a kind of splay tree.*

It just means that the **amortized**(摊还) time is $O(\log N)$.

> *Note*: access: 访问、接触

## Idea

After a node is accessed, it is pushed to the root by a series of AVL tree rotations.

## Insertion

For any nonroot node X, denote its parent by P and grandparent by G:

### P is the root

Rotate X and P

<img src="../assets/image-20240917124518379.png" alt="image-20240917124518379" style="zoom:80%;display:block;margin:0 auto;" />

### P is not the root

#### Zig-zag

Double rotation

<img src="../assets/image-20240917124909569.png" alt="image-20240917124909569" style="zoom:80%;display:block;margin:0 auto;" />

#### Zig-zig

Single rotation

<img src="../assets/image-20240917125048610.png" alt="image-20240917125048610" style="zoom:80%;display:block;margin:0 auto;" />

*Splaying roughly halves the depth of most nodes on the path.*

## Deletion

1. Find X

   X will be at the root.

2. Remove X

   There will be two subtrees $T_L$ and $T_R$.

3. FindMax($T_L$)

4. Make $T_R$ the right child of the root of $T_L$

## Problem

### 1

> <img src="../assets/image-20240917130350862.png" alt="image-20240917130350862" style="zoom:80%;display:block;margin:0 auto;" />

> D
>
> <img src="../assets/image-20240917131818162.png" alt="image-20240917131818162" style="zoom:40%;display:block;margin:0 auto;" />
>
> 查询完后结果如上图所示

## 2

> <img src="../assets/image-20240917132053097.png" alt="image-20240917132053097" style="zoom:80%;display:block;margin:0 auto;" />

> A
>
> 查询完后，这个最大的节点就会被当作是根。根据二叉搜索树的定义可知，这个树没有右子树

