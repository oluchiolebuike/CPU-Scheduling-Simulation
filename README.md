# Scheduling Algorithm Comparison — Allegra the Barman
- A simulation study comparing four standard CPU scheduling algorithms using bash and python scripts across runs — FCFS, SJF, Priority and MLFQ plus a custom bonus algorithm (BPQ-ADRR), modelled through the analogy of a busy bar.
- Grade: 94%

## Overview
Patrons map to processes, drink orders map to CPU bursts and drinking intervals map to I/O waits. Allegra the Barman acts as both the CPU and scheduler, serving orders according to each algorithm's rules. All algorithms are non-preemptive at the order level (no half-made drinks).

## Experimental Setup
- Light load: 5, 10, 15, 20 patrons
- Heavy load: 10, 30, 50, 100 patrons 
- Seeds: 32, 110, 454, 777, 1008 (fixed across all schedulers for fair comparison)
- Context-switch overhead: 5 ms (constant)
- Total runs: 200 (100 light + 100 heavy)

## BPQ-ADRR Analysis
- Best light-load performance; highest throughput
- BPQ-ADRR suits high-throughput venues (festivals, clubs) where maximising orders served matters most
- For a typical low-to-medium load bar it's the best option
- Inflated heavy-load averages but still had the highest throughput
- It accumulates wait time across twice as many orders which inflates the per-algorithm average
- Its worst-case waiting time is actually better than Priority despite serving far more orders meaning its starvation protection holds up reasonably well

