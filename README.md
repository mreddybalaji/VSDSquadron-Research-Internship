# VSDSquadron-Research-Internship-Program

Explore VSDSquadron's internship repository for VLSI embedded systems using VSDSquadron Mini. Access tutorials, templates, tools, and projects for a comprehensive understanding.

<details>
<summary><b> TASK 1: RISC-V TOOL CHAIN </b></summary>

Install RISC-V [GNU ToolChain](https://github.com/riscv-collab/riscv-gnu-toolchain)
  
Compiling the C Program:
  
The sum of Numbers from 1 to n
  
Step 1: cd
  
step 2: gedit sum_1ton.c (save file name as .c)

step 3: Compilling -> gcc sum_1ton.c

step 4: Running    -> ./a.out sum_1ton.c

 
At final Output is printed.


![1](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/1d3e5a6a-75e6-41a9-9653-8475db57a33d)

```  
#include <stdio.h>
int main() 
{
    int i, n = 5, sum = 0;

    for (i = 0; i <= n; ++i)
    {
        sum += i;
    }

    printf("Sum of %d numbers is %d\n", n, sum);

    return 0;
}
```

Use the following commands for compiling in the RISC V Compiler: 

Step 1:

```
riscv64-unknown-elf-gcc -O1 -mabi=lp64 march=rv64i -o sum_1ton.o sum_1ton.c

```

![2](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/c3a5fdc9-1925-43b5-b5bf-d9ea8838d700)


*Use the following commands to open the assembly-level instruction:*

step 2: Go to a new tab

![3](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/ebb66b69-39fd-47a0-8b12-9d7b606cf8f5)


```
riscv64-unknown-elf-objdump -d sum_1ton.c
```
Step  3: To make it less 

![5](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/1fa9f509-cde9-4647-9951-4e4d6d568e54)





```
riscv64-unknown-elf-objdump -d sum_1ton.c | less
```


Search for the main 
use--> /main and press n 


![6](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/47209f29-f4ca-40db-a83c-6391d62bbb0f)


![Screenshot from 2024-05-27 21-55-52](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/43f038b2-713b-4d9c-a5cf-9fc0436fd89a)






now replace O1 to Ofast



![Screenshot from 2024-05-27 21-58-17](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/3bc7eea1-cc24-43b3-8dc3-afcc838c50e1)


To find the number of instruction 

start address of present sequence - start address of next sequence
</details>



<details>


<summary><b> TASK 2: RISC-V INSTRUCTION SET   </b></summary>


### RISC-V 
RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles. It is designed to be royalty-free and open-source, allowing anyone to use and contribute to the architecture without any licensing fees or restrictions.

### INSTRUCTIONS FORMAT IN RISC-V  
Sure, I'd be happy to provide an overview of the topics you've listed related to RISC-V instruction formats and architecture.

1. **General-Purpose Register and PC**:
   - RISC-V has 32 general-purpose 64-bit registers, named `x0` to `x31`.
   - `x0` is a hardwired zero register, which cannot be written to.
   - `x1` is the return address register (also known as the link register).
   - `x2` is the stack pointer register.
   - The program counter (PC) register holds the address of the currently executing instruction.
  
     <img width="191" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/fb785ecf-41fb-4f74-a919-fe200be844d9">

2. **RISC-V Base Instruction Formats**:
   RISC-V defines six base instruction formats:
   - I-type
   - U-type
   - R-type
   - J-type
   - B-type
   - S-type (a subclass of I-type)
  
     <img width="391" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/100192df-1b18-46c9-9341-6060be05cc2b">


3. **I-type Instruction Format**:
   - I-type instructions include load, immediate, and shift instructions.
   - The format is `opcode rd, rs1, immediate`.
   - The immediate value is a 12-bit signed integer.
  
     <img width="382" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/25508962-128c-4814-9421-d947d898b829">


4. **U-type Instruction Format**:
   - U-type instructions include upper-immediate instructions.
   - The format is `opcode rd, immediate`.
   - The immediate value is a 20-bit unsigned integer.
  
     <img width="404" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/4e5a9552-4cfb-4afd-9a1b-9fe7914c84db">


5. **R-type Instruction Format**:
   - R-type instructions include arithmetic, logical, and control-transfer instructions.
   - The format is `opcode rd, rs1, rs2`.
  
     <img width="385" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/23df9b34-dcdd-44ab-b286-15dc9e15494a">


6. **J-type Instruction Format**:
   - J-type instructions include jump instructions.
   - The format is `opcode rd, immediate`.
   - The immediate value is a 20-bit signed integer.
  
     <img width="403" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/a27204d2-350b-4c7c-ab68-74bac28de6c5">


7. **B-type Instruction Format**:
   - B-type instructions include conditional branch instructions.
   - The format is `opcode rs1, rs2, immediate`.
   - The immediate value is a 12-bit signed integer.
  
     <img width="407" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/97976c44-5941-4cd2-b063-f6fc30f2ccdb">


8. **Load and Store Instructions**:
   - Load instructions (`load`, `lw`, `ld`) transfer data from memory to registers.
   - Store instructions (`store`, `sw`, `sd`) transfer data from registers to memory.
   - These instructions use the I-type format.

     <img width="407" alt="image" src="https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/51fb76d3-0c04-4505-bec9-8d740ac27c00">

9. **Address Alignment**:
   - RISC-V requires aligned memory accesses for load and store instructions.
   - For 32-bit and 64-bit loads and stores, the address must be aligned to a 4-byte and 8-byte boundary, respectively.
   - Unaligned memory accesses can be emulated in software if necessary.
  
     

10. **Handle Overflow Situations**:
    - RISC-V does not have dedicated overflow detection instructions.
    - Overflow can be detected by checking the carry or sign bits of the result.
    - Specific instructions like `addiw` and `subw` can be used to perform 32-bit signed integer arithmetic with overflow detection.
    - Software can also implement overflow checking through conditional branches.




1. Command: `ADD r6, r2, r1`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00001 00010 000 00110 0110011`

2. Command: `SUB r7, r1, r2`
   - Instruction Type: R-type
   - Instruction Format: `0100000 00010 00001 000 00111 0110011`

3. Command: `AND r8, r1, r3`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00011 00001 111 01000 0110011`

4. Command: `OR r9, r2, r5`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00101 00010 110 01001 0110011`

5. Command: `XOR r10, r1, r4`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00100 00001 100 01010 0110011`

6. Command: `SLT r11, r2, r4`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00100 00010 010 01011 0110011`

7. Command: `ADDI r12, r4, 5`
   - Instruction Type: I-type
   - Instruction Format: `000000000101 00100 000 01100 0010011`

8. Command: `SW r3, r1, 2`
   - Instruction Type: S-type
   - Instruction Format: `0000000 00001 00011 010 00010 0100011`

9. Command: `SRL r16, r14, r2`
   - Instruction Type: R-type
   - Instruction Format: `0000000 00010 01110 101 10000 0110011`

10. Command: `BNE r0, r1, 20`
    - Instruction Type: B-type
    - Instruction Format: `0000000 00001 00000 001 10100 1100011`

11. Command: `BEQ r0, r0, 15`
    - Instruction Type: B-type
    - Instruction Format: `0000000 00000 00000 000 01111 1100011`

12. Command: `LW r13, r1, 2`
    - Instruction Type: I-type
    - Instruction Format: `000000000010 00001 010 01101 0000011`

13. Command: `SLL r15, r1, r2`
    - Instruction Type: R-type
    - Instruction Format: `0000000 00010 00001 001 01111 0110011`








</details>



<details>
<summary><b> TASK 3: RISC-V Verilog Functional Simulation </b></summary>










