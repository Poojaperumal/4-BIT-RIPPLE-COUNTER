# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**


 Developed by: POOJA.P RegisterNumber: 212224100041

```


module ex12(
    input clk,         // Clock input
    input reset,       // Asynchronous reset
    output [3:0] q     // 4-bit counter output
);

    wire clk1, clk2, clk3;

    // First flip-flop toggles with main clock
    T_FF tff0 (.clk(clk), .reset(reset), .q(q[0]));

    // Subsequent flip-flops toggle with output of previous FF
    T_FF tff1 (.clk(q[0]), .reset(reset), .q(q[1]));
    T_FF tff2 (.clk(q[1]), .reset(reset), .q(q[2]));
    T_FF tff3 (.clk(q[2]), .reset(reset), .q(q[3]));

endmodule

// T Flip-Flop module
module T_FF (
    input clk,
    input reset,
    output reg q
);
    always @(posedge clk or posedge reset)
    begin
        if (reset)
            q <= 0;
        else
            q <= ~q;
    end
endmodule


```

**RTL LOGIC FOR 4 Bit Ripple Counter**



![Screenshot 2025-05-18 183714](https://github.com/user-attachments/assets/fb774117-6e4c-4d51-93ef-b9314f5930c4)





**TIMING DIGRAMS FOR 4 Bit Ripple Counter**


![Screenshot 2025-05-18 183858](https://github.com/user-attachments/assets/562eb532-7687-4b83-b25e-9277d2df14a4)



**RESULTS**


Thus the program to implement a 4 Bit Ripple Counter using verilog and validating their functionality using their functional tables is successfully completed.

