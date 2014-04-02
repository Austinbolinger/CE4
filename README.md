CE4
===
##Tests
A)	Reading the requirements for part A, I noticed that it was simple code that required doing the something three times repeatedly. I wrote out pseudo code as follows:
Store 9 in BO (RAM)
Store 8 in C4 (RAM)
Store B in CB (RAM)
Then, I looked up syntax that would allow me to store operand values in the accumulator with the Table 1. PRISM Instruction Set. I also looked for a method that would store the accumulator value to the RAM. This step, it was helpful to remember that labels would act as pointers. The actual code required LDAI and STA three times.
LDAI 9
STA Label1
LDAI 8
STA Label2
LDAI B
STA Label3
Then a JMP was required to loop it back to the beginning of the code.

B)	My first step to understanding this part was again pseudo code.
Retrieve value from B0
Double value (add itself to itself)
Subtract 4 (Add 4’s 2’s compliment)
Output to 4
*run a test in the beginning for negatives
I then used the Table 1. PRISM Instruction Set to determine what instructions I should use. 
JN (a test that skips to the loop if the number is negative)
LDAD (loads from RAM B0)
ADDD (reads RAM B0 and adds it to accumulator)
ADDI (subtract four = add $C) 

C)	Again, I started out with pseudo code.
Read in from port 3
Output to port 0
Subtract 1
Output to port 1
Subtract 1 again
Output to port 2
Repeat
I noticed a pattern of subtract and output. After reading in the input, I just subtract than output repeat. When I got to the bottom of the coding I had to add to get back to original value.
IN 3
OUT 0
ADDI F (2’s compliment of 1, and equivalent to subtracting 1)
OUT 1
ADDI F (2’s compliment of 1)
OUT 2
ADDI 1 (add one to get one less than original number)
JMP (loop back to first output)

#####Documentation
C3C Hayden suggested and explained the concept of 2's compliment adding instead of subtracting.
