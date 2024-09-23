# Topics

## Distributing indexing

### Term-partitioned index

We can make a partition(分区) of the term dictionary and store differnt subsets of terms on different machines.

<img src="../assets/image-20240923153831203.png" alt="image-20240923153831203" style="zoom:80%;display:block;margin:0 auto;" />

### Document-partitioned index

思想如上一种方法，但是分区的依据是**文件**

<img src="../assets/image-20240923154006259.png" alt="image-20240923154006259" style="zoom:80%;display:block;margin:0 auto;" />

## Dynamic indexing

### Docs come in over time

> * posting uodatas for terms already in dictionary
> * new terms added to dictionary

但是我们可以得到这样一种解决方法：auxiliary(辅助性的，附加的) index

#### Auxiliary index

<img src="../assets/image-20240923154606151.png" alt="image-20240923154606151" style="zoom:80%;display:block;margin:0 auto;" />

问题的关键在于我们的**主要数据库**太大了，插入操作相当费时间

因此我们可以先创建一个**比较小的auxiliary index**，在插入的时候先将文件插入其中，然后在合适的时候进行一个**合并的操作**

在用户查找的时候，我们可以**查询两个index**，然后再返回结果

> 但是这样也会引出两个问题：
>
> * 何时进行删除
> * 怎么进行删除

## Compression

### Store terms

如果用常规的方法去储存单词，我们会发现**空间的利用率是很低的**，因为有些单词是相当长的（100+），这就迫使我们将所有的字符串的长度定义为这么大

<img src="../assets/image-20240923160143689.png" alt="image-20240923160143689" style="zoom:80%;display:block;margin:0 auto;" />

如上图所示，我们可以把所有的单词串在一起进行存储，然后使用一个数组来储存单词首字母的位置

### Posting List store

<img src="../assets/image-20240923160350878.png" alt="image-20240923160350878" style="zoom:80%;display:block;amrgin:0 auto;" />

在之前的存储中，我们都是直接存储**文章的序号**的。但是这样的话序号很快就会超出数据的大小上限（比如，超出long long）

有一种解决方法是我们可以储存后一篇文章与前一篇文章的序号之差，这样的话可以很大的减小数据

## Thresholding

*We only concern the top x documents*

<img src="../assets/image-20240923162051843.png" alt="image-20240923162051843" style="zoom:80%;display:block;margin:0 auto;" />

## Problem

### 1

<img src="../assets/image-20240923162415780.png" alt="image-20240923162415780" style="zoom:80%;display:block;margin:0 auto;" />

A.

### 2

<img src="../assets/image-20240923162441972.png" alt="image-20240923162441972" style="zoom:80%;display:block;margin:0 auto;" />

B

> 这是document的，不是query的