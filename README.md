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


*Use the following commands to open the Assembly level instruction:*

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
The instructions format of a processor is how machine language instructions are structured and organized for a processor to execute. It is made up of a series of 0s and 1s, each containing information about the location and operation of data.  
There are 6 instruction formats in RISC-V:  
1. R-format  
2. I-format  
3. S-format  
4. B-format  
5. U-format  
6. J-format  

ADD r6, r2, r1:

Instruction Type: R-type

Instruction Format: 0000000 00001 00010 000 00110 0110011

SUB r7, r1, r2:
Instruction Type: R-type
Instruction Format: 0100000 00010 00001 000 00111 0110011

AND r8, r1, r3:
Instruction Type: R-type
Instruction Format: 0000000 00011 00001 111 01000 0110011

OR r9, r2, r5:
Instruction Type: R-type
Instruction Format: 0000000 00101 00010 110 01001 0110011

XOR r10, r1, r4:
Instruction Type: R-type
Instruction Format: 0000000 00100 00001 100 01010 0110011


SLT r11, r2, r4:
Instruction Type: R-type
Instruction Format: 0000000 00100 00010 010 01011 0110011


ADDI r12, r4, 5:
Instruction Type: I-type
Instruction Format: 000000000101 00100 000 01100 0010011


SW r3, r1, 2:
Instruction Type: S-type
Instruction Format: 0000000 00001 00011 010 00010 0100011


SRL r16, r14, r2:
Instruction Type: R-type
Instruction Format: 0000000 00010 01110 101 10000 0110011


BNE r0, r1, 20:
Instruction Type: B-type
Instruction Format: 0000000 00001 00000 001 10100 1100011


BEQ r0, r0, 15:
Instruction Type: B-type
Instruction Format: 0000000 00000 00000 000 01111 1100011


LW r13, r1, 2:
Instruction Type: I-type
Instruction Format: 000000000010 00001 010 01101 0000011


SLL r15, r1, r2:
Instruction Type: R-type
Instruction Format: 0000000 00010 00001 001 01111 0110011









</details>
