# POSIX Threads: Bacteria Colony (max 10 points)

## Problem description
Simulate the evolution of a bacteria colony on a rectangular 2D grid.

Initially, bacteria are seeded at specific grid points (at most one per point). The colony evolves in discrete generations with synchronous updates:
- Birth: if 3 neighbors around an empty cell, a new bacterium spawns
- Death: isolation (fewer than 2 neighbors) or overcrowding (more than 3 neighbors)

Given the initial seeding, determine the final configuration after G generations.

Input files: first line has rows and columns; each subsequent character is `X` (bacterium) or `.` (empty).

Reference materials:
- Example inputs: `bacteria-data.zip`
- Sequential baseline: `bacteria_algorithm.c`

## Requirements
Implement both serial and parallel versions.

Command line: input file, number of generations, number of threads.

Parallel version uses pthreads with grid data partitioning (striping) and barrier synchronization between generations.

## Validation and modes
- Automatic check: serial and parallel results must match.
- Modes: DEBUG (print grid every generation) and normal (no printing) for measurements.

## Output
If input is `f.txt`, outputs are `f_serial_out.txt` and `f_parallel_out.txt`.

Only final configurations are saved.

## Performance
- Measure serial and parallel runtimes; compute speedup (exclude I/O).
- Repeat for various grid sizes and thread counts; plot speedup vs threads; discuss results.

## Grading
- Parallel version: 6 points
- Working program with required input format: 2 points
- Serial vs parallel comparison: 0.5 point
- Time measurement, speedup, graphs, discussion: 1.5 points

Notes:
- Your submitted code must at least compile. Code with compilation errors gets zero points.
