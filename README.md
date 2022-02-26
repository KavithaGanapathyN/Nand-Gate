# 3-Input Nand-Gate
This repository presents the design of 3_Input Nand Gate implemented using Synopsys Custom Compiler on 28nm CMOS Technology.
# Table of Contents
- [ABSTRACT](https://github.com/KavithaGanapathyN/Nand-Gate/blob/main/README.md#table-of-contents)
- [INTRODUCTION](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#introduction)
- [TRUTH TABLE](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#truth-table)
- [REFERENCE CIRCUIT](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#reference-circuit)
- [TOOLS](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#tools)
- [PARAMETER SET FOR PULSE](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#parameter-set-for-pulse)
- [SYMBOL](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#symbol)
- [LAYOUT DESIGN](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#layout-design)
- [TRANSIENT SETTINGS](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#transient-settings)
- [NETLIST](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#netlist)
- [WAVEFORM](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#waveform)
- [REFERENCES](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#references)
- [ACKNOWLEDGEMENTS](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#acknowledgements)
- [AUTHOR](https://github.com/KavithaGanapathyN/Nand-Gate/edit/main/README.md#author)
# ABSTRACT
The Logic gates are used to carry out logical
operations using single or multiple binary inputs and a single
binary output. The input and output of a logic gate are based on
certain logic, which is explained using Boolean algebra. Boolean
algebra uses only two variables zero or one. The most basic type
of logic gates are OR gate, AND gate and NOT gate. In addition
to the basic logic gate, there are combination gates like NAND
gate, NOR gate, XOR gate, etc made by combining basic logic
gates in different ways.The NAND gate or “NotAND” gate is the
combination of two basic logic gates, the AND gate and the NOT
gate connected in series. The NAND gate and NOR gate can be
called the universal gates since the combination of these gates
can be used to accomplish any of the basic operations. Hence,
NAND gate and NOR gate combination can produce an inverter,
an OR gate or an AND gate.

# INTRODUCTION
The output of a NAND gate is high when either of the
inputs is high or if both the inputs are low. In other words,
the output is always high and goes low only when both the
inputs are high.. It consists of three series nMOS transistors
between OUT and GND and three parallel pMOS transistors
between OUT and VDD. If any one of the inputs in1 or in2
or in3 is 0, at least one of the nMOS transistors will be OFF,
breaking the path from OUT to GND. But at least one of the
pMOS transistors will be ON, creating a path from OUT to
VDD. Hence, the output OUT will be 1. If all the inputs are
1, all the nMOS transistors will be ON and all the pMOS
transistors will be OFF. Hence, the output will be 0.[1]


# TRUTH TABLE

![101](https://user-images.githubusercontent.com/100337285/155830212-9ec326b2-a97d-45e0-b71f-23036cd78007.png)

                    fig1:Truth Table for 3_input_Nand Gate

# REFERENCE CIRCUIT
![102](https://user-images.githubusercontent.com/100337285/155830422-c70a175a-c13a-436d-ba9b-712b008fd18b.png)


                    fig2:Reference Cirucit for 3_Input_Nand Gate

# TOOLS
Synopsys Custom Compiler
The Synopsys Custom Compiler design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. It delivers industry-leading productivity, performance, and ease-of-use while remaining easy to adopt for users of legacy tools.
The waveform can be simulated by using Synopsys Primewave that is useful for simulation setup and analysis of analog,RF,mixed-signal design within the Synopsys Custom Design Platform
It uses 28nm PDK for creation and simulation of the designed circuit.

# PARAMETER SET FOR PULSE

![104](https://user-images.githubusercontent.com/100337285/155830969-c59ff3e4-3b2b-42fc-9f7f-9d881de8f143.png))

                 fig3:Parameter Setup
# SYMBOL

![104](https://user-images.githubusercontent.com/100337285/155830655-7170afc9-69e8-4f65-bbfd-78d683928ce3.png)


              fig 4: symbol for nand gate

# LAYOUT DESIGN

![103](https://user-images.githubusercontent.com/100337285/155830865-46e5efc5-87e6-40eb-b326-4204f6947645.png)

                               fig 5: Layout Design

# TRANSIENT SETTINGS

![103](https://user-images.githubusercontent.com/100337285/155831381-718a4c9e-e590-437b-9b12-c6c997b341db.png)

                                fig 6: Transient Settings
                                
# NETLIST
                *  Generated for: PrimeSim
                *  Design library name: kavi
                *  Design cell name: nand_tb
                *  Design view name: schematic
                .lib '/PDK/SAED_PDK32nm/hspice/saed32nm.lib' TT
             
                *Custom Compiler Version S-2021.09
                *Sat Feb 26 04:56:48 2022

                .global gnd! vdd!
                ********************************************************************************
                * Library          : kavi
                * Cell             : nand
                * View             : schematic
                * View Search List : hspice hspiceD schematic spice veriloga
                * View Stop List   : hspice hspiceD
                ********************************************************************************
                .subckt nand a b c gnd_1 out vdd vt_bulk_n_gnd! vt_bulk_p_vdd!
                 xm2 out c vdd vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
                 xm1 out b vdd vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
                 xm0 out a vdd vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
                 xm5 net13 c gnd_1 vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
                 xm4 net11 b net13 vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
                 xm3 out a net11 vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
                 .ends nand

                ********************************************************************************
                * Library          : kavi
                * Cell             : nand_tb
                * View             : schematic
                * View Search List : hspice hspiceD schematic spice veriloga
                * View Stop List   : hspice hspiceD
                ********************************************************************************
                xi0 a b c gnd! out net13 gnd! vdd! nand
                v3 c gnd! dc=0 pulse ( 0 1.05 0 0.1u 0.1u 8u 20u )
                v2 b gnd! dc=0 pulse ( 0 1.05 0 0.1u 0.1u 6u 15u )
                v1 a gnd! dc=0 pulse ( 0 1.05 0 0.1u 0.1u 5u 10u )
                v4 net13 gnd! dc=1.05
                c6 out gnd! c=1p








                .tran '1u' '20u' name=tran

                .option primesim_remove_probe_prefix = 0
                .probe v(*) i(*) level=1
                .probe tran v(a) v(b) v(c) v(out)

                .temp 25
  


                .option primesim_output=wdf


                .option parhier = LOCAL






              .end

 # WAVEFORM

![103](https://user-images.githubusercontent.com/100337285/155831927-236c82fc-e176-4f9e-bc6b-18fedf5d379d.png)


                     fig 7: Output Waveform
                                
 # REFERENCES
[1] Neil H. E. Weste Macquarie University , The University of Adelaide
and David Money Harris ,Harvey Mudd College CMOS VLSI Design
- A Circuits and Systems Perspective,4th Edition,pearson Education
India,2011

# ACKNOWLEDGEMENTS
-[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

-[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

-[Synopsys India](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

-[Sameer Durgoji, NIT Karnataka](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

-[Chinmay panda, IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

# AUTHOR

N.KavithaGanapathy,M.Tech Student at National Institute of Technology, Puducherry-609 609. 
