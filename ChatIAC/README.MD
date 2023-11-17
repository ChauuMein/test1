# Lab 4 Task 4: Testing and verification

This task involves writing a testbench to verify the functionality of our single-cycle RISC-V CPU design.   

The external signals that would interact with the testbench are the I/O signals of the CPU as a whole. \

![Alt text](image.png)

From the top-level diagram, the external signals (shown in <font color=RED> red <font color= white>) would be: 

- "clk" (CLOCK), the clock input to the CPU 
- "rst" (RESET), an input to the CPU that initialises the system 
- "a0" (OUTPUT REGISTER), the output from the CPU that we can use to check correct operation of the program

All other signals are internal to the CPU and hence not relevant to the CPU testbench. 


## Verification in the testbench
Aside from the standard C++ testbench syntax, to verify if the design works and to limit human interaction I added some checks. \
An example case is necessary for testing. Based on the example case, we will have an expected value of the output a0, expected_a0. In the testbench, if the actual output top->a0 != expected_a0, an error message will be printed and the testbench program will exit immediately. \
The error message will contain the current cycle (which cycle the failure occured at), the expected value (expected_a0) and the current value (top->a0).
