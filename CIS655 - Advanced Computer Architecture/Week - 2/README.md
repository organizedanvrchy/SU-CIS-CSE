# Processor Design
## Fundamentals 
### 1. Computation
- Role in Processor Design: <br>
  - Responsible for executing instructions and performing arithmetic and logic operations. <br>

- Components: <br>
  - __Arithmetic Logic Unit (ALU)__: Performs arithmetic and logic operations.
  - __Control Unit (CU)__: Decodes instructions and manages data flow.
  - __Floating Point Unit (FPU)__: Handles computations involving real numbers.
  - __Pipeline Stages__: Improves instruction throughput via instruction-level parallelism. <br>
  
- Optimization Goals: <br>
  - Maximize execution speed (e.g., superscalar execution, out-of-order execution).
  - Enhance energy efficiency (e.g., dynamic voltage scaling). <br>
  
### 2. Communication
- Role in Processor Design: <br>
  - Ensures data and control signals flow seamlessly between internal components (e.g., ALU, CU, caches) and external entities (e.g., memory, I/O). <br>

- Components: <br>
  - __Buses__: Internal and external buses for transferring instructions, data, and addresses (e.g., system bus, memory bus).
  - __Interconnects__: On-chip networks (NoC) for multicore processors.
  - __I/O Interfaces__: Handle communication with peripherals. <br>
  
- Optimization Goals: <br>
  - Reduce latency in data transfer.
  - Increase bandwidth to support high-throughput applications. <br>
  
### 3. Storage
  - Role in Processor Design: <br>
    - Provides the means to store and retrieve data and instructions required for computation. <br>
  
  - Components: <br>
    - __Registers__: Small, fast storage within the CPU for immediate data access.
    - __Caches__: Multi-level (L1, L2, L3) storage to minimize latency in accessing frequently used data.
    - __Main Memory__: RAM as the primary storage for executing programs.
    - __Secondary Storage__: Non-volatile storage for long-term data persistence. <br>
    
  - Optimization Goals: <br>
    - Hierarchical memory design for speed and efficiency.
    - Techniques like prefetching and cache coherency for faster access. <br>

## Interplay Between the Building Blocks
- Computation depends on Storage for fetching instructions and data.
- Communication is critical for transferring data between Storage and Computation components.
- Efficient processor design ensures a balanced and optimized interaction among these blocks, leading to higher performance and energy efficiency.
