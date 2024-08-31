# Vector reversal 1

## Problem statement

>  Given an 8-bit input vector [7:0], reverse its bit ordering

```verilog
module top_module( 
    input [7:0] in,
    output [7:0] out
);

endmodule
```

## Hints

- `assign out[7:0] = in[0:7];` does not work because Verilog does not allow vector bit ordering to be flipped.
- The concatenation operator may save a bit of coding, allowing for 1 assign statement instead of 8.

也就是说，我们不能像在python一样使用字符串的逆序来直接解决问题了，因为在verilog中，一个向量的方向是固定的，定义的时候是[7:0]，但使用的时候是[0:7]是不被允许的。

看起来题目是要我们使用**vector concatenation operator**来解决了。

## Solution

```verilog
module top_module( 
    input [7:0] in,
    output [7:0] out
);
    assign out={in[0],in[1],in[2],in[3],in[4],in[5],in[6],in[7]};
endmodule
```

## How to use loop to duel with this problem?

### for-loops

> Create a combinational always block. This creates combinational logic that computes the same result as sequential code. 
>
> * for-loops describe circuit *behaviour*, not *structure*, **so they can only be used inside procedural blocks** (e.g., always block).
>
> The circuit created (wires and gates) does NOT do any iteration: It only produces the same result
>
> AS IF the iteration occurred. In reality, a logic synthesizer will do the iteration at compile(编译) time to figure out what circuit to produce. (In contrast, a Verilog simulator will execute the loop sequentially during simulation.)

```verilog
always @(*) begin	
	for (int i=0; i<8; i++)	// int is a SystemVerilog type. Use integer for pure Verilog.
		out[i] = in[8-i-1];
end
```

### generate-for loop

> It is also possible to do this with a generate-for loop. Generate loops look like procedural for loops, but are quite different in concept, and not easy to understand. 
>
> Generate loops are used to make instantiations of "things" (Unlike procedural loops, it doesn't describe actions). These "things" are assign statements, module instantiations, net/variable declarations, and procedural blocks (things you can create when NOT inside a procedure). 
>
> Generate loops (and genvars) are evaluated entirely at compile time. You can think of generate blocks as **a form of preprocessing to generate more code**, which is then run though the logic synthesizer. 

也就是说，对于generate-for loop来说，本质上是在编译阶段将代码**重复生成**了几遍

In the example below, the generate-for loop first creates 8 assign statements at compile time, which is then synthesized.

```verilog
generate
	genvar i;
	for (i=0; i<8; i = i+1) begin: my_block_name
		assign out[i] = in[8-i-1];
	end
endgenerate
```

Note that because of its intended usage (generating code at compile time), there are some restrictions on how you use them.

* Quartus requires a generate-for loop **to have a named begin-end block attached** (in this example, named "my_block_name").
* Inside the loop body, genvars are **read only**.