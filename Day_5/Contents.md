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

