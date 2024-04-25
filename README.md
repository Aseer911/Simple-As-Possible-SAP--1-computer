## Simple-As-Possible-SAP-1-computer.
SAP-1 Architecture-based 8-bit Computer Design and Implementation: The Simple As Possible (SAP)-1 computer is a very basic model of a microprocessor consisting of discrete modules. Among the modules that comprise this system are an output unit, a memory unit, an ALU, a clock generator, and an instruction register which has 16 instructions in total.

#Circuit
![image](https://github.com/Aseer911/Simple-As-Possible-SAP--1-computer/assets/58761121/5b8f6748-dc34-43f0-96e7-9d9b05553156)

#Features
1. Has various modules like clock pulse generator, program counter, input unit, memory address register (MAR), accumulator, B-register, output register, RAM (16x8 bit), arithmetic and logic unit (ALU),     instruction register, controller/sequencer, binary display, and additional modules like C register, D register, and sign display.
2. Can perform basic operations like loading data (LDA), addition (ADD), subtraction (SUB), and output (OUT) through corresponding instructions.
3. Has a 5 T-state cycle for executing instructions.
4. The clock pulse generator has both automatic (astable multivibrator) and manual (monostable multivibrator) modes.
5. Implements combinational circuits for various control and data selection operations.
6. Has a 16x8 bit RAM designed using basic S-R latches and gates.
7. The ALU can perform addition and subtraction (using 2's complement method) on 8-bit data.
8. The controller/sequencer generates necessary microinstructions based on the macroinstruction and T-state.
9. Has a binary-to-BCD converter to display the output in binary-coded decimal form.

#T-States
The SAP-1 computer executes instructions in a sequence of 5 T-states (T1 to T5):
T1: The instruction is fetched from memory (RAM) into the instruction register by enabling the RO (RAM Output) and II (Instruction Register Load) microinstructions.
T2: The program counter is incremented by enabling the CE (Counter Enable) microinstruction to fetch the next instruction.
T3: For different instructions, different microinstructions are executed:
LDA: IO, MI (Transfers second nibble from IR to MAR)
ADD/SUB: IO, MI
OUT: AO, OI (Transfers data from AC to Output Register)
T4: For ADD/SUB instructions:
ADD: RO, BI (Transfers data from RAM to B register)
SUB: RO, BI, SU (Transfers data and sets SUB mode in ALU)
T5: For ADD/SUB instructions:
ADD: EO, AI, CI (Adds data in ALU, stores result in AC and C register)
SUB: EO, AI (Subtracts, stores result in AC)
The SJ (Skip Jump) microinstruction is used to skip unnecessary T-states for certain instructions like LDA and OUT.

#Microinstructions
1. CO - Sends value from program counter to bus
2. CE - Enables program counter to increment
3. MI - Allows MAR to load data from bus
4. RO - Allows RAM to send data to bus based on the addressed location
5. II - Allows instruction register to load data from bus
6. IO - Allows instruction register to send lower 4 bits to bus
7. AI - Allows accumulator to load data from bus
8. AO - Allows accumulator to send data to bus
9. CI - Sends added value from ALU to C register
10. SU - Enables ALU to perform subtraction operation
11. DI - Sends data from B register to D register
12. EO - Enables ALU to send data to bus
13. BI - Allows B register to load data from bus
14. OI - Allows output register to load data from accumulator via bus
15. SJ - Skips certain T-states as required (for LDA and OUT instructions)
16. HLT - Halts the computer operation by stopping the clock

The repository contains the detailed report and proteus simulation file.     
