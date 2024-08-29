# Not gate

## Problem statement

```verilog
module top_module( input in, output out );

endmodule
```

## Solution

```verilog
module top_module( input in, output out );
	assign out=~in;
endmodule
```

* 在verilog中，"~"意味着**按照位来取反**

