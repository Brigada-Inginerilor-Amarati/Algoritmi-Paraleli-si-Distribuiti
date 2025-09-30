# MPI: Epidemics Simulation

## Overview
Implement a parallel version using MPI.

## I/O and Deployment
- Read the initial configuration from an input file and save the final configuration to an output file.
- The program must work with all processes on the same localhost as well as with processes deployed on several hosts.

## Correctness
- Ensure that serial and parallel versions always produce the same results.

## Communication
- Implement efficient patterns of communication between processes.
- Use collective communication operations where appropriate.

## Performance
- Measure speedup for different input sizes.