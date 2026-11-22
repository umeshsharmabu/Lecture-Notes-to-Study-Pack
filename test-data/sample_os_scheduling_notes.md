# Sample A — Operating Systems: CPU Scheduling

CPU scheduling selects a process from the ready queue and allocates the CPU to it.
FCFS is non-preemptive and runs processes in arrival order. It can cause the convoy effect.
SJF selects the process with the smallest next CPU burst. If burst lengths are known, it gives the minimum average waiting time. SJF can cause starvation.
SRTF is the preemptive form of SJF and selects the process with the smallest remaining CPU burst.
Round Robin is preemptive. Each process receives a fixed time quantum. A very small quantum increases context-switch overhead; a very large quantum makes it behave like FCFS.
Priority scheduling selects the process with the highest priority. It may be preemptive or non-preemptive. Low-priority processes can starve; aging gradually increases their priority.

Turnaround Time = Completion Time - Arrival Time.
Waiting Time = Turnaround Time - Burst Time.
Response Time = First CPU Allocation Time - Arrival Time.
