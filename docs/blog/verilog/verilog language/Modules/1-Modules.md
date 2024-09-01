# Modules

## Some basic information of modules

Modules contain instance of other modules, which forms a **hierarchy**.

When connecting modules, only the **ports** on the module are important. You do not need to know the code inside the module.

> The code for module `mod_a` looks like this:<img src="../assets/image-20240901132132145.png" alt="image-20240901132132145" style="zoom:100%;float:right;" />
>
> ```verilog
> module mod_a ( input in1, input in2, output out );
>     // Module body
> endmodule
> ```

The hierarchy of modules is created by instantiating one module inside another, as long as all of the modules used belong to the same project (so the compiler knows where to find the module). The code for one module is not written *inside* another module's body (Code for different modules are not nested).

You may connect signals to the module by **port name** or **port position**.

## Connecting Signals to Module Ports

There are two commonly-used methods to connect a wire to a port: **by position** or **by name**.

### By position

The syntax to connect wires to ports by position should be familiar, as it uses a C-like syntax. When instantiating a module, ports are connected left to right according to the module's declaration. For example:

```verilog
mod_a instance1 ( wa, wb, wc );
```

This instantiates a module of type `mod_a` and gives it an *instance name* of "instance1", then connects signal `wa` (outside the new module) to the **first** port (`in1`) of the new module, `wb` to the **second** port (`in2`), and `wc` to the **third** port (`out`). One drawback of this syntax is that if the module's port list changes, all instantiations of the module will also need to be found and changed to match the new module.

* By position时，需要关注端口的顺序

### By name

Connecting signals to a module's ports *by name* allows wires to remain correctly connected even if the port list changes. This syntax is more verbose, however.

```verilog
mod_a instance2 ( .out(wc), .in1(wa), .in2(wb) );
```

The above line instantiates a module of type `mod_a` named "instance2", then connects signal `wa` (outside the module) to the port **named** `in1`, `wb` to the port **named** `in2`, and `wc` to the port **named** `out`. Notice how the ordering of ports is irrelevant here because the connection will be made to the correct name, regardless of its position in the sub-module's port list. Also notice the period immediately(句点) preceding the port name in this syntax.

## Problem statement

Connect the signals.

<img src="../assets/image-20240901134537222.png" alt="image-20240901134537222" style="zoom:80%;display:block;margin: 0 auto;" />

```verilog
module top_module ( input a, input b, output out );

endmodule
```

## Solution

```verilog
module top_module ( input a, input b, output out );
    mod_a inst (a,b,out);	// By position
    // mod_a inst (.in1(a), .in2(b), .out(out));		By name
endmodule
```

