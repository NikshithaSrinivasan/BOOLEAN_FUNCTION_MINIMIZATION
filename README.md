# BOOLEAN_FUNCTION_MINIMIZATION

**AIM:**

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D 

F2=xy’z+x’y’z+w’xy+wx’y+wxy

**Equipment Required:**

Hardware – PCs, Cyclone II , USB flasher

**Software – Quartus prime**

**Theory**

Boolean Function Minimization is the process of reducing a Boolean expression to its simplest form without changing its functionality. This minimization reduces the number of gates and inputs required, optimizing circuit design.

Logic Gates: Fundamental building blocks like AND, OR, and NOT gates are used to implement Boolean expressions. Karnaugh Map (K-map): A graphical technique for minimizing Boolean expressions by grouping terms based on commonalities. The given Boolean functions can be minimized as follows:

F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D The terms can be simplified using K-map techniques to reduce the complexity of the circuit. F2 = xy’z + x’y’z + w’xy + wx’y + wxy Similar simplification can be done for this function to reduce the gate count. The resulting minimized expressions are implemented using Verilog HDL and simulated on the Quartus Prime tool. The outputs can then be verified on an FPGA board (e.g., Cyclone II).

**Truth Table**

F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D:

![Screenshot 2025-04-16 093244](https://github.com/user-attachments/assets/d62ce9f9-c2ff-42c1-ba5e-27883535c000)

F2 = xy’z + x’y’z + w’xy + wx’y + wxy:

![Screenshot 2025-04-16 093254](https://github.com/user-attachments/assets/b3f018e9-bc4b-4069-a4c3-bf8b1ab91694)

**Procedure**

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.

**Program:**
```python
/* Program to implement the given logic function and to verify its operations in quartus using Verilog programming. 
Developed by: NIKSHITHA.S
RegisterNumber: 212224040220
*/
module exp2(a,b,c,d,w,x,y,z,f1,f2);
  input a,b,c,d,w,x,y,z;
  output f1,f2;
  wire x1,x2,x3,x4,x5,y1,y2,y3,y4,y5;
  assign x1=((~a)&(~b)&(~c)&(~d));
  assign x2=(a&(~c)&(~d));
  assign x3=((~b)&(c)&(~d));
  assign x4=((~a)&(b)&(c)&(d));
  assign x5=(b&(~c)&(d));
  assign f1=x1|x2|x3|x4|x5;
  
  assign y1=(x&(~y)&(z));
  assign y2=((~x)&(~y)&z);
  assign y3=((~w)&x&y);
  assign y4=(w&(~x)&(y));
  assign y5=(w&x&y);
  assign f2=y1|y2|y3|y4|y5;
  endmodule 
```
**RTL realization**

![Screenshot 2025-04-16 084828](https://github.com/user-attachments/assets/e3dd20a1-6d93-4b0d-a1fa-a1853d5fceff)

**Timing Diagram**

![image](https://github.com/user-attachments/assets/32755610-4555-49e7-8467-53766bdbd97b)
**Result:**

Thus the given logic functions are implemented using and their operations are verified using Verilog programming.

