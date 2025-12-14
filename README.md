# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**



1. Open Quartus Prime and create a new project.
2. Create a new Verilog file and name it appropriately.
3. Declare inputs S, R, clk and output Q.
4. Use an `always @(posedge clk)` block to describe the SR flip-flop.
5. Write a `case` statement with `{S,R}` as the selector.
6. Add conditions for 00 (hold), 01 (reset), and 10 (set).
7. Mark 11 as invalid or assign an unknown state.
8. End the case block and close the module.
9. Compile the code and fix any errors.
10. Open the waveform editor and add all signals.
11. Apply S, R, and clock inputs.
12. Run the simulation.
13. Verify the results with the truth table.


**PROGRAM**

/* 
   Program for SR flip-flop and verification of truth table in Quartus
   Developed by: Monica R
   Register Number: 25010138
*/
```
module SRflipflop(S, R, clk, q, qbar);
    input S, R, clk;
    output reg q, qbar;

    initial
    begin
        q     = 1'b0;
        qbar  = 1'b1;
    end

    always @(posedge clk)
    begin
        case ({S, R})
            2'b00: q <= q;        // Hold
            2'b01: q <= 1'b0;     // Reset
            2'b10: q <= 1'b1;     // Set
            2'b11: q <= 1'bx;     // Invalid
        endcase

        qbar <= ~q;
    end
endmodule

```

**RTL LOGIC FOR FLIPFLOPS**
<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/030ef985-bcee-4b52-ba0a-4f67dd2c1697" />



**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/b12cbdcd-796d-4a9d-bd7a-0089d7b0419e" />



**RESULTS**
