<h1> Homework 1</h1>

**5-to-1 Multiplexer**

```
module multiplexer (input [4:0] a, input [4:0] b,input [4:0] c,input [4:0] d,input [4:0] e, input[2:0] sel, 
							output reg [4:0]  out); 
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

!()[https://github.com/sofyafyaa/fpga/blob/main/hw1/Screenshot_1.png]


<h1>Homework 2</h1>

**JK Flip Flop**

```
module jk_flip_flop ( input j, // Input J
    				input k, // Input K
    				input rstn, // Active-low async reset
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

!()[https://github.com/sofyafyaa/fpga/blob/main/hw2/jk_flip_flpo.png]

!()[https://github.com/sofyafyaa/fpga/blob/main/hw2/res_jk_flip_flop.png]

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

!()[https://github.com/sofyafyaa/fpga/blob/main/hw2/model10counter.png]

!()[https://github.com/sofyafyaa/fpga/blob/main/hw2/res_model10counter.png]

