# Subject: Operating Systems (B.Tech CSE Core)

## Topic 1: Process vs Thread
A  and Wait: A process must be currently holding at least one resource while requesting additional resources held by other processes.
3. No Preemption: Resources cannot be forcibly taken away from a process; they can only be released voluntarily by the process holding them after it finishes its task.
4. Circular Wait: A closed chain of processes exists such that Process P0 waits for a resource held by P1, P1 waits for P2, and Pn waits for a resource held by P0.

## Topic 3: Virtual Memory, Paging, and Page Faults
Virtual Memory is a memory management technique that gives each process the illusion of having a large, contiguous private memory space, even when physical RAM is smaller. The OS divides virtual memory into fixed-size blocks called Pages (typically 4 KB) and physical RAM into fixed-size blocks called Frames.
A Page Table maps virtual page numbers to physical frame numbers. When a CPU requests a virtual address whose page is not currently loaded in physical RAM, the hardware triggers a Page Fault trap. The OS pauses the process, locates the required page on the secondary disk (swap space), loads it into a free RAM frame, updates the Page Table, and restarts the instruction. If the system spends more time swapping pages between disk and RAM than executing instructions, it enters a severe performance collapse called Thrashing.

## Topic 4: CPU Scheduling Algorithms (FCFS, SJF, and Round Robin)
CPU Scheduling determines which process in the Ready Queue gets allocated to the CPU next.
1. First-Come, First-Served (FCFS): A non-preemptive queue where the first process to arrive executes until completion. FCFS suffers from the Convoy Effect, where one long CPU-bound process forces many short I/O-bound processes to wait, increasing average waiting time.
2. Shortest Job First (SJF): Selects the process with the smallest next CPU burst time. While SJF is mathematically optimal for minimizing average waiting time, it can cause Starvation for long processes if short processes keep arriving continuously.
3. Round Robin (RR): Designed for time-sharing interactive systems. Each process gets a fixed small unit of CPU time called a Time Quantum (typically 10 to 100 milliseconds). If the process does not finish within the time quantum, the OS preempts it and moves it to the back of the Ready Queue.

