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

### Steps for RISCV Functional Simulations:

Install `iverilog` and `GTKWave`:

```
sudo apt install iverilog
```

```
sudo apt install gtkwave
```



step 1: create a new dir in a folder as 


```
mkdir mrb
```

step 2: create files the Verilog files code and testbench using touch

file named as rv32i.v and rv32i_tb.v

Step 3: To run and simulate the Verilog code


```
iverilog -o rv32i rv32i.v rv32i_tb.v
```
```
./rv32i
```

Step 4:To simulate in GTKWave

```
gtkwave rv32i.vcd
```

### OUTPUT:
Here's the given information in a table format:

| Operation | Standard RISCV ISA            | Hardcoded ISA |
|-----------|-------------------------------|---------------|
| ADD       | R6, R2, R1                    | 32'h00110333  |
|           |                               | 32'h02208300  |
| SUB       | R7, R1, R2                    | 32'h402083b3  |
|           |                               | 32'h02209380  |
| AND       | R8, R1, R3                    | 32'h0030f433  |
|           |                               | 32'h0230a400  |
| OR        | R9, R2, R5                    | 32'h005164b3  |
|           |                               | 32'h02513480  |
| XOR       | R10, R1, R4                   | 32'h0040c533  |
|           |                               | 32'h0240c500  |
| SLT       | R1, R2, R4                    | 32'h0045a0b3  |
|           |                               | 32'h02415580  |
| ADDI      | R12, R4, 5                    | 32'h004120b3  |
|           |                               | 32'h00520600  |
| BEQ       | R0, R0, 15                    | 32'h00000f63  |
|           |                               | 32'h00f00002  |
| SW        | R3, R1, 2                     | 32'h0030a123  |
|           |                               | 32'h00209181  |
| LW        | R13, R1, 2                    | 32'h0020a683  |
|           |                               | 32'h00208681  |
| SRL       | R16, R14, R2                  | 32'h0030a123  |
|           |                               | 32'h00271803  |
| SLL       | R15, R1, R2                   | 32'h002097b3  |
|           |                               | 32'h00208783  |

Each operation with its corresponding standard RISCV ISA format and hardcoded ISA format.

### 1. ADD: `ADD R6, R2 ,R1`

Output is 1+2 = 3 

32- bit instruction for `ADD R6, R2 ,R1` is 0220833

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/91562f39-cba5-4140-8f4d-5f450a6fdc9e)

For Example:
### Breakdown and how it maps to the 32-bit instruction format in RISCV:

The instruction `ADD R6, R2, R1` is encoded in the RISCV ISA as `0x0220833`. 

In the RISCV ISA, the `ADD` instruction format is as follows:
```
funct7 | rs2 | rs1 | funct3 | rd | opcode
```
Each field is described as:
- `funct7`: 7 bits
- `rs2`: 5 bits
- `rs1`: 5 bits
- `funct3`: 3 bits
- `rd`: 5 bits
- `opcode`: 7 bits

For `ADD R6, R2, R1`, we need to fill in these fields:
- `funct7` = `0000000` (for `ADD`)
- `rs2` = `R1` (register 1 in binary: `00001`)
- `rs1` = `R2` (register 2 in binary: `00010`)
- `funct3` = `000` (for `ADD`)
- `rd` = `R6` (register 6 in binary: `00110`)
- `opcode` = `0110011` (for R-type instructions)

Putting these together:
```
funct7 | rs2  | rs1  | funct3 | rd   | opcode
0000000 | 00001 | 00010 | 000   | 00110 | 0110011
```
In binary: `0000000 00001 00010 000 00110 0110011`

Converting each field to hexadecimal:
- `funct7` = `0000000` = `0x00`
- `rs2` = `00001` = `0x01`
- `rs1` = `00010` = `0x02`
- `funct3` = `000` = `0x0`
- `rd` = `00110` = `0x06`
- `opcode` = `0110011` = `0x33`

Combining these into a single 32-bit instruction:
```
0000000 00001 00010 000 00110 0110011
```

In hexadecimal, this is: `0x00208333`

Given in the hardcoded format:
```
Opcode: 0x33
funct3: 0x0
funct7: 0x0
rd: 0x6
rs1: 0x2
rs2: 0x1
```

So, the 32-bit instruction for `ADD R6, R2, R1` in RISCV ISA is `0x00208333`. 

### 2. SUB: SUB R7, R1 ,R2

Output is 1-2 = -1 or 0XFFFFFFFF 

32- bit instruction for `SUB R7, R1 ,R2` is 0220833

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/615c8461-b6fd-4455-ac3e-4a9f30ccc9c1)



### 3. AND: AND R8, R1, R3

Output is 3 & 1 = 1 or 0X00000001

32 - bit instruction for `AND R8, R1, R3` is 0230A400.
![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/3b422dc3-a10c-4f58-a24a-f5c2bc571e48)





### 4.OR: OR R9, R2, R5

Output is 2|5 = 7 

32- bit instruction for `OR R9, R2, R5 ` is 02513480
![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/a7113048-dc18-4a68-857e-8bf61890b362)



### 5. XOR: XOR R10, R1, R4

Output is 1 (0001) ^ 4 (0100) = 5 (0101) 

32 - bit instruction for `XOR R10, R1, R4` is 0240C500.

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/71726760-eca6-4c49-8343-8ae0ddc70e18)



### 6. SLT: SLT R1, R2, R4

Output is = comparing the value 2 with 4 , so 2 < 4 = 1 

32- bit instruction for `SLT R1, R2, R4` is 02415580.

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/af766f1d-5ae6-4072-b2c8-574c8c16f5a6)




### 7. ADDI: ADDI R12, R4, 5

Output is value 4 is stored in register with an value, 4+5=9

32- bit instruction for `ADDI R12, R4, 5` is 00520600.

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/8bfd163f-5c0e-43d2-a0b3-d06fb04a0fa7)




### 8. BEQ: BEQ R0, R0, 15

Output is BEQ checks the values stored in both registers, both the reg. are equal, and it increments the PC by 15. So, 10 + 15= 25 or 0x00000019.

32- bit instruction for `BEQ R0, R0, 15` is 00F0002.

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/a66ab341-a439-4c55-afb5-780e272c1989)




### 9. BNE: BNE R0, R1, 20

Output BNE checks the values stored in both registers, both the reg. not equal, and it increments the PC by 20. So, 26 + 20 =46 or 0X0000001A.

32 - bit instruction for `BNE R0, R1, 20` is 00210700.

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/b781dcfd-8ba4-4644-93a1-2d9c8ebf82a0)





### 10. SLL: SLL R15, R1, R2

Output (0001) << 2 = 0100 or 4.

32 - bit instruction for `SLL R15, R1, R2` is 00210700

![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/94b8f63d-2160-4bf2-9350-a86a953aa1b6)



</details>



<details>
<summary><b> TASK 4: PROJECT </b></summary>

## AUTOMATED SMS CALLS USING VSDSQUADRON MINI and SIM800L MODULE




![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/3893de24-400e-4c67-9bc7-ae26d541c592)



### VSDSQUADRON MINI and SIM800L Pin Connections

#### VSDSQUADRON MINI Pin Description:
1. **5V**: Power supply pin that provides 5V to the connected module.
2. **GND**: Ground pin for common ground reference.
3. **PA10**: General-purpose I/O pin, used as the TX (Transmit) pin for UART communication.
4. **PA9**: General-purpose I/O pin, used as the RX (Receive) pin for UART communication.

#### SIM800L Pin Description:
1. **VCC**: Power input pin for the SIM800L module, typically requires 3.7-4.2V but is connected to the 5V pin of VSDSQUADRON MINI in this case.
2. **GND**: Ground pin, connected to the common ground.
3. **TXD**: Transmit pin for UART communication, connected to PA10 of the VSDSQUADRON MINI.
4. **RXD**: Receive pin for UART communication, connected to PA9 of the VSDSQUADRON MINI.

### Code Implementation:

The provided code initializes the VSDSQUADRON MINI microcontroller and communicates with the SIM800L GSM module to send an SMS.

1. **Includes and Defines**:
   - `#include <ch32v00x.h>`: Includes the header file for the VSDSQUADRON MINI microcontroller.
   - `#include <debug.h>`: Includes the debug header for debugging purposes.
   - `#define SIM800L_UART USART1`: Defines the UART port used for communication with the SIM800L.
   - `#define SIM800L_BAUDRATE 9600`: Defines the baud rate for UART communication.

2. **Delay Functions**:
   - `void Delay_Init(void)`: Initializes delay functions (implementation needed if required).
   - `void Delay_Ms(uint32_t n)`: Delays for `n` milliseconds by executing a loop.

3. **USART Initialization and Communication Functions**:
   - `void USART_Printf_Init(uint32_t baudrate)`: Initializes the USART peripheral with the specified baud rate.
   - `void USART_SendString(USART_TypeDef* USARTx, char* str)`: Sends a string over the specified USART.

4. **Setup Function**:
   - Initializes the system clock and delay functions.
   - Configures the USART for communication with the SIM800L.
   - Sends AT commands to the SIM800L to send an SMS to the specified phone number.

5. **Main Function**:
   - Calls the `setup()` function and enters an infinite loop.

### Connections Summary:

```plaintext
+-----------------+      +----------+
| VSDSQUADRON MINI|      | SIM800L  |
|                 |      |          |
|              5V |------| VCC      |
|             GND |------| GND      |
|             PA10|------| TXD      |
|             PA9 |------| RXD      |
+-----------------+      +----------+
```

### Usage:

- Connect the pins of the VSDSQUADRON MINI to the SIM800L as described.
- Enter the phone number to which the SMS or call.
- Compile and upload the code to the VSDSQUADRON MINI microcontroller.




























