# Cache
## What is a cache?
The cache is small and fast storage that is used to improve the access time to memory. This is between registers on the CPU and memory. Caches use the principle of Locality. The principle of locality refers to the relatively small portion of the address space that a program accesses at any instant in time. There are two different types of locality:<br>
1. Temporal Locality<br>
This is the locality in time that indicates that if an item is reference at some point in time, then it will likely be referenced again later.<br>

2. Spatial Locality<br>
This is the locality in space where if an item is referenced, then items with nearby addresses are likely to be reference as well.<br>

## Word and Block
When we access a word, a word is not returned to us, but instead, we get a __block__. 

## Terminology
Hit<br>
Hit means that the data exists in some block in the upper level. The __Hit Rate__ is the fraction of memory access found in the upper level. The __Hit Time__ is the time taken to access the upper level consisting of:
```
RAM access time + Time to determine hit/miss
```
Miss<br>
Miss means that the data needs to be retrieved from a block in a lower level. The __Miss Rate__ is 1 - _Hit Rate_. The __Miss Penalty__ is the time taken to replace a block in the upper level and the time to deliver the block in the processor. 

## Cache Performance
Memory stall cycles are the number of cycles where the CPU is waiting for memory access.
CPU time = (CPU<sub>clock cycles</sub> + Mem<sub>stall cycles</sub>) X Cycle Time<br>
Mem<sub>stall cycles</sub> = Number of Misses X Miss Penalty<br>
Mem<sub>stall cycles</sub> = IC X (MemAcess/Inst) X Miss Rate X Miss Penalty<br>


### Q123 only work if we read from the memory
### Q4 only works if we write to the memory

Write Through - data is modified at all levels (cache and memory)
Write Back - data is modified in blocks only in cache level

## Block Placement
### Fully Associative
