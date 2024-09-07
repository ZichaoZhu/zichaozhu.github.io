# Generate for-loop 100-digit BCD adder

## Problem statement

> You are provided with a BCD one-digit adder named `bcd_fadd` that adds two BCD digits and carry-in, and produces a sum and carry-out.
>
> ```verilog
> module bcd_fadd (
>     input [3:0] a,
>     input [3:0] b,
>     input     cin,
>     output   cout,
>     output [3:0] sum );
> ```
>
> Instantiate 100 copies of `bcd_fadd` to create a 100-digit BCD ripple-carry adder. Your adder should add two 100-digit BCD numbers (packed into 400-bit vectors) and a carry-in to produce a 100-digit sum and carry out.

```verilog
module top_module( 
    input [399:0] a, b,
    input cin,
    output cout,
    output [399:0] sum );

endmodule
```



## Solution

```verilog
module top_module( 
    input [399:0] a, b,
    input cin,
    output cout,
    output [399:0] sum );
    wire [99:0] w1;
    assign cout=w1[99];
	genvar i;
    generate
        for (i=0;i<100;i++) begin:block1
            if (i==0) begin
                bcd_fadd inst (a[i*4+3:i*4],b[i*4+3:i*4],cin,w1[i],sum[i*4+3:i*4]);
            end
            else begin
                bcd_fadd inst (a[i*4+3:i*4],b[i*4+3:i*4],w1[i-1],w1[i],sum[i*4+3:i*4]);
            end
        end
     endgenerate
endmodule
```

* for循环后面的那个模块名称是必要的
* genvar是一种特殊的数据类型，特别用于generate for语句