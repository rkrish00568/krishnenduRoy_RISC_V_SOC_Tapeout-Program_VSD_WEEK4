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
![nmos image](images/nmos.png)
•	Threshold Voltage (Vt)

  - The 'Vgs' voltage at which 'Strong Inversion' occurs is known as Threshold Voltage (Vt)

•	Concept of Strong Inversion

  - The phenomenon at which a part of the P-substrate becomes N-substrate (due to the high Vgs value) is called 'Strong Inversion'

•	Impact of Source-to-bulk Voltage (Vsb)

  - In presence of substrate bias voltage 'Vsb', an additional potential is required for strong inversion to occur

•	Threshold Voltage Equation

![Threshold voltage equation](images/thrs.png)

where
  - Vto is the Threshold Voltage when Vsb = 0
  - Vto is a function of manufacturing voltage
  - ϒ is the body effect coefficient and it expresses the impact of changes in body bias 'Vsb' (unit of ϒ is V^0.5)
  - фf is the Fermi Potential

•	Body Effect Coefficient expression

![body effect coeffecient equation](images/body.png)

where
  - εsi is the relative permitivity of silicon (=11.7)
  - NA is the doping concentration
  - q is the charge of an electron
  - Cox is the oxide capacitance

•	Fermi Potential Equation

![fermi potential equation](images/fermi.png)

where
  - ni is the intrinsic doping parameter for the substrate
