# If statement

## Introduction of if statement

An `if` statement usually creates a 2-to-1 multiplexer, selecting one input if the condition is true, and the other input if the condition is false.

<img src="../assets/image-20240906140107467.png" alt="image-20240906140107467" style="zoom:80%;display:block;margin:0 auto;" />

```verilog
always @(*) begin
    if (condition) begin
        out = x;
    end
    else begin
        out = y;
    end
end
```

This is equivalent to using a continuous `assign`ment with a conditional operator:

```verilog
assign out = (condition) ? x : y;
```

However, the procedural `if` statement provides a new way to make mistakes. The circuit is combinational only if `out` is always assigned a value.

## Practice

### Problem statement

> Build a **2-to-1 mux** that chooses between `a` and `b`. Choose `b` if *both* `sel_b1` and `sel_b2` are true. Otherwise, choose `a`. Do the same twice, once using `assign` statements and once using a procedural if statement.

| sel_b1 | sel_b2 | out_assign out_always |
| :----: | :----: | :-------------------: |
|   0    |   0    |           a           |
|   0    |   1    |           a           |
|   1    |   0    |           a           |
|   1    |   1    |           b           |

```verilog
// synthesis verilog_input_version verilog_2001
module top_module(
    input a,
    input b,
    input sel_b1,
    input sel_b2,
    output wire out_assign,
    output reg out_always   ); 

endmodule
```

### Solution

```verilog
// synthesis verilog_input_version verilog_2001
module top_module(
    input a,
    input b,
    input sel_b1,
    input sel_b2,
    output wire out_assign,
    output reg out_always   ); 
    assign out_assign=(sel_b1&sel_b2==1) ? b:a;
    always @(*) begin
        if (sel_b1&sel_b2==1) begin
            out_always=b;
        end
        else begin
            out_always=a;
        end
    end
endmodule
```

