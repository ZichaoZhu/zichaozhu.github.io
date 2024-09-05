# Carry-select adder

## Drawback of the ripple carry adder

One drawback of the ripple carry adder (See [previous exercise](https://hdlbits.01xz.net/wiki/module_add)) is that the delay for an adder to compute the carry out (from the carry-in, in the worst case) is fairly slow, and the second-stage adder cannot begin computing *its* carry-out until the first-stage adder has finished. This makes the adder slow. 

## Improvement

One improvement is a carry-select adder, shown below. The first-stage adder is the same as before, but we duplicate the second-stage adder, one assuming carry-in=0 and one assuming carry-in=1, then using a fast 2-to-1 multiplexer to select which result happened to be correct.

<img src="../assets/image-20240903133028408.png" alt="image-20240903133028408" style="zoom:80%;display:block;margin: 0 auto;" />

## Problem statement

> In this exercise, you are provided with the same module `add16` as the previous exercise, which adds two 16-bit numbers with carry-in and produces a carry-out and 16-bit sum. You must instantiate *three* of these to build the carry-select adder, using your own 16-bit 2-to-1 multiplexer.
>
> Connect the modules together as shown in the diagram below. The provided module `add16` has the following declaration:
>
> ```verilog
> 
> module add16 ( input[15:0] a, input[15:0] b, input cin, output[15:0] sum, output cout );
> ```

```verilog
module top_module(
    input [31:0] a,
    input [31:0] b,
    output [31:0] sum
);

endmodule
```

## Solution

```verilog
module top_module(
    input [31:0] a,
    input [31:0] b,
    output [31:0] sum
);
    wire sel;
    wire [15:0] sum_0,sum_1;
    add16 inst1 (a[15:0],b[15:0],0,sum[15:0],sel);
    add16 inst2 (a[31:16],b[31:16],0,sum_0);
    add16 inst3 (a[31:16],b[31:16],1,sum_1);
	always @* begin
        case(sel)
        	0: sum[31:16]=sum_0;
        	1: sum[31:16]=sum_1;
    	endcase
	end
endmodule
```

* 请注意always语句的结构
