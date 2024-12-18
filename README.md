```
Name : Aneesbashan J
Reference number:212223050006
```
# Exp 7-Synchornous counters up counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
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


### Procedure
Step 1:Create a new project in Quartus2 software .
Step 2:Name the project as uc for upcounter and dc for down counter.
Step 3:Create a new verilog hdl file in the project file.
Step 4:Name the module declare as dc and uc for down counter and upcounter.
Step 5:Within the module declare input and output variables.
Step 6:Create a loop using if-else with condition parameter as reset.
Step 7:End the loop.
Step 8:End the module


### PROGRAM 
# UP COUNTER:
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

### RTL LOGIC UP COUNTER AND DOWN COUNTER  

# UP COUNTER:
![Screenshot 2023-12-29 224532](https://github.com/Aneesbasha18/Exp-7-Synchornous-counters-/assets/154219883/4bb52ad6-5425-454f-a13b-72fd6c95a309)

### TIMING DIGRAMS FOR COUNTER  

# UP COUNTER:
![Screenshot 2023-12-29 224635](https://github.com/Aneesbasha18/Exp-7-Synchornous-counters-/assets/154219883/a378e87d-ef8c-4b4e-ab18-45dbd9bb2fc7)

### TRUTH TABLE 

# UP COUNTER:
![Screenshot 2023-12-29 224819](https://github.com/Aneesbasha18/Exp-7-Synchornous-counters-/assets/154219883/7db16cb6-ef4d-4a2d-b42f-b5dd1101f6b3)




### RESULTS 
Thus synchornous counters up counter circuit are studied and the truth table for different logic gates are verified.
