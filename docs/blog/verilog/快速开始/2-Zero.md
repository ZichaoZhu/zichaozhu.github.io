# Zero

## Problem Statement

>Build a circuit with no inputs and one output that outputs a constant `0`
>
>Now that you've worked through the previous problem, let's see if you can do a simple problem without the hints.

## 题目代码

```verilog
module top_module(
    output zero
);// Module body starts after semicolon

endmodule
```

## 解答

和上题一样

```verilog
module top_module(
    output zero
);// Module body starts after semicolon
	assign zero=1'b0;
endmodule
```

