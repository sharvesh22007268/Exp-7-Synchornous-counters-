# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: 
To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   
Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure

1.    Create a new project in Quartus2 software .
2.    Name the project as uc for upcounter and dc for down counter.
3.    Create a new verilog hdl file in the project file.
4.    Name the module declare as dc and uc for down counter and upcounter.
5.    Within the module declare input and output variables.
6.    Create a loop using if-else with condition parameter as reset.
7.    End the loop.
8.    End the module

## PROGRAM 
### Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: Sharvesh
RegisterNumber:  22007268
### UP COUNTER
```
Module upcounter(clk,a);
input clk;
output reg[3:0];
always @(posedge clk)
begin
a[3]=(a[2]&a[1]&a[0])^a[3];
a[2]=(a[1]&a[0])^a[2];
a[1]=(a[0]^a[1]);
a[0]= ^a[0];
end
endmodule
```
### DOWN COUNTER
```
Module downcounter(clk,a);
input clk;
output reg[3:0]a;
always @(posedge clk)
begin
a[3]=(~a[2]&~a[1]&~a[0])^a[3];
a[2]=(~a[1]&~a[0])^a[2];
a[1]=(~a[0]^a[1]);
a[0]=1^a[0];
end
endmodule
```
## RTL LOGIC UP COUNTER AND DOWN COUNTER  
### UPCOUNTER :
![243264207-bf2999c0-6bec-47f6-915f-b636aeda4576](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/ca7cdfef-1cfa-4a65-99c6-98c20af18ac3)
### DOWNCOUNTER:
![243265990-f9f7346d-aaf2-470e-9547-9c05a71689b3](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/7de16600-7faf-4d72-81fe-afbc0068a934)
## TIMING DIGRAMS FOR COUNTER  
### UPCOUNTER:
![243264477-ba044594-b7e9-4289-9580-cf048d003b85](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/76a36aa5-aac3-4ae9-81a8-7090db265978)
### DOWNCOUNTER:
![243264515-10d8818b-ae16-4829-88b0-c6586fe01ba8](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/fab165fe-7964-4741-af4a-9079131a374d)
## TRUTH TABLE 
### UPCOUNTER:
![243264700-fe5c6e0f-b1d0-49ba-97fc-a9843ff1e42a](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/b194d5fb-876d-4a4e-a78c-9d055ab3c2a5)
### DOWNCOUNTER:
![243264770-03ace885-dd9a-47ac-8ecd-392886805052](https://github.com/Yuvaraj878/Exp-7-Synchornous-counters-/assets/118622554/a0fb34eb-d5b3-4e9e-a7c0-f814580490e7)

### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
