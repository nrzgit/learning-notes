# It is introduction to computer architecture
## CPU:
***Central Processing Unit***-brain of a computer.  
CPU is usually placed in a special slot called a **socket** on the computers **motherboard**.  
`Motherboard-is the main circuit board that connects all the parts of a computer.`  
The CPU tasks:
+ Doing math calculations
+ Running apps or games
+ Helping the keyboard, mouse, and screen work together
+ Storing and retrieving information during tasks
  
`Without a CPU, a computer wouldn’t know what to do.`

### Main components of CPU:

![CPU Picture](https://github.com/nrzgit/learning-notes/blob/beabcdcb51107bebda5be27981fdab19f0ca11d2/computer-basics/CPU-Components-.webp)

`The components of a CPU include the ALU (Arithmetic Logic Unit), CU (Control Unit), registers, cache, and clock.`

+ ***ALU***-arithmatic & logic unit. It do arithmatic tasks (like multiplication, division, addition, substraction) and logical tasks(like And, Or, Comparisons)

+ ***Control Unit***-the control unit manages the CPU by sending signals like clock, hold, and reset to its parts. It ensures all components work together to complete tasks. For example, it synchronizes data movement from cache memory to the ALU.

+ ***Memory Unit***-the memory unit stores data and instructions. Older CPUs used registers, but modern ones also have fast cache memory. The CPU fetches data from RAM, ROM, or hard disks and stores it in registers or cache during tasks.

### Functions of the CPU:

![Functions of the CPU](https://github.com/nrzgit/learning-notes/blob/72fec142c0cb988c944ba757d5595ffff2a08626/computer-basics/functions_of_cpu.webp)

***Fetch-Decode-Execute-Store***

+ **Fetch:**-the first CPU gets the instruction. That means binary numbers that are passed from RAM to CPU.  
+ **Decode**-when the instruction is entered into the CPU, it needs to decode the instructions. with the help of ALU(Arithmetic Logic Unit), the process of decoding begins.  
+ **Execute**-after the decode step the instructions are ready to execute(do)  
+ **Store**-after the execute step the instructions are ready to story in the memory

### Types of CPUs:

+ **Single-Core CPU:** the oldest type. It can only handle one task at a time. Very slow for modern apps, games
+ **Dual-Core CPU:** two tasks at once, it is faster and better for multitasking, like listening to music while doing homework.
+ **Quad-Core CPU:** four cores, heavy tasks like video editing or playing modern games.

### How does the CPU make computer faster?:

+ **Multiple Cores:**-many CPUs have multiple cores, which are like mini-CPUs that can work on different tasks at the same time. It’s like having several chefs in the kitchen instead of one.
+ **Faster Clocks:**-the clock speed (measured in GHz, like 3.5 GHz) determines how many instructions the CPU can handle per second.
+ **Bigger Cache:***-more cache means the CPU can store more data close by, reducing wait times.
+ **Pipelining:**-this lets the CPU start working on the next instruction before finishing the current one, like a factory line.

 Advantage                     | Disadvantage                                                                 |
|-------------------------------|------------------------------------------------------------------------------|
| Versatile: Can handle all kinds of tasks, from math to running complex games. | Heat: CPUs get hot when working hard, so computers need fans or cooling systems to stay safe. |
| Fast: Modern CPUs process billions of instructions per second.         | Power Use: Powerful CPUs use a lot of electricity, which can raise power bills.               |
| Multi-tasking: Multi-core CPUs let you run many programs at once.      | Cost: High-performance CPUs, like Intel Core i9, can be expensive.                            |
| Compatible: Work with tons of software, so you can use the same CPU for different apps. | Not Perfect for All Tasks: For graphics or video editing, specialized chips like GPUs are better than CPUs. |
