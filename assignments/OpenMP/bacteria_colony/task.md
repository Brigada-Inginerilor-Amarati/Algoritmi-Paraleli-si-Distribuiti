This variant has a maximum number of 20 point

Problem description

Simulate the evolution of a  colony of bacteria that is grown on a culture surface of rectangular shape. 

The general problem description is the same as in Assignment 1 - Variant Bacteria.

Given the configuration of the initial bacterial seeding,  determine  the final configuration of the bacterial colony after a number of G generations.  Implement parallel versions of the simulation algorithm using OpenMP.

Initial configurations are loaded from files. The first line contains the number of rows and columns. Starting with the second line, every character represents a grid point and is an “X” (bacterium) or  “.” (empty).

Examples of initial configuration input files are provided in bacteria-data.zip.

The bare code implementing the sequential algorithm is given in bacteria-algorithm.c

Requirements

Implement a program that determines the final configuration both in serial and parallel.

The name of the input file, the number of generations and the number of threads for the parallel versions are given as command line arguments.

The parallel versions will use OpenMP.

For full points, implement 4 different parallel versions:

    V1: use parallel for. Investigate various scheduling policies and chunksizes
    V2: use parallel for but let threads be created only once in the beginning
    V3: use manual explicit data partitioning
    V4: use omp tasks

Implement an automatic validation method to compare that the result (the final configuration) of each parallel versions is the same as  the  result produced by the serial version.  

The program must provide 2 modes of running: the interactive (DEBUG) mode, when the evolution of the grid is printed on screen after each generation, and the normal mode (without any printing) for performance measurements.

The final configuration will be saved in files. If input file was  f.txt, then output files are following the name convention f_serial_out.txt and f_parallel_omp_Vn.txt where for parallel n is the version number.

Only the final result is saved – intermediate configurations for all generations are not saved in files.

Measure serial and parallel runtime and compute the speedup.  The measured runtime does NOT include reading initial configuration from file and writing the final configuration in a file.

Repeat measurements for different sizes of the  input grid and different number of parallel threads and draw the graph of speedup as a function of number of threads for different sized of the input grid. Provide a meaningful discussion of your experimental results.

Grading 

A working program, reading input data in the required format  2 points

Implement parallel version1  4 points

Implement parallel version2  4 points

Implement parallel version3  4 points

Implement parallel version4  4 points

Time Measurements, Validated results by comparisons, Speedup, Graphs, Discussion for all 4 variants. 2 points 

Your submitted code must at least compile. Code with compilation errors gets zero points.