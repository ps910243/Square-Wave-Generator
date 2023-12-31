# Square-Wave-Generator
Square Wave Generator Abstract: The Intel MCS-51 is a single chip microcontroller series developed by Intel in 1980 for use in embedded systems. The architect of the Intel MCS-51 instruction set was John H. Wharton. Intel's original versions were popular in the 1980s and early 1990s, and enhanced binary compatible derivatives remain popular today.
Objective:
To generate Square Wave using Embedded C in Keil uvision 5 software.
Software requirements: KEIL uvision 5, Embedded C
Realistic constraints: This model demo basic utilization of 8051 microcontroller Embedded C
programming
Procedure: Step 1: Step 2: Step 3: Step 4: Step 5: Step 6: Step 7: Step 8:
   Download the Keil Uvision IDE
To initiate the programming you must create a project using the keil Uvision IDE Selecting the type of device you are working with
Adding C files to your project
Adding C files to your project
Compiling and building the C project using Keil Uvision IDE
Generating the hex file using Keil Uvision IDE
Burning the hex code into 8051 microcontroller
      
Code:
#include <reg51.h> sbit pin = P1^0; void main()
{
P1 = 0x00;
TMOD = 0x09; loop:TL0 = 0xAF;
// include 8051 register file
// decleare a variable type sbit for P1.0
// clear port
// initialize timer 0 as 16 bit timer
// load valur 15535 = 3CAFh so after
// 50000 counts timer 0 will be overflow
// send high logic to P1.0 // start timer
// wait for first overflow for 50 ms // again reload count
// now send 0 to P1.0
// wait for 50 ms again
// continue with the loop
TH0 = 0x3C;
pin = 1;
TR0 = 1;
while(TF0 == 0) {}
TL0 = 0xAF; TH0 = 0x3C; pin = 0;
while(TF0 == 0) {} goto loop;
}
