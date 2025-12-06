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



**PROGRAM**

```
module ex11 (out,clk,rstn); 
input clk,rstn;
output reg [3:0] out;
always @ (posedge clk)
begin 
	if(!rstn) 
		out<=0; 
	else 
		out <= out+1; 
end 
endmodule
```
Developed by:PRIYARITHANYA M RegisterNumber:25007623
*/

**RTL LOGIC UP COUNTER**
<img width="1920" height="1080" alt="Screenshot (102)" src="https://github.com/user-attachments/assets/feac307f-05dc-4fe4-bdf2-0ba448c53f91" />


**TIMING DIAGRAM FOR IP COUNTER**
<img width="1920" height="1080" alt="Screenshot (103)" src="https://github.com/user-attachments/assets/597a3b84-dc0b-4253-9447-3ddf5b611a15" />

**TRUTH TABLE**
![de pic](https://github.com/user-attachments/assets/82549aa1-eee6-4f2c-bf19-89c0c19cca84)

**RESULTS**
This program was executed successfully
