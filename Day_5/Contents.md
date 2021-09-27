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
2. check_timing : to see if the path is constrained or not
3. report_timing : to check if the SLACK is met or not
4. set_max_capacitance & set_max_transition : to break/buffer the high fanout net

