# Modules and vectors

## What is the aim of this part?

This exercise is an extension of [module_shift](https://hdlbits.01xz.net/wiki/module_shift). Instead of module ports being only single pins, we now have modules **with vectors as ports**, to which you will **attach wire vectors instead of plain wires**. Like everywhere else in Verilog, the vector length of the port does not have to match the wire connecting to it, but this will cause zero-padding or trucation of the vector. This exercise does not use connections with mismatched vector lengths.

## Problem statement

> You are given a module `my_dff8` with two inputs and one output (that implements a set of 8 D flip-flops). Instantiate three of them, then chain them together to make a 8-bit wide shift register of length 3. In addition, create a 4-to-1 multiplexer (not provided) that chooses what to output depending on `sel[1:0]`: The value at the input d, after the first, after the second, or after the third D flip-flop. (Essentially, `sel` selects how many cycles to delay the input, from zero to three clock cycles.)
>
> The module provided to you is: `module my_dff8 ( input clk, input [7:0] d, output [7:0] q );`
>
> The multiplexer is not provided. One possible way to write one is inside an `always` block with a `case` statement inside. (See also: [mux9to1v](https://hdlbits.01xz.net/wiki/mux9to1v))

```verilog
module top_module ( 
    input clk, 
    input [7:0] d, 
    input [1:0] sel, 
    output [7:0] q 
);
    
endmodule
```

## Solution

```verilog
module top_module ( 
    input clk, 
    input [7:0] d, 
    input [1:0] sel, 
    output [7:0] q 
);
    wire  [7:0] w1, w2, w3;
    my_dff8 inst1 (clk, d, w1);
    my_dff8 inst2 (clk, w1, w2);
    my_dff8 inst3 (clk, w2, w3);
    always @* begin
        case(sel)
            0: q = d;
            1: q = w1;
            2: q = w2;
            3: q = w3;
        endcase
    end
endmodule
```

* 第7行中的定义方式是将w1,w2,w3全部定义成了8位

若要在一行中定义不一样位数的变量，可以使用以下方式

> ```verilog
> wire  [7:0] w1; wire w2;
> ```
>
> 其中，w1是8位的，w2是1位的

