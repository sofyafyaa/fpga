<h1> Homework 1</h1>

**5-to-1 Multiplexer**

```
module multiplexer (input [4:0] a, input [4:0] b,input [4:0] c,input [4:0] d,input [4:0] e, input[2:0] sel, output reg [4:0]  out); 
    always @ (a or b or c or d or sel) begin
		 case (sel)
			2'b000: out <= a;
			2'b001: out <= b;
			2'b010: out <= c;
			2'b011: out <= d;
			2'b100: out <= e;

		 endcase
	 end

endmodule
```

Result of tests:

![test](https://github.com/sofyafyaa/fpga/blob/main/hw1/Screenshot_1.png)


<h1>Homework 2</h1>

**JK Flip Flop**

```
module jk_flip_flop ( input j, Input J, input k, Input K, input rstn, Active-low async reset
		      input clk, // Input clk
		      output reg q); // Output Q
    always @ (posedge clk or negedge rstn) begin
    	if (!rstn) begin
    		q <= 0;
    	end else begin
    		q <= (j & ~q) | (~k & q);
    	end
    end
endmodule
```

![2](https://github.com/sofyafyaa/fpga/blob/main/hw2/jk_flip_flpo.png)

![3](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_jk_flip_flop.png)

**Mod 10 counter**

```
module mod10_count ( input clk, input rstn, output reg[3:0] out);

    always @ (posedge clk) begin
    	if (!rstn) begin
    		out <= 0;
    	end else begin
    		if (out == 10)
    			out <= 0;
    		else
    			out <= out + 1;
    	end
    end
endmodule
```

![4](https://github.com/sofyafyaa/fpga/blob/main/hw2/model10counter.png)

![5](ttps://github.com/sofyafyaa/fpga/blob/main/hw2/res_model10counter.png)

**4-bit Left Shift Register**

```
module lshift_4b_reg(input d,
    						input clk,
    						input rstn,
    						output reg [3:0] out);
    always @ (posedge clk) begin
    	if (!rstn) begin
    		out <= 0;
    	end else begin
    		out <= {out[2:0], d};
    	end
    end
endmodule
```
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/shiftreg.png)
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_shiftreg.png)

**Compination of ligic elements**

```
module combo ( input a, b, c, d, e, output reg z);
    always @ ( a or b or c or d or e) begin
    	z = ((a & b) | (c ^ d) & ~e);
    end
endmodule
```
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_combination.png)
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_combination.png)

** Half Adder **

```
module halfadd ( input a, b, output reg sum, cout);
    always @ (a or b) begin
    	{cout, sum} = a + b;
    end
endmodule
```
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/halfadder.png)
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_halfadder.png)

**Ful Adder **

```
module fulladd ( input a, b, cin, output reg sum, cout);
    always @ (a or b or cin) begin
    	{cout, sum} = a + b + cin;
    end
endmodule
```
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/fuladder.png)
![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res_fulad.png)

**2x1 Multipolexer**

```
module mux21 (input a, b, sel, output reg c);
    always @ ( a or b or sel) begin
    	c = sel ? a : b;
    end
endmodule
```

![](https://github.com/sofyafyaa/fpga/blob/main/hw2/res2xmultiplexer.png)
