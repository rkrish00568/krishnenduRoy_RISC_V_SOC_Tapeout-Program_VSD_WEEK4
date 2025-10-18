# Day 4: CMOS Noise Margin Robustness Evaluation

##  Part 1: Static Behavior Evaluation - CMOS Inverter Robustness: Noise Margin

### Lab Activity
```
*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=1 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.36 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op

.dc Vin 0 1.8 0.01

.control
run
setplot dc1
display
.endc

.end
```
![image](images/1.png)
![image](images/2.png)
The snap shot of the output window for calculating the Noise Margins

Method to calculate the Noise Margins from the plot:
Run the ngspice command and open the plot
left click on the point towards the top of the graph where the curvature seems to be '-1'
In this case it was x0 = 0.766667, y0 = 1.71351
Now, left click on the point towards the bottom of the graph where the curvature seems to be '-1'
In this case it was x0 = 0.977333, y0 = 0.110811. Let's consider these points as x1 and y1 thus making the coordinates x1 = 0.977333, y1 = 0.110811
For noise margin high we need Voh-Vih and in this case Voh=y0 and Vih=x1
For noise margin low we need Vil-Vol and in this case Vil=x0 and Vol=y1
Therefore, we get NMh = 0.736177 and NMl = 0.655856
