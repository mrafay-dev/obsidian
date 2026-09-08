`asm volatile("" ::: "memory")` is a compiler barrier

asm (template : output operands : input operands : clobbers)

`asm` tells compiler this is assembly
`volatile` - prevents compiler optimising this or reordeing

`""` - no CPU instructions here
`"memory"` - clobber list, tells compiler it might read or write to any memory address which exists

compiler
1. prevents memory reordering
2. forces register spilling - any vars in cpu registers must be written to RAM before and then re-read from RAM after


**Uses** 
If theres a simple for loop, compiler might just optimise it away - not useful for benchmarks
Writing spinlocks - ensure compilre doesn't cache the lock, rendering it useless
forcing variable to be in RAM, not jusst CPU
