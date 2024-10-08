# Prelude

## The construct of CPU

<img src="../assets/image-20240918100432482.png" alt="image-20240918100432482" style="zoom:80%;display:block;margin:0 auto;" />

## Memory

<img src="../assets/image-20240918100512278.png" alt="image-20240918100512278" style="zoom:80%;display:block;margin:0 auto;" />

* 易失性的访问快，非易失性访问速度慢

## Instruction set architecture

<img src="../assets/image-20240918101134254.png" alt="image-20240918101134254" style="zoom:80%;display:block;margin:0 auto;" />

* 软件和硬件的接口：关注指令集

## 机器语言、汇编语言、高级编程语言

<img src="../assets/image-20240918101621874.png" alt="image-20240918101621874" style="zoom:80%;display:block;margin:0 auto;" />

## Technologies for Building Processors and Memory

集成电路加工绕不开的一个话题就是硅晶加工，硅晶锭(silicon crystal ingot)会被加工成硅片(silicon wafer)，然后再进行加工，最后成为集成电路。一个硅片会被切成很多小块，其中难免有一些坏的(defects)，而那些好的就被称为 dies，或者说 chips。而这个工艺的产量则由下面这个公式定义：

<img src="../assets/image-20240918124707583.png" alt="image-20240918124707583" style="zoom:80%;display:block;margin:0 auto;" />

最后一个式子基于经验观察得到，其中指数实际上与加工步骤数量有关。

## Response Time and Throughput

<img src="../assets/image-20240918110737461.png" alt="image-20240918110737461" style="zoom:80%;display:block;margin:0 auto;" />

* Rplacing the processor with a faster version -> Response Time and Throughput
* Adding more processors -> Throughput

## Relative Performance

<img src="../assets/image-20240918111249709.png" alt="image-20240918111249709" style="zoom:80%;display:block;margin:0 auto;" />

衡量计算机的性能和表现，无论对于工程师还是消费者都是一个非常必要的需求。其中一个重要的标准就是“运行速度”，具体来说：

- **Response Time / Execution Time** 从程序开始到结束的时间
- **Throughput / Bandwidth** 单位时间内完成的任务数量

并且我们这样联系 performance 和 execution time：
$$
Performance_X=\frac 1 {Execution \; time_X}
$$

## CPU Time

<img src="../assets/image-20240918112202813.png" alt="image-20240918112202813" style="zoom:80%;display:block;margin:0 auto;" />

* CPU (execution) time（CPU 执行时间）
* CPU clock cycle（时钟周期数）
* clock rate（时钟频率） / clock cycle time（时钟周期）

因此，我们可以得到一个关系式：
$$
CPU \; (ececution) \; time=CPU \; clock \; cycles \times Clock \; cycle \; time
$$
也就是说，CPU 的运行时间是 **CPU 时钟周期数**乘上**时钟周期**

与此同时，我们也可以将 CPU 的**时钟周期**以及**时钟频率**进行一个转换
$$
CPU \; (ececution) \; time=\frac {CPU \; clock \; cycles} {Clock \; rate}
$$


## Instruction Count and CPI

在每一个时钟周期中，我们也可以把 CPU 的执行周期数量看成 CPU 执行指令集的过程，于是，我们有下列公式
$$
CPU\;clock\;cycles=Instruction\;count \times cycles\;per\;instruction
$$
**其中，cycles per instruction 又被称为 CPI**，这个公式意味着 CPU 的执行周期数量等于总指令数量乘以每一个指令所对应的周期数量

因此，我们又可以将 CPU 的运行时间写作下列方式
$$
CPU\;time=Instruction\;count \times CPI \times Clock\;cycle\;time=\frac {Instruction\;count \times CPI}{Clock\;rate}
$$


## Amdahl's Law

<img src="../assets/image-20240925101004062.png" alt="image-20240925101004062" style="zoom:80%;display:block;margin:0 auto;" />

## Eight Great Ideas

<img src=".。/assets/image-20240925101142920.png" alt="image-20240925101142920" style="zoom:80%;display:block;margin:0 auto;" />

## Homework

<img src="./assets/image-20240925102921070.png" alt="image-20240925102921070" style="zoom:80%;" />

转成pdf上传学在浙大
