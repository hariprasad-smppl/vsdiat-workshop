# vsdiat-workshop
  # Day - 1
  # Introduction to QFN-48 package, chip, pads, core, die

![image](https://github.com/user-attachments/assets/df8b876a-98e0-4bcf-a5be-2266474e3cda)

We are discussing inside the chips.

This board can be represented as a block diagram.

![image](https://github.com/user-attachments/assets/127bd954-b7bc-462a-a076-97463b017682)


chip diagram/ Package diagram of the chip in Arduino 
![image](https://github.com/user-attachments/assets/28cdd1e0-f058-4503-9f6e-2ade585ba34c)


An Arduino board drives all the pins.

Chip to I/O pad connections shall be made as shown in the diagram.

![image](https://github.com/user-attachments/assets/1d4eb3c3-d5e3-4e4f-a952-d44556b63b78)

PADS allows one to communicate with the external world

The core is where actual digital logic sits.

![image](https://github.com/user-attachments/assets/f7af7ad4-e3c3-4450-92d4-74c441553835)




RISC-V Design, as shown in the figure

![image](https://github.com/user-attachments/assets/7f624d52-e60a-4334-b638-b3af40f5c5c9)

consists of the PLL, SRAM, CORE, DAC, ETC

Some are foundry IPs.
![image](https://github.com/user-attachments/assets/419ba4f9-675b-4005-ae2e-444babd19d21)


All performances of chips depend on foundry IP

![image](https://github.com/user-attachments/assets/35ffc3ba-1d2b-41b7-a4dd-b04d0d800e3d)

The foundry is a big factory with machines where chips are manufactured. VLSI engineers continuously communicate with the foundry 

![image](https://github.com/user-attachments/assets/b0575bcc-aab7-4179-a9a4-e0854974e943)

![image](https://github.com/user-attachments/assets/c154e2e5-227a-4cd2-88ac-3bb9ed65ce8b)

The foundry usually provides some interface files to communicate with the foundry. 

  # RISC V ISA

ISA is the way we talk to the computer 

![image](https://github.com/user-attachments/assets/f99665a1-4786-4e96-b5ea-057f7f87b243)


C program is compiled and converted to assembly >>, and then to machine-level language.

The binary is in ones and zeros, which hardware can understand. 

Then, each bit will be executed on the hardware. 

![image](https://github.com/user-attachments/assets/f535aba2-b146-4604-a959-ade770a98ff8)

The RTL2GDS flow starts with the RISC V architecture and is then converted to Layout.

but the user will be just executing the 'c' program

HOW does Application software run on the Hardware?

![image](https://github.com/user-attachments/assets/ae53ef77-68fe-43a0-afd5-eabfed6d6204)


OS handles IO operations and memory. 

then the compiler converts these to machine language 

the output of the application is small c/c++ functions --> then converted to instruction sets suitable for the process


![image](https://github.com/user-attachments/assets/abc38030-74c9-4482-aac7-ea81d3652ee4)


#SOC Design using Openlane

To design, we need RTL IPs, EDA tools, PDK( Process design kit) data


![image](https://github.com/user-attachments/assets/a848142e-4891-4467-9f7c-914e6b535b1f)

In open source - we have a lot of RTL sources.

We also many academics based EDA tools 

![image](https://github.com/user-attachments/assets/2b1c3022-94d5-43bd-b261-56c0403cd020)


What is PDK?

* In the "age of gods!" the design of IC was tightly integrated with manufacturing processes available with each company
* Lynn Conway and Carver Mead envisioned the need to separate the design from the technology


![image](https://github.com/user-attachments/assets/370015f6-3c33-4c7e-b865-8eff1f0706df)


Since then, we have started seeing. 


But These PDK are covered under NDA, So Google worked on the opernsource PDK

![image](https://github.com/user-attachments/assets/f08a6266-72af-4f0b-9f73-9d607869d95f)

Now, we have all the elements for the ASIC design.


![image](https://github.com/user-attachments/assets/223d4dce-ecee-455d-a871-d59dc9d0ac76)


The cutting edge is 5nm, but the 130nm is fast enough?

![image](https://github.com/user-attachments/assets/5d8dbbc8-eeac-4a4a-8ac9-8ed61900cc99)

for all the performance advance nodes not required 

130nm is still valid for many applications 

![image](https://github.com/user-attachments/assets/ea82032c-2289-41e6-922b-19c2c35a2e4d)

Pipelined of the above CPU can 1GHz

![image](https://github.com/user-attachments/assets/e7f53a84-1bce-4f79-8ee2-3da49f907bca)

ASIC design is a complex process that requires a lot of complex steps.
![image](https://github.com/user-attachments/assets/e6394d82-0229-465e-bb34-88e7eb30f4c8)


The main objective from RTL to GDS (the format used by the final layout)


![image](https://github.com/user-attachments/assets/02d8fdcf-63fd-4139-8c44-bc08512a565a)


# Simplified RTL to GDS flow

![image](https://github.com/user-attachments/assets/7b43e345-156e-4032-98fb-3df853619231)

* Synthesis

![image](https://github.com/user-attachments/assets/a6cdf5ac-5f16-4ed0-ae8b-c2c92761df99)

Resultant circuit represented in HDL - In terms of gate level netlist 

![image](https://github.com/user-attachments/assets/29914adf-78c2-42de-8548-141af55f1e5b)

Building blocks - Standard cell

![image](https://github.com/user-attachments/assets/3cf91d82-0fe9-4b5e-8ab5-eded0893e6c3)

It also consist of a delay model, electrical model etc

* Floor and power planning

- Depends on whether you are implementing a single component or whole chip
The objective here is to create an area and robust power distribution.

![image](https://github.com/user-attachments/assets/f9316768-2f30-4569-93b4-67f0eb075c3c)

![image](https://github.com/user-attachments/assets/d3464f46-4a13-45e1-8c6e-42f2dacf05bf)

In power planning, power network is constructed
![image](https://github.com/user-attachments/assets/6b2b5d98-cbf8-40a9-8ca0-cf10345f76c3)

The chip is powered by multiple VDD and the GND pins 

vertical and horizontal metal straps

such parallel structures are meant to reduce the resistance 

Typically power distribution networks uses upper metal layer 

They are thicker than lower metal layer, hence less resistance 


* Placement



![image](https://github.com/user-attachments/assets/be53e23a-8149-47ed-845e-eb5f70608aff)


connected cells should be placed close to each other - to reduce interconnect delay also to enable successful routing 

Typically cell placement done in two steps.

 ![image](https://github.com/user-attachments/assets/170f3799-c604-40a7-937b-580d2750198c)

 Global placement, followed by detailed placement 

 ![image](https://github.com/user-attachments/assets/15b890e9-70ae-421b-b440-ec306b6bbd0e)

 Global placement tries to find the optimal positions for all cells; those positions may not be legal - they may go off rows or overlap.

 ![image](https://github.com/user-attachments/assets/9b187ba8-2699-4c77-a9e1-db921d723491)

 positions obtained from the global placements are minimally altered 
* Clock tree synthesis

![image](https://github.com/user-attachments/assets/11bc30b6-a6e5-475a-b7a6-0acf191a1d7a)


We need to focus on minimum skew and minimal latency. 

* signal routing

![image](https://github.com/user-attachments/assets/087ee88c-8207-48c5-9189-236432e7920f)


router uses available metal layer to route as per PDK - PDK defines pich, tracks, and minimum width

Sky Works defines - 6 layers 

- lower interconnect layer
- The remaining 5 layers are aluminium layers
- 

![image](https://github.com/user-attachments/assets/e2fe505c-8968-4c9f-997f-840fb0bfcc14)

most of the routers are grid router 

* Signoff

![image](https://github.com/user-attachments/assets/37df54e2-186d-44fe-b612-849497c22382)


![image](https://github.com/user-attachments/assets/bd0cdce6-5029-400b-a5d0-14e6af6c2941)


For standardizing the opensource chip flow easier - efabless created a flow and called it as openlane

![image](https://github.com/user-attachments/assets/51c5fc3c-42a4-4646-a4d7-a332bd72a3bd)

![image](https://github.com/user-attachments/assets/d19a5962-6d2b-414e-823d-436ece557e40)


![image](https://github.com/user-attachments/assets/8fc56e9f-b726-45b6-9e18-49993d1a74fc)

![image](https://github.com/user-attachments/assets/4eb99f07-8208-4b50-8982-30e16f4395e8)


Handling timing violations is still work in progress.

![image](https://github.com/user-attachments/assets/0efa6c2c-684e-48ae-ac4c-5c496c225493)

![image](https://github.com/user-attachments/assets/4acbbe58-eda4-4580-b363-7447cd7080d6)



![image](https://github.com/user-attachments/assets/69b6ca68-400b-4790-bd57-02337a3a73fb)

![image](https://github.com/user-attachments/assets/78ccb8ae-cf31-41a3-9505-cef36f371d98)

![image](https://github.com/user-attachments/assets/81b31779-1630-4f9a-9714-bdadf70652bb)


# OPENLANE ASIC Design flow 

![image](https://github.com/user-attachments/assets/ffbcb73c-1b07-4227-bf18-0ba8130e1d0d)


![image](https://github.com/user-attachments/assets/be3d308c-dee6-410c-9398-0c89cfc52c6b)

synthesis exploration shows delay vs area affected by synthesis strategy

based on this exploration we can take the best strategy 

![image](https://github.com/user-attachments/assets/d0b3f6da-a167-4f6b-b77b-ce70a5a99a5e)

![image](https://github.com/user-attachments/assets/c8e5ad72-e14e-4d9c-b7ee-f8dedd612d2d)

* DFT:

This step uses open-source project fault 

![image](https://github.com/user-attachments/assets/ce145eba-ebbe-4d65-a547-17963c0061e4)

here fault adds extra logic - these scan chains can be used for fabrication for testing 


* Physical implementation

These are done using the OpenRoad - app

![image](https://github.com/user-attachments/assets/d94f4082-5234-4866-ba11-3616860727d7)

Since PD involves some level of optimization, we need to do logic equivalence checking of synthesis ( can be done using Yosis)

* LEC

![image](https://github.com/user-attachments/assets/1e270764-a9ff-4e9d-8a17-196dd1536372)


* Antenna rule violation

![image](https://github.com/user-attachments/assets/cc8718de-9e36-4a15-a49b-1b092c65d236)

![image](https://github.com/user-attachments/assets/579c210a-26b1-4331-9fc1-be9687cd9011)

![image](https://github.com/user-attachments/assets/155bff23-bc17-4c1b-8fbb-41672ef6382b)


there are two approach - openroad and openlane approach 

* Signoff

![image](https://github.com/user-attachments/assets/33d75008-627a-484d-8955-3a0e47412427)


![image](https://github.com/user-attachments/assets/1256da42-1414-4a03-8c69-db05df93f847)


# LAB Session using Openlane tool

* Openlane is not a tool, it is set of different opensource tools ( Yosys, openSTA ......)

* complete RTL2GDS without human intervenstion

* almost similar to commercial tool



* Some of the important Linux commands
  - cd: change directory
  - files for the workshop present in work/tools/
 

![image](https://github.com/user-attachments/assets/478056b8-3b30-4f2a-ace8-452da04d00c1)


* ls -lts : displays the folders and files in chronological order

![image](https://github.com/user-attachments/assets/f5d4d601-295f-4ac2-b1a6-d4ce8dc7fe7b)

* to get help on any command you can use the command --help

* we can clear the screen with clear command

Before clear
![image](https://github.com/user-attachments/assets/214320ef-9472-4a35-86a8-e0282ead05de)


After clear 
![image](https://github.com/user-attachments/assets/0fffccc9-c3a9-40c2-a9c2-3af10c56a239)


change the working directory to openlane working directory 

![image](https://github.com/user-attachments/assets/8a401287-ade4-42d7-b3d6-6242d0faa3d0)


we will be seeing two directories:

Openlane and PDK - we will be working on openlane

![image](https://github.com/user-attachments/assets/03243d4f-29d3-40c8-91b9-67f6d4e47d34)

![image](https://github.com/user-attachments/assets/9bf08273-1708-4de6-94f0-48d31ca794e9)

sky130A is compatible with our opensource tool chains 


![image](https://github.com/user-attachments/assets/75ec6cc7-f5a9-4d43-aca3-31522d9c205e)
lib.ref contains process specific files 
.tech specific to the tool

![image](https://github.com/user-attachments/assets/fc6536fb-ef01-4dbe-a875-d994f51ad821)

![image](https://github.com/user-attachments/assets/bb9ae544-ce07-46c3-afac-6812e7a8cf10)

libs.tech has following files 

![image](https://github.com/user-attachments/assets/eddf4600-1259-4dc0-b54a-9fb3a7432329)


nomenclature sky130< process name>_fd< foundry name>_sc< standard cell>


we will be working on openlane directory 


run docker using **docker command** 

change the directory to openlane

type command ./flow.tcl -interactive

The above command helps to do the step-by-step process 

![image](https://github.com/user-attachments/assets/e2258626-1646-43b5-a5d5-745fe5ef414c)




























































 

 


 
































































