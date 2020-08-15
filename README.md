# Pipelined-processor-in-Cpp-with-stalling-on-hazards
Ass8

Assignment_8 README
Done by:              Shubham               2018CS10641

⦁	Please make a "out.txt" file for the output of the program and "instructions.txt" for the input instructions in the same folder as Ass_8.cpp.
⦁	Instructions should be of the form "add $t1, $t2, $t3" with no extra spaces.

		In this assignment, we have implemented a pipelined version of the processor. This program implements instructions in five stages, namely "if, id, ex, mem and wb". There is no possibilty of structural hazard because we have separate instruction and data memories. But specific actions as taken if any data or control hazard is detected. Four registers are used for storing the values during the pipeline execution, implemented as struct in C++. Four registers are for IF/ID register, ID/EX register, EX/MEM register and MEM/WB register.
Instruction memory: Instructions are read from a input file "instructions.txt" and stored in the instruction memory. Instruction memory is of the type <vector<vector<string>>. For ex, "add $t1, $t2, $t3" would be stored as {"add", "$t1", "$t2", "t3"} on the instruction memory.
Data memory: Data memory is an array of integers.
Action on a Data hazard or Control hazard:  If any data hazard is detected, the pipeline is stalled. Stalls are implemented as inserting "nop" instructions which do nothing(No operation). After some specific no of stalls, the nop's from the instruction memory are removed as soon as the hazards are safe to allow further instructions to proceed normally.
Output: Output is written to the "out.txt" file. It prints the register and memory first. Then, during each cycle, the program print the instruction number which is in the stage1, 2, 3, 4 and 5, the register file contents and the data memory.
 
	
