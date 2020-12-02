# 9T_SRAM_Cell
**Characterization of 1k 32-bit 9T-SRAM**
## Contents
- **_1. Introduction_** 
- **_2. Literature Review_**
- **_3. Methodology and Block Diagram_** 
- **_4. Operation_**
- **_5. Simulation Results_**
- **_6. Upcoming Updates_**
## **1. Introduction**
In modern high-performance integrated circuits, more than 40% of the total active mode energy is consumed due to leakage currents. Furthermore, leakage is the only source of energy consumption in an idle circuit. SRAM arrays are   important sources of leakage since the majority of transistors are utilized for on-chip memory in today’s high-performance microprocessors and systems-on-chips (SoCs). The design of a low leakage SRAM cell is, therefore, highly desirable.
In addition to the leakage power issues, the degradation of data stability in SRAM cells is another growing concern with the scaling of device dimensions and voltages in each new technology generation.

## **2.Literature Review**
A new nine-transistor (9T) SRAM cell with reduced leakage power consumption and enhanced data stability is presented. The 9T SRAM cell provides two separate data access mechanisms for the read and write operations. During a read operation, the data storage nodes are completely isolated from the bit lines. The read static-noise margin (SNM) of the proposed 9T SRAM cell is thereby enhanced by "2x" as compared to the standard 6T SRAM cells.

## **3.Methodology and Block Diagram**
-Memory Size - 1k x 32bit,

-Operating voltage - 5V,

-Technology -  0.5um SCMOS

-Tools used: Sue2, NGspice, Magic

-The upper sub-circuit is essentially a 6T SRAM cell.

-The two write access transistors (M3 and M4) are controlled by a write signal (wl).

-The data is stored within this upper memory sub-circuit. 

-The lower sub-circuit of the new cell is composed of the bit-line access transistors (M7 and M8) and the read access transistor (M9). 

