# OpenMP: Tic-tac-toe (max 20 points)

## Problem description
Tic-tac-toe is generalized to an N×N board. The player who places N marks in a row (horizontal, vertical, or diagonal) wins.

You are given a simple serial implementation of Player vs Computer.

## Goal
Use parallelization to speed up the time needed by the computer to decide its moves.

## Scenarios
- Player vs Computer
- Computer vs Computer (for performance measurements)

Provide a switch menu so the user can choose the scenario and whether parallelism is used.

Computer vs Computer must support:
- DEBUG mode: print intermediate boards
- Performance mode: no intermediate printing

## Performance measurements
For different board sizes (N > 4) and different depths of the minimax search, for different numbers of threads (2, 4, 8), with and without parallelism, measure:
- duration of each computer move in Player vs Computer
- average duration of a computer move end-to-end in Computer vs Computer
- compute the speedup from parallelization

## Grading
- Complete the serial version based on the provided code: 5 points
- Implement parallel version: 12 points
- Time Measurement, Speedup, Graphs, Discussion: 3 points

Notes:
- Your submitted code must at least compile. Code with compilation errors gets zero points.
- Serial implementation reference: `https://github.com/RyanKrech/PDA-APD-game`
