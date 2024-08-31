# Replication operator

## What is replication operator and why we need them?

The [concatenation operator](https://hdlbits.01xz.net/wiki/Vector3) allowed concatenating together vectors to form a larger vector. But sometimes you want the same thing concatenated together many times, and it is still tedious to do something like `assign a = {b,b,b,b,b,b};`. The replication operator allows repeating a vector and concatenating them together:

```verilog
{num{vector}}
```

This replicates *vector* by *num* times. *num* must be a constant. Both sets of braces are required.

Examples:

```verilog
{5{1'b1}}           // 5'b11111 (or 5'd31 or 5'h1f)
{2{a,b,c}}          // The same as {a,b,c,a,b,c}
{3'd5, {2{3'd6}}}   // 9'b101_110_110. It's a concatenation of 101 with
                    // the second vector, which is two copies of 3'b110.
```

## Practice

### Background information

One common place to see a replication operator is when sign-extending a smaller number to a larger one, while preserving its signed value. This is done by replicating the sign bit (the most significant bit) of the smaller number to the left. For example, sign-extending 4'b**0**101 (5) to 8 bits results in 8'b**0000**0101 (5), while sign-extending 4'b**1**101 (-3) to 8 bits results in 8'b**1111**1101 (-3).

### Problem statement

> Build a circuit that sign-extends an 8-bit number to 32 bits. This requires a concatenation of 24 copies of the sign bit (i.e., replicate bit[7] 24 times) followed by the 8-bit number itself.

```verilog
module top_module (
    input [7:0] in,
    output [31:0] out );//

    // assign out = { replicate-sign-bit , the-input };

endmodule
```

### Solution

```verilog
module top_module (
    input [7:0] in,
    output [31:0] out );
    assign out={{24{in[7]}},in};
endmodule
```

* 尤其需要注意的是，{num{vector}}只有在**左右都加上括号**的情况下才是一个**向量**