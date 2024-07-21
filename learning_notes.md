# Learning Documentation: Computer Architecture, July 10th
**Nana Yaw Acheampong**

## CPU Visual Simulator
**Link Title**: [CPU Visual Simulator](https://learn.ontariotechu.ca/courses/27711/modules/items/640483)

### Summary of Content:
- The first step in the CPU simulation is the transfer of data from the "Program Counter" (PC) through the "Address Bus", where it is then loaded into an address in the RAM.  
- The PC is a register used to store memory addresses and holds the next set of instructions to be executed by the CPU.  
- The PC increments (by 2 in our case) each time a new set of instructions is received.  
- From the Control Unit/Decoder, a fetch signal is sent to RAM through the "Control Bus". In the simulation, the Control Bus activates a specific address in RAM, proceeding sequentially for each new instruction. The data    is then sent from RAM out via the "Data Bus".  
- The "Instruction Register" (IR) is where the data lands next. The IR holds instructions currently being executed by the CPU. The contents of the data are decoded to specify the "Opcode", which directs other CPU     
  components on how to execute the instructions.  
- This cycle ends with the PC incrementing and the entire process resetting.

### Key Takeaways:
- The simulation starts with the Program Counter, which tracks the cycles of the program and waits for a new set of instructions once the current cycle completes.
- The Program Counter's content is placed on the Address Bus to access RAM.
- The Control Bus signals a fetch operation to access the RAM address based on the PC counter.
- Fetched instructions from RAM are loaded into the Instruction Register via the Data Bus.
- The IR decodes the Opcode to determine the operation that needs to be performed.

### Personal Reflections:
- The CPU simulation is reminiscent of "Scott’s CPU" as both illustrate the flow of data during the execution process.
- Both involve registers for storing data and buses that dictate where data should travel next.
- In my view, the CPU process can be likened to the function of a traffic light at an intersection, where wires and buses act like traffic lights controlling the flow of data (cars) along highways and roads.
- Creating a list of definitions proves helpful when aiming to comprehend the process at a deeper level.

![CPU Visual Simulator](https://github.com/twilightalc/Learning-Documentation/assets/164780825/edcc7008-57e1-459e-878d-0ada89af51bd)

## Compiler Explorer
**Link Title**: [Compiler Explorer](https://godbolt.org/)

### Summary of Content:
Compiler Explorer allows users to observe the inner workings of their favorite programming languages. Most high-level programming languages enable us to write instructions that are easier for humans to understand. These languages use a compiler to translate code into Assembly Language (1s and 0s), enabling computers to comprehend the instructions given. Compiler Explorer showcases how different compilers handle the same code, providing insight that can empower programmers to optimize their code, especially in C and C++.

### Key Takeaways:
- Input code from your preferred programming language into the panel on the right to view the corresponding Assembly code.
- Multiple compiler versions are available for comparison, showing how specific changes affect the generated Assembly code.
- Compilers can be optimized to reduce the amount of generated Assembly code. In the video, the user applies "O2" as an optimization to enhance performance and reduce overall code size.
- Compilers act as bridges between hardware, software, users, and the deepest levels of computing.

### Personal Reflections:
- It was intriguing to see how many lines of Assembly code were necessary to execute a simple `print("Hello World")` in Python. This vividly illustrates the disparity between high-level and low-level languages. Most of the Assembly code is challenging to decipher compared to Python.
- Different compilers produce distinct sets of Assembly instructions from the same Python code. This demonstrates that even different compiler versions employ separate algorithms to convert the same instructions.

![Compiler Explorer](https://github.com/twilightalc/Learning-Documentation/assets/164780825/cf275b19-b856-4809-a6e9-b4517c72c96c)

## emulsiV

# Components of the CPU

1. **Program Counter (PC)**: 
   - This register holds the address of the current instruction being executed.
   - It increments by 4 (since each instruction is 4 bytes) to point to the next instruction.
     ![image](https://github.com/user-attachments/assets/4fafbbdf-7dd3-44d9-ab63-aa26ef3f98ae)


2. **Registers**: 
   - Virgule has 32 general-purpose registers (x0 to x31) and special registers like the program counter (PC) and the machine exception program counter (MEPC).
     ![image](https://github.com/user-attachments/assets/eca06aaf-aac0-4273-ade3-a39d705e082e)


3. **Memory Organization**: 
   - The memory is divided into different sections, with specific addresses for RAM, input/output devices, and bitmap display.
     ![image](https://github.com/user-attachments/assets/661269c5-657b-415c-aad8-f4d49f6b7ae0)


4. **Instruction Set**: 
   - Virgule supports a subset of RISC-V instructions, including computational, control transfer, and memory access instructions.

5. **Interrupts**: 
   - Virgule handles interrupts by setting the program counter to a predefined address (typically address 4) and saving the return address in the MEPC register.

- Just like the previous simulation, the set of data starts from the Program Counter. The information travels along the addr bus where it seems to interact with the memory. The 4 address slots light up at once; my guess is that the data is stored with the same address in the memory until it is no longer needed.
- After the interaction with memory, the data is sent along the Data Bus where it reaches the Instruction Register. From what I know about the register, they store data that the CPU can access even faster than the RAM.
