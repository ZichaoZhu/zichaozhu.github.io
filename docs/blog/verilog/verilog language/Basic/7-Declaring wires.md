# Declaring wires

## Why should we declare wires?

The circuits so far have been simple enough that the outputs are simple functions of the inputs. **As circuits become more complex, you will need wires to connect internal components together.** When you need to use a wire, you should declare it in the body of the module, somewhere before it is first used. 

## Example

<img src="../assets/image-20240827124958871.png" alt="Example" style="zoom:80%;display:block;margin:0 auto;" />

```verilog
module top_module (
    input in,              // Declare an input wire named "in"
    output out             // Declare an output wire named "out"
);

    wire not_in;           // Declare a wire named "not_in"

    assign out = ~not_in;  // Assign a value to out (create a NOT gate).
    assign not_in = ~in;   // Assign a value to not_in (create another NOT gate).

endmodule   // End of module "top_module"
```

* Note that it doesn't matter which of the NOT gates you create first: You still end up with the same circuit.

## Problem statement

> Implement the following circuit. Create two intermediate wires (named anything you want) to connect the AND and OR gates together. Note that the wire that feeds the NOT gate is really wire `out`, so you do not necessarily need to declare a third wire here. Notice how wires are driven by exactly one source (output of a gate), but can feed multiple inputs.
>
> If you're following the circuit structure in the diagram, you should end up with four assign statements, as there are four signals that need a value assigned.

<img src="../assets/image-20240827125559403.png" alt="image-20240827125559403" style="zoom:80%;display:block;margin:0 auto;" />

```verilog
`default_nettype none
module top_module(
    input a,
    input b,
    input c,
    input d,
    output out,
    output out_n   ); 

endmodule
```

## Solution

```verilog
`default_nettype none
module top_module(
    input a,
    input b,
    input c,
    input d,
    output out,
    output out_n   ); 
	wire wire1,wire2;
    assign wire1=a&b;
    assign wire2=c&d;
    assign out=wire1|wire2;
    assign out_n=~out;
endmodule
```

