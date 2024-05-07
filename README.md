# SIMULATION AND IMPLEMENTATION OF COMBINATIONAL CIRCUITS

## AIM:
To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Vivado.

## APPARATUS REQUIRED:
VIVADO 2023.2

## PROCEDURE:
 STEP:1 Start the Vivado, Select and Name the New project.
 
 STEP:2 Select the device family, device, package and speed. 
 
 STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
 
 STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.
 
 STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.
 
 STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

## ENCODER
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/2f228a11-7218-4784-b729-1ce544d8e069)

## PROGRAM
```
module encoder (d, a0, a1, a2);
input [7:0] d;
output a0, a1, a2;
assign a2=d[7] |d[6] |d[5] |d[4];
assign a1=d[7] |d[6] |d[3] |d[2];
assign a0=d[7] |d[5] |d[3] |d[1];
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/a57959af-0c10-48b6-a269-69df8b1d4a10)

## DECODER
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/6deffdcc-e4c1-4fe2-89f3-77f40df4a0c1)

## PROGRAM
```
module decoder (s, y);
input [2:0] s;
output [7:0] y;
assign y[0]=~s[2] & ~s[1] & ~s[0];
assign y[1]=~s[2] &~s[1] &  s[0];
assign y[2]=~s[2] & s[1] &~s[0];
assign y[3]=~s[2] & s[1] & s[0];
assign y[4]=s[2] & ~s[1] & ~s[0];
assign y[5]=s[2] & ~s[1] & s[0];
assign y[6]=s[2] & s[1] & ~s[0];
assign y[7]=s[2] & s[1] & s[0];
endmodule
```
## OUTPUT
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/53e55e6d-aa59-4422-9ebc-c4ffc300d585)

## MULTIPLEXER
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/8462e064-67da-488f-94d8-5c51b0391ade)

## PROGRAM
```
module Mux_8_1(s0,s1,s2,i,y);
input [7:0] i;
input s0, s1, s2;
output y;
wire [7:0] w;
assign w[0]=(~s2) & (~s1) & (~s0) & i[0];
assign w[1]=(~s2) &(~s1) &(s0) & i[1];
assign w[2]=(~s2) &(s1) &(~s0) & i[2];
assign w[3]=(~s2) &(s1) &(s0) & i[3];
assign w[4]=(s2) &(~s1) &(~s0) & i[4];
assign w[5]=(s2) &(~s1) &(s0) & i[5];
assign w[6]=(s2) &(s1) &(~s0) & i[6];
assign w[7]=(s2) &(s1) &(s0) & i[7];
assign y=w[0] |w[1] |w[2] |w[3] |w[4] |w[5] |w[6] |w[7];
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/017e6c89-8ac2-4912-b8a2-375630a2aaa5)

## DEMULTIPLEXER
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/e3fba960-d477-4cc1-87ca-09c6bacb927c)

## PROGRAM
```
module Demux1_8(i, s0, s1, s2, y);
input i;
input s0, s1, s2;
output [7:0] y;
assign y[0]=~s0 &~s1 &~s2 & i;
assign y[1]=~s0 &~s1 &s2 & i;
assign y[2]=~s0 &s1 &~s2 & i;
assign y[3]=~s0 &s1 &s2 & i;
assign y[4]=s0 & ~s1 & ~s2 & i;
assign y[5]=s0 & ~s1 & s2 & i;
assign y[6]=s0 & s1 & ~s2 & i;
assign y[7]=s0 & s1 &s2 & i;
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/d42f7828-5519-44f6-a25b-339ea586c157)

## MAGNITUDE COMPARATOR
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/0e41ae2e-3a0a-4951-a4f3-a70b8fc8e21a)

## PROGRAM
```
module mag_cmp(a,b,l,g,e);
input [3:0]a,b;
output reg l,g,e;
always @(*)
 begin
 if(a>b)
 begin
 l=1'b0;
 g=1'b1;
 e=1'b0;
 end
 else if(a<b)
 begin
 l=1'b1;
 g=1'b0;
 e=1'b0;
 end
 else
 begin
 l=1'b0;
 g=1'b0;
 e=1'b1;
 end
 end
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/Experiment-02-vlsi-/assets/159044760/e960c8ae-fed4-4d96-9176-eacb0bea761a)

## RESULT
Thus, the combinational circuits of   multiplexer, demultiplexer, encoder, decoder and magnitude comparator are implemented and simulated successfully.
