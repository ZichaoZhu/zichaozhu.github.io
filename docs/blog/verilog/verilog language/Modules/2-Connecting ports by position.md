# Connecting ports by position

> This problem is similar to the previous one ([module](https://hdlbits.01xz.net/wiki/module)). You are given a module named `mod_a` that has 2 outputs and 4 inputs, in that order. You must connect the 6 ports *by position* to your top-level module's ports `out1`, `out2`, `a`, `b`, `c`, and `d`, in that order.

You are given the following module:

```verilog
module mod_a ( output, output, input, input, input, input );
```

<img src="../assets/image-20240901140029478.png" alt="image-20240901140029478" style="zoom:80%;display:block;margin: 0 auto;" />

```verilog
module top_module ( 
    input a, 
    input b, 
    input c,
    input d,
    output out1,
    output out2
);

endmodule
```

## Solution

```verilog
module top_module ( 
    input a, 
    input b, 
    input c,
    input d,
    output out1,
    output out2
);
    mod_a inst (out1,out2,a,b,c,d);
endmodule
```

* 注意端口顺序