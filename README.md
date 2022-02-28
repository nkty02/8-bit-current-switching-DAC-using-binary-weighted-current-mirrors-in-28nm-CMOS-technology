# 8-bit current switching DAC using binary weighted current mirrors
The design of an 8-bit current switching DAC employing binary weighted current mirrors is available in this repository. It is based on the Synopsys Custom Compiler and is manufactured on the 28nm technology node.

# Table of contents
- [Abstract]()
- [Detailed Explanation with reference Block diagram]()
- [Tool used]()
- [MOS Switch]()
- [8-bit current switching DAC using binary weighted current mirrors]() 
- [Simulation results]()
- [Transistor count for 8-bit current switching DAC using binary weighted current mirrors]()
- [Netlist]()
- [Author]()
- [Acknowledgements]()
- [Reference]()

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

#### Switch symbol

# 8-bit current switching DAC using binary weighted current mirrors

#### 8-bit DAC schematic

#### 8-bit DAC symbol

#### 8-bit DAC testbench

# Simulation results

# Transistor count for 8-bit current switching DAC using binary weighted current mirrors

# Netlist

# Author 

Khyathi N, B.Tech in Electronic and Electrical Communication Engineering at Indian Institute of Technology(IIT) Kharagpur, Kharagpur - 721302

# Acknowledgements
[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836/)

[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

[Synopsys India](https://www.synopsys.com/)

# Reference


