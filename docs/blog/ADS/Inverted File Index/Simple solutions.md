# Simple solutions

*The real key technique used by search engines*

## The tool needed

### Spider

<img src="../assets/image-20240922194547983.png" alt="image-20240922194547983" style="zoom:67%;display:block;margin:0 auto;" />

It's a tool to help you fetch web pages from the Internet.

## How can we get the page which contain "Computer Science"

### Scan each page for the string "Computer Science"

### Term-Document Incidence Matrix

<img src="../assets/image-20240922202325697.png" alt="image-20240922202325697" style="zoom:50%;display:block;margin:0 auto;" />

> How can we get the passage which contains both "silver" and "truck"?
>
> <img src="../assets/image-20240922202521316.png" alt="image-20240922202521316" style="zoom:80%;display:block;margin:0 auto;" />

* 但是，这样的方式会造成表格中有很多个0，进一步导致空间、时间的浪费

## Compact Version - Inverted Index

### What is index?

Index is a mechanism for locating given term in a text.

简单来说，index就是指针，用来指示一个值的位置

### What is Inverted file

Inverted file contains a list of pointers to all occurrences of that term in the text.

<img src="../assets/image-20240922203215728.png" alt="image-20240922203215728" style="zoom:80%;display:block;margin:0 auto;" />

#### Term Dictionary

<img src="../assets/image-20240922204010406.png" alt="image-20240922204010406" style="zoom:80%;display:block;margin:0 auto;" />

> 第二列是Term Dictionary，第二列是Posting list
>
> <x; (a11;a12),(a21,a22),...,(an1,an2)>
>
> x意味着总频率，就是这个数在文本中出现了几次
>
> an1;an2意味着在第an1个文档中出现，出现的次数是an2次

* 当查找的时候，我们可以从频率小的关键词开始查询，减少总共的查询次数

## Index generator

Inverted file index也被称为index generator

### 伪代码

<img src="../assets/image-20240923140955663.png" alt="image-20240923140955663" style="zoom:67%;display:block;margin:0 auto;" />

<img src="../assets/image-20240923141201750.png" alt="image-20240923141201750" style="zoom:67%;display:block;margin:0 auto;" />

## Problem

### 1

<img src="../assets/image-20240923141942172.png" alt="image-20240923141942172" style="zoom:67%;display:block;margin:0 auto;" />

D

最后不需要计算精度