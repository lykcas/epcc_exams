# 2018

## -

1. 处理硬件性能的四个影响因素（4）
2. 简述Tensor Cores（4）
3. IC和ASIC的区别（2）
4. ASIC和FPGA的区别（2）
5. FPGA的编程步骤（6）
6. GPU和FPGA的结构区别。尤其是1.如何做到high performance？2.challenges（7）

## cache

1. 解释cache coherency, cache block和cache miss（6）
2. 看题写cache状态（11）
3. coherency miss计算（8）

## network

## -

1. performance相关概念（10）
2. strong scaling和weak scaling的优缺点（4）
3. 达不到ideal performance的原因（5）
4. Shared memory systems的优缺点（6）

# 2017

## cache

1. cache相关的定义（8）
2. cache的hit ratio计算（10）
3. cache miss计算（7）

## hardware

给定三种hardware

1. 简述相同与不同（9）
2. motivation, history相关问题（7）
3. compilers（9）

## processors

给定四种processors

1. 概念，简述如何使用（8）
2. 如何组建一个HPC system（10）
3. 开放题（7）

## network

# 2016

## cache

1. 概念（6）
2. cache miss计算（14）
3. cache miss计算（5）

## Memory

1. MIMD概念（2）
2. 三种HPC system优缺点（6）
3. 简述accelerator（3）
4. 说出HPC system的三个组件（2）
5. 简述batch system（6）
6. 简述OS（6）

## processors

1. 简述superscalar和VLIW，他们俩的区别，优缺点（15）
2. 看题说upper bound on the floating point performance（10）

## GPU

1. GPU在HPC中的优缺点（4）
2. 两种不同GPU的对比（6）
3. processor计算（6）
4. high band width的优点(4)
5. 开放题（5）

# 2015

## GPU

1. 为什么GPU比CPU更快（11）
2. accelerated cluster的组成？需要什么硬件组件？他们如何布置在standard clusters中？（7）
3. NVIDIA GPU 和 Xeon Phi芯片和其他同类产品的不同（看录播，老师有没有着重讲这里）（7）

## Parallel Architectures

1. 什么是cache memory？为什么processors需要cache？（4）
2. 说出两个现代处理器的指令集并行特征（instruction level parallelism ILP）（2）
3. shared memory systems的一般特征，SMP和ccNUMA的区别（6）
    Each processor has access to global memory.
    Communication via read/write to memory.
    Simple to program, no explicit communication.
    Scaling is difficult because of memory access bottleneck.
    Usually modest number of processors.
    SMP: each processor has equal access to all parts of memory. Same latency and bandwidth.
    cc-NUMA: Each processor has has some fast local memory. Direct access lower remote memory via global address space. Hardware includes support circuitry to deal with remote accesses, allowing fast communication. Allowing scaling to 100's CPUs.
4. distributed memory architecture的主要特征，他们如何组成一个shared memory cluster（6）
    Each processor has its own local memory.
    Processors are connected by some interconnection mechanism.
    Communication via explicit message passing.
    Highly scalable architecture.
    Distributed memory between nodes, shared memory within a node.
5. *并行架构和并行化策略（处理大数据集）*？（7）

## network

1. degree, diameter, direction width概念+解释他们与network的performance和cost之间的关系（12）
2. 算上面那三个的值（3）
3. balance（3）
4. diameter和minimum bisection width的通用公式（3）

## cache

1. cache miss, set associativity, prefetching的概念（6）
2. cache的计算（14 ）
3. 关于block size的讨论（5）

# 2014

## -

1. Flynn分类法下四个HPC系统类别都是什么（4）
    Classification of architectures by instrustion stream and data stream.
    SISD: Sinngle instruction Single data *(serial machines)*
    MISD: Multiple instructions Single data
    SIMD: Single instruction Multiple data
    MIMD: Multiple instructions Multiple data
2. 列举现代processors里的parallelism部分/部件，简述他们是如何做到并行的（8）
3. GPU浮点数运算的计算（5）
4. 简述为什么电脑无法达到理论运算峰值的原因（8）

## cache coherency

1. cache coherency和false sharing的概念（6）
2. shared memory system状态计算（12）
3. 计算the cost of a coherency miss in clock cycles（7）

## processor

1. RISC和CISC的概念、区别（3）
    RISC: Reduced instruction set computer.
    CISC: Complex instruction set computer.
    Difference:
    RISC: Low-level, fast-to-execute instructions grouped by functional unit. Minimise the number of clock cycle per instruction. Arithmetic on registers only.
    CISC: More complex instructions. Minimise the number of instructions in program. Arithmetic on registers and memory locations. Easier to compiler for.
2. 现代processors里的五个主要功能单位（main functional units）（10）
    Instruction Unit:
    Responsible for fetching, decoding, dispatching instructions.
    Integer Unit:
    For integer arithmetic.
    Floating Point Unit:
    For floating point arithmetic.
    Control Unit:
    Responsible for branches and jumps.
    Load/Store Unit:
    Responsible for loading data from memory and storing it back.
3. 通过汇编写C代码（8）
4. 上述代码引起poor performance的原因（4）

## -

1. Amdahl's law概念（2）
    The performance improvement to be gained by the parallelisation is limited by the proportion of the code which is serial.
2. shared memory clusters里的两种parallel computing architectures（8）
    Shared memory:
    Each processor has access to global memory store.
    Communication via read/write to memoory.
    Simple to program, no explicit communication.
    Scaling is difficult because of memory access bottleneck.
    Modest number of processors.
    Probs: Simple to use and maintain. cc-NUMA allows scaling 100's CPUs.
    Cons: Potential problems with simultaneous access to memory. Sophisticated hardware to maintain cache coherency. Scalability limited by this.
    Distributed memory:
    Each processor has its own local memory.
    Processors are connected by some interconnection mechanism.
    Interconnection need explicit message passing.
    Highly scalable architecture.
    Probs: Can grow to any size. Adding processors increases bandwidth.
    Cons: Rely on good interconnection. Jobs are placed by users and remained on same processor. High system management overhead.
3. SMP和cc-NUMA式区别，可画图（5）
    SMP：
    Symmetric Multi-Processiing. 
    Each processor has equal access to all parts of global memory.
    Same latency and bandwidth.
    cc-NUMA:
    Each processor has some fast local memory.
    Direct access to slower remote memory via global address space.
    Hardware includes support circuitry to deal with remote access, allowing fast communication.
4. network相关概念（4）
5. network计算（6）

# 2013

## -

1. Moore's law概念（2）
    CPU power doubles every 18 months.
2. parallel systems里的四个主要组成部分（main building blocks）（8）
    Processors: To calculate. Accelerators.
    Memory: For temporary storage of data.
    Interconnect: So processors can talk to each other and the outside world.
    Storage: Disks for storing input/output data and tapes for long term archiving of data.
3. strong scaling和weak scaling的概念，他们与hpc的关系（8）
    strong scaling: 
    increasing p, constant n. 
    Problem size stays as the number of processors increasing, decreasing the work per processor.
    weak scaling:
    increasing p, increasing n.
    Problem size increasing as the same rate as the number of processors increasing, keeping the work per processor the same.
4. The metrics theoretical 和 measured peak ﬂoating-point performance的讨论（7）

## network

## processor

1. superscalar, SIMD instruction, conventional multithreading概念（4）
2. 计算theoretical peak double-precision ﬂoating point rate（12）
3. 三个为什么无法达到双精度浮点数理论峰值（2）的原因（9）

## GPU

1. 简述NVIDIA的GPU架构（相较于CPU，为什么GPU能做到高性能计算）（11）
2. Xeon Phi和Tesla GPUs的相同点与不同点（6）
3. 从体系架构上描述大型超算机如何couple多个accelerators，作图（8）







Week 1 (Week commencing: 16 Sept) 

​	**Mon, 16** **Sept** **2019**: Lecture 1a: Introduction - DarrenW 
​	**Fri, 20** **Sept** **2019**: Lecture 1b: Introduction II - DarrenW 

Week 2 (Week commencing: 23 Sept) 

​	**Mon, 23** **Sept** **2019**: Lecture 2: HPC Hardware - DarrenW 
​	**Fri, 27** **Sept** **2019**: Lecture 3: Processors - StephenB 

Week 3 (Week commencing: 30 Sept) 

​	**Mon, 30** **Sept** **2019**: Lecture 4: Processors II - StephenB 
​	**Fri, 04** **Oct 2019**: Lecture 5: Caches - MarkB 

Week 4 (Week commencing: 07 Oct) 

​	**Mon**, 07 Oct 2019: Lecture 6: Cache Coherency - MarkB 
​	**Fri, 11** **Oct 2019**: Lecture 7: Memory - StephenB 

Week 5 (Week commencing: 14 Oct) 

​	**Mon**, 14 Oct 2019: Lecture 8: Advanced CPUs - AdrianJ 
​	**Fri, 18 Oct 2019**: Hardware Review - AdrianJ **- Reminder, no lecture today, reading paper instead** 

Week 6 (Week commencing: 21 Oct) 

​	**Mon, 21 Oct 2019**: Lecture 10: Memory Consistency - MarkB 
​	**Fri, 25 Oct 2019**: Lecture 11: Accelerated Architectures - MarkB 

Week 7 (Week commencing: 28 Oct) 

​	**Mon, 28 Oct 2019**: Lecture 12: Interconnects - StephenB 
​	**Fri, 01 Nov 2019**: Lecture 13: Power monitoring and energy efficiency – MicheleW 

Week 8 (Week commencing: 04 Nov) 

​	**Mon, 04 Nov 2019**: Lecture 14: Compiler Architecture - MarkB 
​	**Fri, 08 Nov 2019**: Lecture 15: HPC Architectures - MarkB 

Week 9 (Week commencing: 11 Nov) 

​	**Mon, 11 Nov 2019**: Lecture 16: Filesystems and big data hardware - AdrianJ 
​	**Fri, 15 Nov 2019**: Lecture 17: Schedulers – IakovosP  

Week 10 (Week commencing: 19 Nov) 

​	**Mon, 18 Nov 2019**: Lecture 18: System Software, Future Hardware and Architectures - AdrianJ **Reminder, no lecture today**
​	**Fri, 22 Nov 2019**: Lecture: Lecture L19: FPGAs – IakovosP 




