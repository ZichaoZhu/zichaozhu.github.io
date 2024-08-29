# Nor gate

## What is nor gate?

> A NOR gate is an OR gate with its output inverted. A NOR function needs two operators when written in Verilog.

## Problem statement

```verilog
module top_module( 
    input a, 
    input b, 
    output out );

endmodule
```

## Solution

```verilog
module top_module( 
    input a, 
    input b, 
    output out );
	assign out=~(a|b);
endmodule
```

