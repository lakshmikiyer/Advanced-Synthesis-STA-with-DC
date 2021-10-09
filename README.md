# Advanced-Synthesis-STA-with-DC

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


 # Day 2: Basics of STA

+ Basics of STA 
+ Delays
+ Timing Arcs
+ Constraining the Design
+ What is STA , setup , hold quick recap .
+ What are constraints
+ Constraining the Reg2Reg , Reg2IO , IO2Reg Paths
+ Input transition and OutputLoad and its effects on IO delays.

## Introduction to STA:
1.	Concept of Maximum and Minimum delay
2.	Water bucket Analogy: Delay of cell is a function of input transition & load capacitance

## Timing Path: 

### Start Points :
+ Input Ports
+ Clk Pins of Register

### End Points:
+ Output Ports
+ D pin of DFF /DLATCH

+ Always the timing paths start at one of the start points and ends at one of the end points:
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


# Day 3: Advanced Constraints

+ Clock Skew and Clock Jitter, its modelling in DC
+ Writing SDCs [Synopsys Design Constraints]
+ Creating Clocks
+ Querying Cells
+ Specifying IO Delays
+ Specifying Clock Waveforms
+ Generated Clocks
+ Multi Clock Design
+ False Paths

Open dc_shell. Echo target and link library
+ Read Verilog file and Now link the design, followed by Compile.
 
![image](https://user-images.githubusercontent.com/91059226/134951239-dfcae520-0f61-4d3c-8b3e-4d1624396aec.png)

What all pins are cock pins ??

![image](https://user-images.githubusercontent.com/91059226/134951387-6ac643f7-f209-40ff-bccf-becf79917ff6.png)

Writeout the ddc file
Now launch the design vision

![image](https://user-images.githubusercontent.com/91059226/134951544-fc78d4ee-61c5-4711-9b6e-7b1f128d5324.png)

Model the source latency, network latency and clock uncertainity

![image](https://user-images.githubusercontent.com/91059226/134951908-ea8937db-358c-4d18-8413-96acdbb340f2.png)

![image](https://user-images.githubusercontent.com/91059226/134952059-0e0ac075-e9bb-4ac0-bd6d-75d47d74a9f6.png)

SETTING THE MAX DELAY AT THE INPUT PORT A&B

![image](https://user-images.githubusercontent.com/91059226/134952835-2ea6c5d9-fba5-4fa7-8584-9c90eb78f266.png)

Similarly, 
+ SET THE MIN DELAY AT THE INPUT PORT A&B
+ SET THE INPUT TRANSITION & LOAD CAPACITANCE & ALSO MODEL THE LOAD

# Day 4: Optimizations

+ Optimizations in Synthesis
+ Combinational Logic Optimization
+ Boolean Reduction
+ Constant Propagation
+ Synthesis Directives
+ Synopsys full_case
+ Synopsys parallel_case
+ Sequential Logic Optimization
+ Sequential Constant
+ Retiming / Pipelining

![image](https://user-images.githubusercontent.com/91059226/134954713-e211d526-d2fb-45f8-af25-6e2fc3b84fb7.png)

![image](https://user-images.githubusercontent.com/91059226/134954758-f1e7adaf-b565-457a-aabf-147e034799d6.png)

Some results of combinational logic optimisation:

![image](https://user-images.githubusercontent.com/91059226/134955127-8b87273b-3d8d-4af5-bb6a-28a1eee8471e.png)

![image](https://user-images.githubusercontent.com/91059226/134955185-592d9749-1220-4564-8094-487edcba0288.png)


Resource Sharing Optimisation:

![image](https://user-images.githubusercontent.com/91059226/134955249-f6e7d4d0-0c45-475d-8775-e31e5ee57e88.png)

![image](https://user-images.githubusercontent.com/91059226/134955380-ed2fffbb-0790-4afe-ace5-e105cd671e8a.png)


# Day5 : Quality checks

+ Checking Netlist Quality and Generating Reports
+ Generating Timing Reports
+ max_paths
+ nworst
+ Boundary Optimizations
+ check_design
+ check_timing
+ HFN (High Fanout Nets)

Read verilog:

![image](https://user-images.githubusercontent.com/91059226/134955929-9b65f421-3c55-44c1-837d-940ff52262ca.png)

Report timings

![image](https://user-images.githubusercontent.com/91059226/134956049-818a78eb-1ce3-452c-b47b-bcc05903eef2.png)

1. check_design : to see if design is loaded properly or not

![image](https://user-images.githubusercontent.com/91059226/134956690-ee20882b-3878-49de-bcde-cd96f0b59425.png)

2. check_timing : to see if the path is constrained or not

![image](https://user-images.githubusercontent.com/91059226/134956951-2499d60c-5dfc-4c3c-b011-b43be8cdb3a1.png)

3. report_timing : to check if the SLACK is met or not

![image](https://user-images.githubusercontent.com/91059226/134956985-f7b53d83-0fd8-46de-93a1-4a2b9c98170a.png)

4. set_max_capacitance & set_max_transition : to break/buffer the high fanout net

![image](https://user-images.githubusercontent.com/91059226/134957053-49ed11bf-cbf1-4f87-a87c-7dd7b482868d.png)

![image](https://user-images.githubusercontent.com/91059226/134957134-0f535187-c126-4c0c-9bd0-b9f3b0287b9d.png)

5. report_constraints: to look at violations

![image](https://user-images.githubusercontent.com/91059226/134956914-fdf3c02e-d990-4f03-8dff-7d73ed2c6733.png)



## Acknowledgements:
+ Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
+ Shon Taware, TA for the course.

## References:
VSD-IAT: https://vsdiat.com/
