# Verilog-Code-for-Swapping-Three-Numbers
## AADHITHYA SV
## 212223060001
## Aim
To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

## Apparatus Required
Vivado 2023.1 or equivalent Verilog simulation tool.

## Procedure
Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.

## Verilog Code:
### By Blocking (3 Variables)
```
`timescale 1ns / 1ps
module swap3block;
reg [3:0]a,b,c;
initial begin
a=4'd10;
b=4'd12;
c=4'd14;
end
always @(*)
begin
a=b;
b=c;
c=a;
end
endmodule
```
### Output
### By Blocking ( 3 Variables)
![WhatsApp Image 2025-04-12 at 14 33 41_dab37ed4](https://github.com/user-attachments/assets/bd991413-b754-48aa-8901-7958bbb0032d)
### By Non-Blocking(3 Variables)
```
`timescale 1ns / 1ps
module nonblock(a,b,c,clk);
input clk;
output reg [3:0]a,b,c;
initial 
begin
a=4'd12;
b=4'd14;
c=4'd15;
end
always @(posedge clk)
begin
a<=b;
b<=c;
c<=a;
end 
endmodule

```
### Output
### By Non-Blocking  ( 3 Variables)
![image](https://github.com/user-attachments/assets/89aa7cf3-0d1e-4a85-8b98-5601ddf770c6)

### By Blocking (2 variable)
```
`timescale 1ns / 1ps
module swap2block;
reg [3:0]a,b;
initial begin
a=4'd10;
b=4'd12;
end
always @(*)
begin
a=b;
b=a;
end
endmodule

```
### Output
### By Blocking( 2 variable)
![image](https://github.com/user-attachments/assets/37dec5da-78e0-4637-832b-046c754cd63a)

### By Non-Blocking (2 Variable)
```
`Timescale 1ns / 1ps
module swap2nonblock(a,b,clk);
input clk;
output reg [3:0]a,b;
initial 
begin
a=4'd12;
b=4'd14;
end
always @(posedge clk)
begin
a<=b;
b<=a;
end 
endmodule
```
## OUTPUT

### By Non Blocking(2 variable)
![image](https://github.com/user-attachments/assets/98886ae5-ecf5-45b7-bf7e-2269fde0b40f)

## Testbench for Swapping Three Numbers:

// swap_three_numbers_tb.v
```
`timescale 1ns / 1ps

module swap3block_tb;

    // Inputs
    reg [7:0] a;
    reg [7:0] b;
    reg [7:0] c;

    // Outputs
    wire [7:0] a_out;
    wire [7:0] b_out;
    wire [7:0] c_out;

    // Instantiate the Unit Under Test (UUT)
    swap_three_numbers uut (
        .a_in(a),
        .b_in(b),
        .c_in(c),
        .a_out(a_out),
        .b_out(b_out),
        .c_out(c_out)
    );

    // Test procedure
    initial begin
        // Initialize inputs
        a = 8'd10; // Assign 10 to a
        b = 8'd20; // Assign 20 to b
        c = 8'd30; // Assign 30 to c

        // Wait for 10 ns to observe swap
        #10;

        // Display results
        $display("Before Swap: a = %d, b = %d, c = %d", a, b, c);
        #10;
        $display("After Swap: a = %d, b = %d, c = %d", a_out, b_out, c_out);
        
        // Stop the simulation
        #10 $stop;
    end
endmodule
```


## Conclusion
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
