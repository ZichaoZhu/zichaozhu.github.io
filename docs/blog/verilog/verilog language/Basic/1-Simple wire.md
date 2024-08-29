# Simple wire

## 什么是 wire ?

> Unlike physical wires, wires (and other signals) in Verilog are ***directional***. This means information flows **in only one direction**, from (usually one) *source* to the *sinks* (The source is also often called a *driver* that *drives* a value onto a wire). In a Verilog **"continuous assignment" (`assign left_side = right_side;`)**, the value of the signal on the right side is driven onto the wire on the left side. The assignment is "continuous" **because the assignment continues all the time even if the right side's value changes**. A continuous assignment is not a one-time event.

* wire 具有方向性，值从右到左
* continuous assignment 指的是像 **assign left_side = right_side;** 的赋值
* continuous assignment 每时每刻都在作用，左边的值随着右边的值改变

> In addition to continuous assignments, Verilog has three other assignment types that are used in procedural blocks, **two of which are synthesizable**. We won't be using them until we start using procedural blocks.

## Problem statement

>  Your task is to create a wire (in green) by adding an `assign` statement to connect `in` to `out`. 

```verilog
module top_module( input in, output out );

endmodule
```

## Solution

```verilog
module top_module( input in, output out );
	assign out=in;
endmodule
```

