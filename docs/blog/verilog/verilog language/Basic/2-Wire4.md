# Wire4

## Something need to be noticed

* When you have multiple `assign` statements, the **order** in which they appear in the code **does not matter**.

  Unlike a programming language, `assign` statements ("continuous assignments") **describe *connections* between things**, **not** the *action* of copying a value from one thing to another.

## Problem statement

> Create a module with 3 inputs and 4 outputs that behaves like wires that makes these connections:
>
> a -> w
>
> b -> x
>
> b -> y
>
> c -> z

```verilog
module top_module( 
    input a,b,c,
    output w,x,y,z );

endmodule
```

## Solution

```verilog
module top_module( 
    input a,b,c,
    output w,x,y,z );
	assign {w,x,y,z} = {a,b,b,c};
endmodule
```

* If we're certain about the width of each signal, using the concatenation operator is equivalent and shorter: assign {w,x,y,z} = {a,b,b,c};