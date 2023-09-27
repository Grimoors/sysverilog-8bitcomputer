# sysverilog-8bitcomputer
sysverilog-8bitcomputer 

A little birdie told me that I cannot possibly know sys-verilog or any ECE things, as a student of the natural Sciences in Physics, and hence Begins this foray into the sys-verilog.
@rohanGupta pls no hurts mai feelings.


## Where to start?
Logically breaking down a pc, we have RAM, ROM, CPU, Bus, Input and Output, and some more.

Specs need to be set for our sanity (or lack thereof;) and specs are hence:


1. Architecture:
    - 8-bit CPU with a basic instruction set.
    - 256 bytes of RAM for data storage.
    - Registers, ALU, and Control Unit within the CPU.
2. Instruction Set:
    2.1. Data Transfer Group:
    - Load and store operations.
    - Move data between registers and memory.
    2.2. Arithmetic Group:
    - Addition, subtraction, increment, and decrement.
    - Comparison operations and flag updates.
    2.3. Logical Group:
    - AND, OR, XOR operations.
    2.4. Branching Group:
    - Conditional and unconditional jumps.
    - Subroutine call and return.
    2.5. Machine Control:
    - NOP for no operation.
    - HLT to halt the CPU.
    - I/O Group:
    2.6. Input and output operations for interacting with external devices.
    2.7. Stack Operation Group:
    - Push and pop operations for stack handling.
3. Memory:
    - 256 bytes of RAM.
    - Separate instruction memory (size not specified).
4. I/O Ports:
    - Several I/O ports for interacting with external devices, such as LEDs, switches, seven-segment display, etc.
5. Clocks:
    - Different clock signals including CLK, CYCLE_CLK, MEM_CLK, INTERNAL_CLK.
6. Control Ports:
    - 256 8-bit control ports for host computer interaction.
    - Used for uploading programs, setting states, etc.
7. Utilities and Peripherals:
    - Seven-segment display with different display modes.
    - LED control, switch and button reading.
    - Potential for VGA output in future versions.
8. Development and Support Tools:
    - Assembler for converting assembly code to machine code.
    - Interpreter for executing programs written for the CPU.
    - Potential compiler for a C-like language (work in progress).
    - GTKWave for waveform viewing and debugging.
9. Future Plans and Optimization:
    - The roadmap includes optimization of instruction set and CPU efficiency.
    - Pipelining and reduction of cycles per instruction.
    - Addition of new features and IO capabilities.
    - Addressing limitations such as general subroutine usage, memory addressing, arithmetic operation semantics, etc.
    - This 8-bit computer, while simple and basic, provides a variety of functionalities and has the potential for expansion and optimization. The detailed specifications and future plans make it a suitable project for learning and experimenting with computer architecture and digital design.

## Planned File structure : 

In SystemVerilog, the commonly used file extensions are .sv for source files and .svh for header files. Below is the final planned file structure along with explanations of what each file is intended to implement:

1. Source Files (.sv):
    a. rtl/computer.sv
    - Top-level module that instantiates the CPU, Memory, and I/O modules.
    - Connects the modules using buses and wires.
    b. rtl/cpu.sv
    - Instantiates ALU, Control Unit, and Register File.
    - Handles instruction decoding and execution according to the defined instruction set.
    c. rtl/alu.sv
    - Implements arithmetic and logical operations.
    - Sets flags based on the results of operations.
    d. rtl/cpu_control.sv
    - Generates control signals for different stages of instruction execution.
    - Manages the overall operation of the CPU.
    e. rtl/cpu_registers.sv
    - Defines and manages the registers within the CPU.
    - Handles read and write operations to the registers.
    f. rtl/ram.sv
    - Implements the RAM memory with 256 bytes of storage.
    - Handles read and write operations to the memory.
    g. rtl/io.sv
    - Implements I/O ports and their operations.
    - Handles IN and OUT instructions for interaction with external devices.
    h. rtl/machine.sv
    - Encapsulates the entire computer system.
    - Can include additional features and interfaces, such as debugging and reset logic.
    i. library/clock.sv, library/counter.sv, library/register.sv, library/tristate_buffer.sv
    - Utility modules implementing basic digital logic components like clocks, counters, registers, and tristate buffers.
2. Header Files (.svh):
    a. rtl/parameters.svh
    - Defines constants and parameters used across different modules.
    - Includes opcode values, memory size, register width, etc.
3. Testbench Files (.sv):
    a. tb/alu_tb.sv, tb/cpu_tb.sv, tb/machine_tb.sv, tb/register_tb.sv
    - Testbenches for simulating and verifying the functionality of ALU, CPU, the entire computer system, and register file respectively.
    - Includes test cases and simulation scenarios.
4. Assembly Tests and Tools:
    a. tests/
    - Directory containing assembly tests for different components and instructions.
    b. asm/asm.py
    - Python script that serves as an assembler to convert assembly code to machine code.
    5. Miscellaneous Files:
    a. Makefile
    - Contains build and run commands for the project.
    b. README.md
    - Documentation providing detailed information about the project, its architecture, usage, and development status.
    c. gtkwave/
    - Directory containing GTKWave configuration files for waveform viewing and debugging.

This structured file organization ensures a clean and maintainable codebase, with clear separation of different components and functionalities, making it easier to develop, test, and debug the 8-bit computer system in SystemVerilog.

