### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

ALGORITM: 

Step1: Define the specifications and initialize the design. 

Step2: Declare the name of the entity and architecture by using VHDL source code. 

Step3: Write the source code in VERILOG. 

Step4: Check the syntax and debug the errors if found, obtain the synthesis report. 

Step5: Verify the output by simulating the source code. 

Step6: Write all possible combinations of input using the test bench. 

Step7: Obtain the place and route report.  


**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:HARINI S

RegisterNumber:24900110

module syncupcntr(clk, rst, q); 

  input clk; 
  
  input rst; 
  
  output [3:0]q; 
  
  reg [3:0]q; 
  
  reg [3:0]x=0; 
  
  always @ (posedge(clk) or posedge(rst))
  
  begin 
  
  if (rst==1'b1) 
  
  begin 
  
  q=4'b0; 
  
  end 
  
  else  
  
  begin 
  
  x=x+1'b1; 
  
  end 
  
  q=x; 
  
  end 
  
  endmodule
  


**RTL LOGIC UP COUNTER**
![Screenshot (47)](https://github.com/user-attachments/assets/c456d1bc-0b0b-4636-8abb-17d9210305b5)



**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot (46)](https://github.com/user-attachments/assets/79165882-603d-441c-b877-8aedf81b861f)

**TRUTH TABLE**

![Screenshot (48)](https://github.com/user-attachments/assets/3d8f80b2-0dca-49f3-b39d-011d9402f858)

**RESULTS**

Thus the OUTPUT’s of Synchronous and counter are verified by synthesizing and simulating the  VERILOG code.
