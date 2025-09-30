# OpenMP: Epidemics (max 20 points)

## Problem description
Implement and parallelize a simplified epidemic evolution simulation using OpenMP.

The complete description is the same as the corresponding Assignment1 variant. If you already implemented that, continue by adding OpenMP parallel versions. If not, implement your own serial version as part of this assignment.

## Parallel versions
- V1: use `parallel for`; investigate different scheduling policies and chunk sizes
- V2: either manual explicit data partitioning or OpenMP tasks

## Expected results
Output (same as Assignment1) for each person:
- Final coordinates x, y
- Final status (infected, immune, susceptible)
- Infection counter: number of times the person became infected

Output files: if input file was `f.txt`, then `f_serial_out.txt`, `f_omp1_out.txt`, `f_omp2_out.txt`.

Only the final result is saved; intermediate states are not saved.

## Validation and modes
- Provide automatic verification comparing serial and parallel results.
- Two running modes: DEBUG (print evolution after each generation) and normal (no printing) for performance.

## Performance
- Measure serial and parallel runtimes and compute speedup (exclude I/O time).
- Repeat for different population sizes, simulation durations, and thread counts.
- Provide a meaningful discussion of experimental results.

## Grading
- Serial version (from Assignment1 or implemented now): 5 points
- Parallel version V1: 5 points
- Parallel version V2: 5 points
- Working program with required input format: 2 points
- Automated comparison serial vs parallel: 1 point
- Time measurement, speedup, graphs, discussion: 2 points

Notes:
- Your submitted code must at least compile. Code with compilation errors gets zero points.
