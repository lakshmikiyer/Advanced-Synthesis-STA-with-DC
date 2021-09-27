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


 
 