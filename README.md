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
![Uploading image.png…]()









































