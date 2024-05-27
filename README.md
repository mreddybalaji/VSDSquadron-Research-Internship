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




</details>
