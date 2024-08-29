# Xnor gate(同或)

## Xnor

意为**同或**，相同输出1，不同输出0

## Problem station

>  Create a module that implements an XNOR gate.

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
    assign out=~(a^b);	//assign out=a^b;
endmodule
```

* 其中，a^b意为**异或**
