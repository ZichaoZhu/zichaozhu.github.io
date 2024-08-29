# Vector part select

## Problem statement

A 32-bit vector can be viewed as containing 4 bytes (bits [31:24], [23:16], etc.). Build a circuit that will reverse the *byte* ordering of the 4-byte word.

> Example:
>
> ```verilog
> AaaaaaaaBbbbbbbbCcccccccDddddddd => DdddddddCcccccccBbbbbbbbAaaaaaaa
> ```

* This operation is often used when the [endianness](https://en.wikipedia.org/wiki/Endianness) of a piece of data needs to be swapped, for example between little-endian x86 systems and the big-endian formats used in many Internet protocols.

```verilog
module top_module( 
    input [31:0] in,
    output [31:0] out );//

    // assign out[31:24] = ...;

endmodule
```

## Solution

```verilog
module top_module( 
    input [31:0] in,
    output [31:0] out );
    assign out={in[7:0],in[15:8],in[23:16],in[31:24]};
endmodule
```