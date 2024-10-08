# Skew Heaps

## Definition

A simple version of the leftist heaps, don't care about the Npl.

### Target

<img src="../assets/image-20241007195627374.png" alt="image-20241007195627374" style="zoom:67%;display:block;margin:0 auto;" />

### The merge method

<img src="../assets/image-20241007195755544.png" alt="image-20241007195755544" style="zoom:80%;display:block;margin:0 auto;" />

* 需要注意的是，skew heap右边路径最大的节点不需要交换左右孩子

> Ex
>
> <img src="../assets/image-20241007200006399.png" alt="image-20241007200006399" style="zoom:80%;display:block;margin:0 auto;" />
>
> 在这个例子中，对于18，35组成的子堆来说，因为18是其右边路径上最大的节点，因此我们不需要交换它的左右孩子





## Problem

### 1

<img src="../assets/image-20241007200952321.png" alt="image-20241007200952321" style="zoom:80%;display:block;margin:0 auto;" />

> B
>
> 应该是leftist heap更平衡

### 2

<img src="../assets/image-20241007201019115.png" alt="image-20241007201019115" style="zoom:80%;display:block;margin:0 auto;" />

> A
>
> 因为skew tree的交换时时都在发生，因此有可能会出现右路径特别长的情况

### 3

<img src="../assets/image-20241007205540717.png" alt="image-20241007205540717" style="zoom:80%;display:block;margin:0 auto;" />

> C
>
> B是对的，因为不需要储存Npl；C摊还时间是$O(\log N)$，最差的时间大于$\log N$；D正确

### 4

<img src="../assets/image-20241007210730408.png" alt="image-20241007210730408" style="zoom:80%;display:block;margin:0 auto;" />

> A
>
> 正确的
