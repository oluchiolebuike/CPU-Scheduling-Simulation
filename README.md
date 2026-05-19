# Scheduling Algorithm Comparison — Allegra the Barman
A simulation study comparing four standard CPU scheduling algorithms using bash scripts across runs — FCFS, SJF, Priority and MLFQ plus a custom bonus algorithm (BPQ-ADRR), modelled through the analogy of a busy bar.

## Overview
Patrons map to processes, drink orders map to CPU bursts and drinking intervals map to I/O waits. Allegra the Barman acts as both the CPU and scheduler, serving orders according to each algorithm's rules. All algorithms are non-preemptive at the order level (no half-made drinks).

## Experimental Setup
- Light load: 5, 10, 15, 20 patrons
- Heavy load: 10, 30, 50, 100 patrons 
- Seeds: 32, 110, 454, 777, 1008 (fixed across all schedulers for fair comparison)
- Context-switch overhead: 5 ms (constant)
- Total runs: 200 (100 light + 100 heavy)

## Key Findings
### SJF
- Lowest avg wait & turnaround (heavy load)
- Starvation risk for complex orders
- 
## FCFS
- Most fair & predictable, zero starvation
- Higher average wait times
- 
## Priority
- Best response time 
- Severe starvation for low-priority patrons
- 
## MLFQ
- Aging limits worst-case waits
- Overhead exceeds FCFS under this workload

## BPQ-ADRR
- Best light-load performance; highest throughput
- Inflated heavy-load averages but still had the highest throughput

### Recommendation
SJF is recommended for a typical bar — lowest waiting and turnaround times with near-zero response time. FCFS is preferred when fairness is paramount. BPQ-ADRR suits high-throughput venues (festivals, clubs) where maximising orders served matters most.

## Metrics Tracked
- Average & median waiting time per patron
- Response time (first drink wait)
- Turnaround time
- Throughput (total orders completed)
- Starvation outlier detection (IQR-based)
