# Wire

## 什么是 wire ?

> Unlike physical wires, wires (and other signals) in Verilog are ***directional***. This means information flows **in only one direction**, from (usually one) *source* to the *sinks* (The source is also often called a *driver* that *drives* a value onto a wire). In a Verilog **"continuous assignment" (`assign left_side = right_side;`)**, the value of the signal on the right side is driven onto the wire on the left side. The assignment is "continuous" **because the assignment continues all the time even if the right side's value changes**. A continuous assignment is not a one-time event.

* wire 具有方向性，值从右到左
* continuous assignment 指的是像 **assign left_side = right_side;** 的赋值
* continuous assignment 每时每刻都在作用，左边的值随着右边的值改变