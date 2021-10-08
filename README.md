# Advanced-Synthesis-STA-with-DC

![10_VSD-IAT Workshop Certificatecertificate_page-0001](https://user-images.githubusercontent.com/91059226/136513704-3dc4753a-8928-4d5b-a143-78b20649e7e6.jpg)


# Contents:

* Day-1
  * Introduction
  * DC_shell
  * Tcl_scripting
  * Design_Vision

* Day-2
  * STA_Basics
  * Constraints_and_IO_load
  * Timing_and_Exploring_dot_lib_files

* Day-3
  * Clock-tree_modelling
  * Clock-network_modelling_with_IO_delays

* Day-4
  * Combinational_and_resource_sharing_optimization
  * Sequential_optimization
  * Special_optimization

* Day-5
  * Timing_report
  * Set_max_capacitance_HFN


## INTRODUCTION TO THE COURSE:
Design Compiler is an Advanced Synthesis Tool used by leading semiconductor companies across world.
Synthesis of logic circuits plays a crucial role in optimizing the logic and achieving the targeted performance, area and power goals of an IC.
Understanding the fundamentals of design are very important to give the correct inputs to the tool to achieve the best-in-class netlist quality.
This workshop explores the following aspects:
+	Design fundamentals
+	Setting up DC for synthesis
+	Understanding STA
+	Understanding and writing the Synopsys Design Constraints [SDC].
+	Analyzing the quality of netlist synthesized.


## AGENDA OF THE COURSE:
+	Basics of Digital Logic Design and Synthesis ~ Quick Recap
+	Introduction to DC
+	TCL (Tool Command Language) ~ Quick Refresher
+	Constraining the Design, Synopsys Design Constraints (SDC)
+	STA
+	Logic Optimizations
+	Advanced Synthesis options
+	Generating Timing Reports
+	Analyzing Synthesis QoR

## TOOLS USED:
+	Iverilog - For Verilog Compilation, Simulation
+	gtkwave ~ for viewing the simulation output
+	Synopsys Design Compiler — For Logic Synthesis
+	Skywater 130nm Library

# Day 1  : Introduction to Logic Synthesis

+ Introduction to Design Compiler
+ what is Logic Synthesis ,
+ What is netlist , libraries ,
+ TCL Quick refresher
+ What is DC and how to launch DC ,
+ What are the inputs needed to load the design in DC ,
+ Loading a basic design in DC ,
+ Writing out a basic NL and DDC

### Introduction:
Every design starts with the target specification which decides the architecture of the chip. These specifications are represented in RTL. Hence, we can say that RTL is just a code!
This RTL Code is converted into gate level translation by SYNTHESIS. Hence the design is converted in to gates and the connections are made between the gates. This is given out as a netlist file
Now, what is .lib? It is basically a collection of logical modules. It includes basic logic gates and also includes different flavours of the same gate (i.e. slow, medium & fast). Note: We need fast cells to meet the required performance & we need slow cells to meet the HOLD. Faster cells imply Wider transistors (increased area & more power consumption) ---> Will have less delay.  Slower cells imply Narrow transistors (less area & less power consumption) ---> Will have more delay. Hence, we need to guide the synthesis to a make a mixture of cells and optimise. This guidance is given in the form of CONSTARINTS. Thus, CONSTRAINTS: are a guide to the synthesizer to pick correct library cells which is most appropriate for the design.

# Introduction to design compiler:
•	Basic Terminologies:
a.	 SDC: Synopsys design constraints
b.	.lib: design library containing cell information
c.	.db: DC understands library in .db format
d.	 ddc: DC can read in and write out in ddc

# DC SETUP:

![image](https://user-images.githubusercontent.com/91059226/134945944-5c9b0b59-92f5-4da3-9066-ed77bdfe81fb.png)
 

# DC SYNTHESSI FLOW:


![image](https://user-images.githubusercontent.com/91059226/134946046-a369f30f-8ea1-4de0-bc51-04392fd345d9.png)



# LAB:
•	Open dc_shell & read Verilog
•	Now we will point our target_library and link_library to skywater 130nm ---.db & read Verilog
•	Compile and produce the netlist

![image](https://user-images.githubusercontent.com/91059226/134946332-cec9440f-0fa2-4e50-a5e4-2f42b1db7437.png)

 
•	Write out ddc
•	Launch design vision & read ddc

![image](https://user-images.githubusercontent.com/91059226/134946430-e83b2eaa-3eae-4b83-843c-41415ebfddac.png)

•	Schematic design

![image](https://user-images.githubusercontent.com/91059226/134946487-616461ab-5c76-4b92-98ef-a762c6ff5571.png)


 
 


## Acknowledgements:
+ Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
+ Shon Taware, TA for the course.

## References:
VSD-IAT: https://vsdiat.com/
