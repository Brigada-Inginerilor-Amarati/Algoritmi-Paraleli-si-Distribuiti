# MPI: Bacteria Colony

## Overview
Implement two different parallel versions using MPI.

## Versions (each 10 points)
- 1D data partitioning
- 2D data partitioning

## I/O and Deployment
- Read the initial configuration from an input file and save the final configuration to an output file.
- The program must work with all processes on the same localhost or with processes deployed on several hosts.

## Correctness
- Ensure that serial and parallel versions always produce the same results.

## Communication
- Implement efficient patterns of communication between processes.
- Use collective communication operations where appropriate.

## Performance
- Measure speedup for different input sizes for the 1D version, with numbers of processes appropriate for the physical parallelism of your testing environment.
- For the 2D version, start with a larger number of processes (p=16, p=25) and compare with the 1D version using the same number of processes.