# 4BIT_RIPPLE_COUNTERS

AIM:

To implement 4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:
           Quartus prime

THEORY

4 Bit Ripple Counter

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

<img width="749" height="396" alt="Screenshot 2025-12-15 225706" src="https://github.com/user-attachments/assets/96feebf5-06fa-4ec3-afa2-aef10b1c7320" />

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

<img width="441" height="336" alt="Screenshot 2025-12-15 225457" src="https://github.com/user-attachments/assets/491a427c-2b34-4520-b955-bdccd025e7ee" />

<img width="315" height="241" alt="Screenshot 2025-12-15 225520" src="https://github.com/user-attachments/assets/5bb67466-35ab-4a6f-a5fc-654440e54567" />



PROGRAM

```

module Bit_ripple_counter (
    input  wire clk,      // external clock
    input  wire rst,      // asynchronous reset
    output reg  [2:0] q   // counter output
);

always @(posedge clk or posedge rst)
begin
    if (rst)
        q[0] <= 1'b0;
    else
        q[0] <= ~q[0];     // LSB toggles on every clock
end

always @(posedge q[0] or posedge rst)
begin
    if (rst)
        q[1] <= 1'b0;
    else
        q[1] <= ~q[1];     // toggles on q[0]
end

always @(posedge q[1] or posedge rst)
begin
    if (rst)
        q[2] <= 1'b0;
    else
        q[2] <= ~q[2];     // toggles on q[1]
end

endmodule

```

Developed by: B.TAMIZHAN

RegisterNumber: 25018064

RTL LOGIC FOR 4 Bit Ripple Counter:

[EX 12 Dia.pdf](https://github.com/user-attachments/files/24172424/EX.12.Dia.pdf)

WAVEFORM:

[BIT_RIPPLE_4COUNTERS.pdf](https://github.com/user-attachments/files/24172429/BIT_RIPPLE_4COUNTERS.pdf)

RESULTS:
Thus implementing 4 Bit Ripple Counter using Verilog and validating their functionality using their functional tables is done successfully.
