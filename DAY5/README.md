# Day 5: CMOS Power supply and device variation robustness evaluation

## Part 1: Static Behavior Evaluation - CMOS Inverter Robustness: Power Supply Variation
-   Whenever we move from 250nm nodes to lower nodes like 20nm or so on, we scale our supply voltage as well. For example, if things were working at 1V sometime back, now they will be operating at 0.7V
    
-   A CMOS inverter can be operated at 0.5V as well and it has it's own advantages and disadvantages:
    
    -   Advantages of using 0.5V supply:
        -   There is a significant increase in gain (close to 50% improvement)
        -   There is a significant reduction in energy consumption (close to 90% improvement)
    -   Disadvantages of using 0.5V supply:
        -   Performance impact (0.5V supply rising and falling edge is insufficient to completely charge or discharge the load capacitance)

  ### Lab :
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

.control

let powersupply = 1.8
alter Vdd = powersupply
        let voltagesupplyvariation = 0
        dowhile voltagesupplyvariation < 6
        dc Vin 0 1.8 0.01
        let powersupply = powersupply - 0.2
        alter Vdd = powersupply
        let voltagesupplyvariation = voltagesupplyvariation + 1
      end

plot dc1.out vs in dc2.out vs in dc3.out vs in dc4.out vs in dc5.out vs in dc6.out vs in xlabel "input voltage(V)" ylabel "output voltage(V)" title "Inveter dc characteristics as a function of supply voltage"

.endc

.end
```
