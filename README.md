# 32Bit-ALU_Synthesis

## Aim:

Synthesize 32 Bit ALU design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)
```
module alu_32bit_case(y,a,b,f);
input [31:0]a;
input [31:0]b;
input [2:0]f;
output reg [31:0]y;
always@(*)
begin
case(f)
3'b000:y=a&b; //AND Operation
3'b001:y=a|b; //OR Operation
3'b010:y=~(a&b); //NAND Operation
3'b011:y=~(a|b); //NOR Operation
3'b100:y=a+b; //Addition
3'b101:y=a-b; //Subtraction
3'b110:y=a*b; //Multiply
default:y=32'bx;
endcase
end
endmodule
```

### Step 2 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

#### Synthesis RTL Schematic :
![WhatsApp Image 2025-05-20 at 13 22 27_d39b7b01](https://github.com/user-attachments/assets/f94380ba-d1d2-4629-8b1a-acd9ad189814)


#### Area report:
![WhatsApp Image 2025-05-20 at 13 23 22_deac214b](https://github.com/user-attachments/assets/e50d94ca-67dd-4c2b-9e27-a6f22cd8a197)

#### Power Report:
![WhatsApp Image 2025-05-20 at 13 24 06_f0da12dc](https://github.com/user-attachments/assets/3844efe7-2002-45e0-8ba4-020effcfe7d9)

#### Result: 
The generic netlist of 32 bit ALU  has been created, and area, power reports have been tabulated and generated using Genus.
