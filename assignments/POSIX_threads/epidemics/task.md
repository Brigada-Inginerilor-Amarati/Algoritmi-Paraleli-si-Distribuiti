# POSIX Threads: Epidemics (max 20 points)

## Problem description
Implement and parallelize a simplified epidemic simulation using Pthreads.

The area is a rectangle; each person has discrete coordinates (x, y). If two persons are in the contagion area, they share the same coordinates.

Persons move in discrete time. Each time step, each person makes one move with a simple pattern:
- Direction (N, S, E, W). At borders, reverse direction until the opposite border is reached.
- Amplitude: step distance. Passing over intermediate positions does not create contacts; only co-location at the destination can infect.

Statuses: infected, immune, susceptible. Sickness lasts `INFECTED_DURATION` steps; then immune for `IMMUNE_DURATION` steps. Each person has current and future status; statuses update each time step based on time and co-located infections.

Pseudocode:
```
while (simulation not over) {
  update location for all persons
  compute future status for all persons
  advance time; future becomes current
}
```

## Input
Command line: `TOTAL_SIMULATION_TIME InputFileName ThreadNumber`

Input file contains:
- MAX_X_COORD, MAX_Y_COORD
- N persons, each with:
  - PersonID
  - Initial coordinates x, y (within bounds)
  - Initial status (infected=0, susceptible=1). Initially no immune persons; initially infected are infected at time 0.
  - Movement direction (N=0, S=1, E=2, W=3)
  - Movement amplitude (integer, less than area dimension on movement direction)

## Implementation
Implement both sequential and parallel versions. The parallel version uses pthreads and divides persons across threads. Provide synchronization so that:
- all locations are updated before infection status updates
- all statuses are updated before proceeding to the next time step

## Output
For each person:
- Final coordinates x, y
- Final status (infected, immune, susceptible)
- Infection counter: number of times infected

Output files: if input is `f.txt`, produce `f_serial_out.txt` and `f_parallel_out.txt`.

Only final results are saved; intermediate states are not saved.

## Validation and modes
- Automatic verification comparing serial and parallel outputs
- Modes: DEBUG (print evolution after each generation) and normal (no printing) for performance

## Performance
- Measure serial and parallel runtimes and compute speedup (exclude I/O)
- Repeat for various population sizes and simulation times; vary thread counts
- Suggested sizes: population 10K, 20K, 50K, 100K, 500K; time 50, 100, 150, 200, 500
- Discuss experimental results

## Grading
- Serial version: 5 points
- Parallel version: 10 points
- Working program with required input format: 3 points
- Comparison serial vs parallel: 0.5 point
- Time measurement, speedup, graphs, discussion: 1.5 points

Notes:
- Your submitted code must at least compile. Code with compilation errors gets zero points.

Examples and updates:
- Higher density of persons is recommended to keep the epidemic active longer.
- Example input files: `epidemics10.txt` (N=10, grid 4×4, 20% infected), `epidemics10K.txt` (N=10K, grid 110×110, 20%), `epidemics20K.txt`, `epidemics100K.txt`.
- You can generate input files using `generator_epidemics.c`. You will need files up to several 100K persons.
