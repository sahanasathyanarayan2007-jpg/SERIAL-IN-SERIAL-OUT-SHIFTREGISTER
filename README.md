# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

```


The block runs whenever there is a positive edge of the clock (posedge clk).


If clear is high, the 4-bit register tmp is reset to 0000.


Otherwise, the contents of tmp are shifted left by one bit.


The serial input si is loaded into the least significant bit tmp[0].


The most significant bit tmp[3] is assigned to the serial output so.
```

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: RegisterNumber:212225240130

*/
```

module exp5de(clk,clear,si,so);
input clk,si,clear;
output so;
reg so;
reg [3:0] tmp;
always @(posedge clk )
begin
if (clear)
tmp <= 4'b0000;
else
tmp <= tmp << 1;
tmp[0] <= si;
so = tmp[3];
end
endmodule
```

**RTL LOGIC FOR SISO Shift Register**
<img width="1021" height="530" alt="image" src="https://github.com/user-attachments/assets/4a5edb65-2ffa-4887-b1ae-cbf9809e0fd3" />


**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1918" height="351" alt="image" src="https://github.com/user-attachments/assets/125e8487-8488-426c-af9e-768326a2b27b" />


**RESULTS**
This Verilog code implements a 4-bit left shift register with serial input si, serial output so, and synchronous clear control.
