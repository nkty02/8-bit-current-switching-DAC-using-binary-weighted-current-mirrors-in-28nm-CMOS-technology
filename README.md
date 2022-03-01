# 8-bit current switching DAC using binary weighted current mirrors
The design of an 8-bit current switching DAC employing binary weighted current mirrors is available in this repository. It is based on the Synopsys Custom Compiler and is manufactured on the 28nm technology node.

# Table of contents
- [Abstract](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology#abstract)
- [Detailed Explanation with reference Block diagram](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#detailed-explanation-with-reference-block-diagram)
- [Tool used](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#tool-used)
- [MOS Switch](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#mos-switch)
- [8-bit current switching DAC using binary weighted current mirrors](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#8-bit-current-switching-dac-using-binary-weighted-current-mirrors-1) 
- [Simulation results](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#simulation-results)
- [Transistor count for 8-bit current switching DAC using binary weighted current mirrors](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#transistor-count-for-8-bit-current-switching-dac-using-binary-weighted-current-mirrors)
- [Netlist](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#netlist)
- [Author](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#author)
- [Acknowledgements](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#acknowledgements)
- [Reference](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/edit/main/README.md#reference)

# Abstract
Many systems use digital-to-analog converters (DACs),including communication transmitters and consumer devices. 
Among the several DAC realisations, the current switching topology has a notable advantage over others in
that it can drive resistive loads without the requirement of a buffer. The goal of this project is to design 
an 8-bit current-switching digital-to-analog converter (DAC) in 28-nm CMOS utilising a cascode current mirrorarchitecture. 
The 8-bit binary input spans a voltage range of -1 to 1 V. Due to faulty mirroring and parasitic capacitances, 
major glitching issues arose during the design process, which were resolved with the introduction of an RC filter. 
An overall swing of 500 mV is achieved. 

# Detailed Explanation with reference Block diagram

We want to convert Din , an N-bit digital signal, to
Iout, an analog current. This can be achieved as shown
in below figure, where each input bit controls a binarily
weighted current in relation to a unit value, I<sub>0</sub>. The least
significant bit (LSB) is D<sub>0</sub>, and the most significant bit
is D<sub>N−1</sub> (MSB). From one bit to the next, the current
sources are scaled up by a factor of two, providing
Iout = D<sub>N−1</sub> (2N−1I<sub>0</sub>) + · · · + D<sub>1</sub> (2I<sub>0</sub>) + D<sub>0</sub>I<sub>0</sub>.
The sizes of transistors intended to transport I<sub>0</sub>, 2I<sub>0</sub>,
.., 2(N−1) I<sub>0</sub> must be scaled proportionately. Instead of
increasing the width, we use a number of transistors
in parallel based on the current they must carry while
maintaining the same size of each unit. This is done to
reduce noise, increase linearity, and eliminate issues that
arise from mismatches between them.

![image](https://user-images.githubusercontent.com/75198926/155963000-abb5aeec-7a3d-4309-b4b1-5d0aedf99b53.png)

## Design specifications of this project :

|  |  |
| :-------------: | :-------------: | 
| Supply Voltage V<sub>dd</sub> | 1.2 V |
| Golden current source  | 0.01mA |
| Output swing  | 550mV |
| Topology  | Binary-weighted |
| Load resistance  | 200 ohm |
| Load capacitance  | 0.01uF |

# Tool used
#### Synopsys Custom Compiler : 
The Synopsys Custom Compiler™ design environment is a cutting-edge solution for designing full-custom analogue, custom digital, and mixed-signal integrated circuits. 
Custom Compiler, the heart of the Synopsys Custom Design Platform, offers design entry, simulation management and analysis, and custom 
layout editing features. On a transistor level, this tool was utilised to design the circuit.

#### Synopsys Primewave :  
PrimeWave™ within the Synopsys Custom Design Platform, the Prime Wave Design Environment is a comprehensive and versatile environment for simulation setup and analysis 
of analoge, RF, mixed-signal design, custom-digital, and memory designs. This tool aided in numerous simulations of the above-mentioned circuit.

#### Synopsys 28nm PDK :  
The Synopsys 28nm Process Design Kit was used to construct and simulate the given circuit design (PDK).

# MOS Switch

#### Switch schematic

![switch_schematic](https://user-images.githubusercontent.com/75198926/156119653-eff10d23-1947-4dcc-a783-7f7f09bee1af.png)


#### Switch symbol

![switch_symbol](https://user-images.githubusercontent.com/75198926/156119711-c87b2007-61ed-4c7b-adb9-5d4c80ec1e23.png)


# 8-bit current switching DAC using binary weighted current mirrors

#### 8-bit DAC schematic

![sch_dac](https://user-images.githubusercontent.com/75198926/156120002-5b40e130-3304-42c5-a09d-09797b5e6bc9.png)


#### 8-bit DAC symbol

![sch_dac_symbol](https://user-images.githubusercontent.com/75198926/156120087-a0f81fe8-438a-4741-ace1-6657863c29ce.png)


#### 8-bit DAC testbench

![sch_dac_tb](https://user-images.githubusercontent.com/75198926/156120198-267ef1e4-f82e-4921-8acc-65af82897f9e.png)


# Simulation results

### Plot of inputs D<sub>0</sub> to D<sub>7</sub> and output V<sub>out</sub> respectively 

![f6](https://user-images.githubusercontent.com/75198926/156120246-76f9ac97-32ed-4b1a-bf77-f4eb6ef6754d.png)

![f5](https://user-images.githubusercontent.com/75198926/156120296-4e4bab5f-6976-4601-8ce8-c964eaec3380.png)

### Plot of input D<sub>0</sub>  

![f8](https://user-images.githubusercontent.com/75198926/156120382-3d9bbcc9-f94a-4127-91f4-3f397c886646.png)

### Plot of input D<sub>1</sub>  

![f9](https://user-images.githubusercontent.com/75198926/156120419-9c537872-d02e-47b9-80b7-025f7f8f5693.png)

### Plot of input D<sub>2</sub>  

![f10](https://user-images.githubusercontent.com/75198926/156120506-580b3068-4f95-4bb0-bac8-26646976fd10.png)

### Plot of input D<sub>3</sub>  

![f11](https://user-images.githubusercontent.com/75198926/156120821-26720e48-a47c-481b-828c-a9d0fa925957.png)

### Plot of input D<sub>4</sub>  

![f12](https://user-images.githubusercontent.com/75198926/156120841-22b10f70-1159-492f-8bef-dad3bfc49259.png)

### Plot of input D<sub>5</sub>  

![f13](https://user-images.githubusercontent.com/75198926/156120860-cc6b377e-b25c-4368-bbe0-cdc06d1c3da8.png)

### Plot of input D<sub>6</sub>  

![f14](https://user-images.githubusercontent.com/75198926/156120874-b5022aaf-9ca2-458c-91f0-884d02249de5.png)

### Plot of input D<sub>7</sub>  

![f15](https://user-images.githubusercontent.com/75198926/156120891-5506e0fe-8a7e-4eff-bbed-92fd31fbeb2c.png)

### Plot of ramp output V<sub>out</sub>  

![fff](https://user-images.githubusercontent.com/75198926/156120909-d7eca075-0a7f-45e8-b6e4-ce3681942e3f.png)

### Plot of zoomed ramp output V<sub>out</sub>  

![step](https://user-images.githubusercontent.com/75198926/156120962-57c18d1e-652d-48c7-9cfd-81a4b1826857.png)


# Transistor count for 8-bit current switching DAC using binary weighted current mirrors

| Block name | Number of Block | Transistor count per block | Total transistor count |
| ------------- | :-------------: | :-------------: | :------------: |
| Mos switch  | 8  | 500 | 4000 |
| 8-bit DAC  | 1  | 512 | 512|

`Total transistor count` = 4512

# Netlist

8-bit DAC circuit netlist is available [here.](https://github.com/nkty02/8-bit-current-switching-DAC-using-binary-weighted-current-mirrors-in-28nm-CMOS-technology/blob/11e789418e5378aed5ba05a995567fd72c1eca6c/netlist.txt)

# Author 

Khyathi N, B.Tech in Electronic and Electrical Communication Engineering at Indian Institute of Technology(IIT) Kharagpur, Kharagpur - 721302

# Acknowledgements
[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836/)

[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

[Synopsys India](https://www.synopsys.com/)

# Reference

[B. Razavi, “The current-steering dac,” IEEE SOLID-STATE CIRCUITS MAGAZINE, pp. 1–5, 2018.](http://www.seas.ucla.edu/brweb/papers/Journals/BRWinter18DAC.pdf)


[A. Anshul, “Design of low power 8-bit digital-to-analog converter with good voltage-stability.” Center for VLSI andvEmbedded System Technologies, IIIT Hyderabad, 2013, pp. 4–
46.](https://web2py.iiit.ac.in/research_centres/publications/download/mastersthesis.pdf.b2d1fe81ef0aa0ae.416e7368756c204167617277616c202832303034333130303129202d204d53207468657369732e706466.pdf)


[Taoufiq Bellamine, "8 Bit Current Steering DAC," A project for ECE 547 “VLSI Design”, pp. 5-20, 2007.](https://ece.umaine.edu/wp-content/uploads/sites/203/2012/05/Taoufiq_Bellamine_ECE547Report.pdf)
