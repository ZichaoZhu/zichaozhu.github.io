# Modules

## Word stemming

<img src="../assets/image-20240923142606162.png" alt="image-20240923142606162" style="zoom:80%;dsplay:block;margin:0 auto;" />

* 就是使用单词的原型

## Stop words

<img src="../assets/image-20240923142734222.png" alt="image-20240923142734222" style="zoom:80%;display:block;margin:0 auto;" />

* 去掉“a”“the“这种很简单的词

## 查询一个词的时候

### Search trees

* B- trees, B+ trees, Tries, ...

### Hashing

> Q: What are the pros and cons of using hashing, comparing to using search trees?
>
> * faster for one word
> * scanning in sequetial order is not possible(e.g. range searches are expansive)
>   * 比如，如果我们输入了一个错误的词语，按理论来讲我们应该是得不到查询结果的；但实际上，我们却可以得到相应的返回值

## Memory Management

当我们没有足够的空间的时候，我们应该怎么办呢？

<img src="../assets/image-20240923151646522.png" alt="image-20240923151646522" style="zoom:67%;display:block;margin:0 auto;" />

* 如名字所示，BlockIndex就是一块的Index
* 关键在于我们需要在一块满之后，将其写入硬盘中，释放内存，并进入下一个区块中。最后再进行一个合并
  * 在最后一步中，我们需要确保所有的block Index是有序的，这样可以让我们操作得更快

## Problem

### 1

<img src="../assets/image-20240923152544690.png" alt="image-20240923152544690" style="zoom:80%;display:block;margin:0 auto;" />

A.

> 根据B+ tree的性质可以知道，范围搜索是比较方便的。上述句子所说的应该是Hashing

### 2

<img src="../assets/image-20240923152739549.png" alt="image-20240923152739549" style="zoom:80%;display:block;margin:0 auto;" />

A

### 3

<img src="../assets/image-20240923152813374.png" alt="image-20240923152813374" style="zoom:80%;display:block;margin:0 auto;" />

B
