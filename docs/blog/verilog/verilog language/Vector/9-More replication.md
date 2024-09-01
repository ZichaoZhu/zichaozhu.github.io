# More replication

## Problem statement

> Given five 1-bit signals (a, b, c, d, and e), compute all 25 pairwise one-bit comparisons in the 25-bit output vector. The output should be 1 if the two bits being compared are equal.

```verilog
out[24] = ~a ^ a;   // a == a, so out[24] is always 1.
out[23] = ~a ^ b;
out[22] = ~a ^ c;
...
out[ 1] = ~e ^ d;
out[ 0] = ~e ^ e;
```

<img src="../assets/image-20240901130304531.png" alt="image-20240901130304531" style="zoom:100%;display:block;margin: 0 auto;" />

As the diagram shows, this can be done more easily using the [replication](https://hdlbits.01xz.net/wiki/Vector4) and concatenation operators.

- The top vector is a concatenation of 5 repeats of each input
- The bottom vector is 5 repeats of a concatenation of the 5 inputs

```verilog
module top_module (
    input a, b, c, d, e,
    output [24:0] out );//

    // The output is XNOR of two vectors created by 
    // concatenating and replicating the five inputs.
    // assign out = ~{ ... } ^ { ... };

endmodule
```

## Solution

```verilog
module top_module (
    input a, b, c, d, e,
    output [24:0] out );
    assign out=~{{5{a}},{5{b}},{5{c}},{5{d}},{5{e}}}^{5{a,b,c,d,e}};
endmodule
```

