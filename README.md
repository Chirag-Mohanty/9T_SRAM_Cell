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

## **3.Methodology and Schematic**
- This project is mainly targeted for the following specifications:-
  - Memory Size - 1k x 32bit,
  - Operating voltage - 5V,
  - Technology -  0.5um SCMOS
  - Tools used: Sue2, NGspice, Magic

- Design Description  
  - The upper sub-circuit is essentially a 6T SRAM cell.
  - The two write access transistors (M3 and M4) are controlled by a write signal (wl).
  - The data is stored within this upper memory sub-circuit. 
  - The lower sub-circuit of the new cell is composed of the bit-line access transistors (M7 and M8) and the read access transistor (M9). 

- Schematic
  - ![image](https://user-images.githubusercontent.com/72131007/100839185-d00bb180-3499-11eb-86b9-cd45ca01ffe3.png)

## **4.Operation**
- During Write Operation
  - wl signal transitions high while RD is maintained low, M9 is cutoff. The two write access transistors M3 and M4 are turned on. In order to write a “0” to Node1, bl and blb       are discharged and charged, respectively. A “0” is forced into the SRAM cell through M3. Alternatively, for writing a “0” to Node2, bl and blb are charged and discharged,       respectively. A “0” is forced onto Node2 through M4.
- During Read Operation
  - RD signal transitions high while wl is maintained low. The read access transistor M9 is activated. Provided that Node1 stores “1”, bl is discharged through M7 and M9.           Alternatively, provided that Node2 stores “1”, the complementary bit line (blb) is discharged through M7 and M9. Since M3 and M4 are cutoff, the storage nodes Node1 and         Node2 are completely isolated from the bit lines during a read operation. 
  - Unlike the 6T SRAM cell, the voltage of the node which stores “0” is strictly maintained at the ground level during a read operation with the proposed circuit technique. The     read stability of the 9T SRAM cell is thereby enhanced as compared to a standard 6T SRAM cell.
  
  
