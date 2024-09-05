# Adder-subtractor

## What is adder-subtractor?

An adder-subtractor can be built from an adder by optionally negating one of the inputs, which is equivalent to inverting the input then adding 1. The net result is a circuit that can do two operations: (a + b + 0) and (a + ~b + 1). See [Wikipedia](https://en.wikipedia.org/wiki/Adder–subtractor) if you want a more detailed explanation of how this circuit works.

## Problem statement

> Build the adder-subtractor below.
>
> You are provided with a 16-bit adder module, which you need to instantiate twice:
>
> ```verilog
> module add16 ( input[15:0] a, input[15:0] b, input cin, output[15:0] sum, output cout );
> ```
>
> Use a 32-bit wide XOR gate to invert the `b` input whenever `sub` is 1. (This can also be viewed as `b[31:0]` XORed with sub replicated 32 times. See [replication operator](https://hdlbits.01xz.net/wiki/vector4).). Also connect the `sub` input to the carry-in of the adder.

<img src="../assets/image-20240903142331473.png" alt="image-20240903142331473" style="zoom:80%;display:block;margin: 0 auto;" />

```verilog
module top_module(
    input [31:0] a,
    input [31:0] b,
    input sub,
    output [31:0] sum
);

endmodule
```

## Solution

```verilog
module top_module(
    input [31:0] a,
    input [31:0] b,
    input sub,
    output [31:0] sum
);
    wire [31:0] b_sub;
    wire cout1;
    assign b_sub=b^{32{sub}};
    add16 inst1 (a[15:0],b_sub[15:0],sub,sum[15:0],cout1);
    add16 inst2 (a[31:16],b_sub[31:16],cout1,sum[31:16]);
endmodule
```