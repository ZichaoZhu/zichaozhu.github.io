# Combinational for-loop 255-bit population cout

## Problem statement

> A "population count" circuit **counts the number of '1's** in an input vector. Build a population count circuit for a 255-bit input vector.

```verilog
module top_module( 
    input [254:0] in,
    output [7:0] out );
	
endmodule
```

## Solution

```verilog
module top_module( 
    input [254:0] in,
    output [7:0] out );
    always @(*) begin
        out=0;
        for (int i=0;i<$bits(in);i++)
            out=out+in[i];	// out+=in[i]
    end
endmodule
```

* 注意需要对out**初始化**