# Day 1: Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)

## Part 1: Introduction to Circuit Design and SPICE simulations
### The importance of W/L ratio
 - The W/L ratio determines a MOSFET’s strength — a higher W/L increases the drain current (Id), making the transistor faster. Since delay is inversely proportional to Id, a larger W/L ratio reduces propagation delay, improving circuit speed.
###  Need of SPICE
 - SPICE (Simulation Program with Integrated Circuit Emphasis) is used to analyze and verify circuit behavior before fabrication. It accurately simulates voltage, current, delay, and power at the transistor level, helping designers predict performance and detect errors early in the design process
### NMOS design and specifications

-   It is a four terminal deive
-   It consists of a P-substrate body
-   An isolation region created from SiO2 is present
-   n+ diffusion region is present near the SiO2 layer
-   It has a Gate oxide layer
-   A Poly-Si or metal gate layer is added on top of the gate oxide layer
-   There are a few abbreviations:
    -   G means Gate
    -   S means Source
    -   D means Drain
    -   B means Body or Bulk
