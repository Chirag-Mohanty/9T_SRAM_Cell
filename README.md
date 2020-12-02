# 9T_SRAM_Cell
**Characterization of 1k 32-bit 9T-SRAM**
## Contents
- **_1. Introduction_** 
- **_2. Literature Review_**
- **_3. Methodology and Block Diagram_** 
- **_4. Operation_**
- **_5. Simulation Results_**
- **_6. Conclusion_**
- **_7. Upcoming Updates_**
- **_8. References_**
- **_9. Acknowledgement_**
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
- **During Write Operation**
  - wl signal transitions high while RD is maintained low, M9 is cutoff. The two write access transistors M3 and M4 are turned on. In order to write a “0” to Node1, bl and blb       are discharged and charged, respectively. A “0” is forced into the SRAM cell through M3. Alternatively, for writing a “0” to Node2, bl and blb are charged and discharged,       respectively. A “0” is forced onto Node2 through M4.
- **During Read Operation**
  - RD signal transitions high while wl is maintained low. The read access transistor M9 is activated. Provided that Node1 stores “1”, bl is discharged through M7 and M9.           Alternatively, provided that Node2 stores “1”, the complementary bit line (blb) is discharged through M7 and M9. Since M3 and M4 are cutoff, the storage nodes Node1 and         Node2 are completely isolated from the bit lines during a read operation. 
  - Unlike the 6T SRAM cell, the voltage of the node which stores “0” is strictly maintained at the ground level during a read operation with the proposed circuit technique. The     read stability of the 9T SRAM cell is thereby enhanced as compared to a standard 6T SRAM cell.
  
## **5. Simulation Results**
- **Transient Response of 9T**
  - ![image](https://user-images.githubusercontent.com/72131007/100842788-5aa2df80-349f-11eb-831d-8db0f87c2cc4.png)
  - The operation of read and write of 9T SRAM cell is simulated as above.
  
- **Read Stability**
  - Static noise margin (SNM) is the metric used here to characterize the read stability of the SRAM cells. The SNM is deﬁned as the minimum noise voltage necessary which can       ﬂip the state of an SRAM cell. The static voltage transfer characteristics of the 6T and 9T SRAM cells during a read operation are shown below :-
  - Static voltage transfer characteristics of the conventional 6T SRAM
   - ![6tsnm](https://user-images.githubusercontent.com/72131007/100844879-6ba12000-34a2-11eb-93f5-6c918da9d925.PNG)
   - Taking the worst case SNM i.e. **0.38** 
  - Static voltage transfer characteristics of the 9T SRAM
   - ![9tsnm](https://user-images.githubusercontent.com/72131007/100845180-d4889800-34a2-11eb-8f38-6903e6c0ac15.PNG)
   - Taking the worst case SNM i.e. **0.85** 
  - **Hence we conclude that the SNM of the 9T SRAM is around 2x of the SNM of the 6T SRAM. So the read stability is improved in 9T SRAM.**
  
- **Layout**
  - 6T SRAM cell in 0.5um Technology
   - ![image](https://user-images.githubusercontent.com/72131007/100846037-0c440f80-34a4-11eb-80d0-a608e12ff3e1.png)
   - The area of the Layout of 6T SRAM cell is **118um²**
  - 9T SRAM cell in 0.5um Technology
   - ![image](https://user-images.githubusercontent.com/72131007/100846603-b9b72300-34a4-11eb-891c-b8fc76fb785c.png)
   - The area of the Layout of 9T SRAM cell is **153um²**
  - **So the area of 9T SRAM cell is 29.66% more than the area of the 6T SRAM cell.**

## **6. Conclusion**
- The new 9T SRAM cell is presented here is for enhancing the read SNM as compared to the conventional 6T SRAM circuits.
- The presented static memory circuit provides two separate data access mechanisms for the read and write operations.
- During a read operation, the stored data is isolated from the bitlines, thereby enhancing the read SNM by 2x as compared to the conventional 6T SRAM cells. 
- However there is an area overhead, depicting a tradeoff factor.

## **7. Upcoming Updates**
- It can be further extended for eliminating leakage power.
- It can be simulated in different PVT corners.

## **8. References**
- Sung-Mo Kang, Yusuf Leblebici, “CMOS Digital Integrated Circuits analysis and design” Tata McGraw-hill Edition, 4 Edition, ISBN: 978-0-07-338062-9. 
- 2008-Characterization of a Novel Nine-Transistor SRAM Cell by Zhiyu Liu and Volkan Kursun.

## **9. Acknowledgement**
- Dr.Saroj Rout, Associate Professor, Silicon Institute of Technology
- Mr.Santanu Sarangi, Assistant Professor, Silicon Institute of Technology
