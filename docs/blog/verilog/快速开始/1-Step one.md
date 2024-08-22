# 第一个内容

## Problem Statement

>We're going to start with a small bit of HDL to get familiar with the interface used by HDLBits. Here's the description of the circuit you need to build for this exercise:
>
>Build a circuit with no inputs and one output. That output should always drive 1 (or logic high).

## 题目代码

```verilog
module top_module( output one );

// Insert your code here
    assign one = [fixme];

endmodule
```

## 分析

可以看到`assign one = [fixme];`这段明显是要我们填入一个高电位。

## 答案

```verilog
module top_module( output one );
	
	assign one = 1'b1;
	
endmodule
```

* 注意：赋值的时候需要确定比特位数