proof of Internship: https://drive.google.com/drive/folders/1A7yyCnujzIXhRx3tdcgjpiUbG1SX7Y5G?usp=sharing
# DRAM-Controller

Thread Cluster Memory Scheduling:Exploiting Differences in Memory Access Behavior
In a modern chip-multiprocessor system, memory is a shared resource among multiple concurrently executing threads. The memory scheduling algorithm should resolve memory contention by arbitrating memory access in such a way that competing threads progress at a relatively fast and even pace, resulting in high system throughput and fairness. Previously proposed memory scheduling algorithms are predominantly optimized for only one of these objectives: no scheduling algorithm provides the best system throughput and best fairness at the same time.



The idea presents a new memory scheduling algorithm that addresses system throughput and fairness separately with the goal of achieving the best of both. The main idea is to divide threads into two separate clusters and employ different memory request scheduling policies in each cluster. The proposal, Thread Cluster Memory scheduling (TCM), dynamically groups threads with similar memory access behavior into either the latency-sensitive (memory-non-intensive) or the bandwidth-sensitive (memory-intensive) cluster. 
TCM introduces three major ideas for prioritization: 
1) we prioritize the latency-sensitive cluster over the bandwidth-sensitive cluster to improve system throughput; 
2) we introduce a “niceness” metric that captures a thread’s propensity to interfere with other threads; 
3) we use niceness to periodically shuffle the priority order of the threads in the bandwidth-sensitive cluster to provide fair access to each thread in a way that reduces inter-thread interference. 

On the one hand, prioritizing memory-non-intensive threads significantly improves system throughput without degrading fairness, because such “light” threads only use a small fraction of the total available memory bandwidth. On the other hand, shuffling the priority order of memory-intensive threads improves fairness because it ensures no thread is disproportionately slowed down or starved.
