# Combinational for-loop Vector reversal 2

## Problem statement

> Given a 100-bit input vector [99:0], reverse its bit ordering.

```verilog
module top_module( 
    input [99:0] in,
    output [99:0] out
);

endmodule
```

## Solution

```verilog
module top_module( 
    input [99:0] in,
    output [99:0] out
);
    always @(*) begin
        for (int i=0;i<$bits(out);i++)
            out[i]=in[$bits(out)-i-1];
    end
endmodule
```

* $bits() is a system function that returns the width of a signal.
* $bits(out) is 100 because out is 100 bits wide.