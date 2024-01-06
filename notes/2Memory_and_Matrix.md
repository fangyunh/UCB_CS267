# Memory Hierarchies and Matrix Multiplication

### Memory Hierarchies

**Memory accesses costs**:

- Latency: cost to load or store 1 word
- Bandwidth: avg rate to load/store a large chunk, data throughput

**Locality**:

- spatial: accessing things nearby previous accesses
- temporal: reusing an item that was previously accessed

**Cache**

L1, L2, L3

- on-chip caches are faster but smaller.
- large cache has higher delay

### Parallelism Within Single Processors

**Concurrency we need**

- Little's Law: concurrency = latency * bandwidth

**SIMD single instruction multiple data**

- scalar operation: a + b = c
- SIMD (vector) operation: run a1 + b1 = c1, a2 + b2 = c2 ... at same time

**Data Dependencies Limit Parallelism**

- RAW: Read after Write
- WAR: Write after Read
- WAW: Write after Write

**FMA: Fused Multiply Add**

### Matrix Multiplication

![](..\img\model_of_memory.png)

![](..\img\naive_mat_multi.png)

![](..\img\blocked_mat_multi.png)

**Optimization**

- Performance model to predict the best tile size
- Autotuning search to find the best in a range
  - Useful especially in dense matrix operations