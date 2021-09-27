# Introduction to STA:
1.	Concept of Maximum and Minimum delay
2.	Water bucket Analogy: Delay of cell is a function of input transition & load capacitance

##Timing Path: 

### Start Points :
+ Input Ports
+ Clk Pins of Register

### End Points:
+ Output Ports
+ D pin of DFF /DLATCH
*Always the timing paths start at one of the start points and ends at one of the end points:
a.	Clk to D
b.	Input to D
c.	Clk to Output
d.	Input to Output
Note: We also have to take into account the input external delay & the output external delay. Don’t forget the input transition and the output load capacitance!

Thus, timing path takes into account the following:
+	REG 2 REG: Constrained by Clock
+	REG 2 OUT: Constrained by Output External Delay, Output Load and Clock Period
+	IN 2 REG: Constrained by Input External Delay, Input Transition and Clock Period

# LAB:

•	Open sky130 .lib file

•	list_libs : tells the library that we have already loaded in our design
 
![image](https://user-images.githubusercontent.com/91059226/134950175-d7f6c0ef-0b71-47dd-bb6a-6c9920666d1f.png)


•	Get all the and gates and Let us print it one by one
 
![image](https://user-images.githubusercontent.com/91059226/134950400-e06844d8-dcee-46f6-b625-32e0f2496dce.png)




