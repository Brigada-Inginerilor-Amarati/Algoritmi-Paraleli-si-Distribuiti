This variant has a maximum number of 20 points

Problem description

In this assignment you implement and parallelize a highly simplified simulation model for the evolution of an infectious disease in a population, using parallel programming with OpenMP.

The  complete description of the simulation problem is  the same as in the corresponding Assignment1 Variant.

If you already implemented this variant for Assignment1, you can continue adding parallel versions with OpenMP. You can do this variant of Assignment2 even if you did not do the Epidemics problem for Assignment, but  in this case, you must implement your own serial version as well as part of Assignment2.

In this assignment, provide two different parallel versions of the epidemics simulation:

    V1: use parallel for,  investigate different scheduling policies and chunksizes
    V2:  you can either use manual explicit data partitioning or you can use omp tasks

Expected results:

The output: The same as in Assignment1: For each person:

     Final coordinates x, y
      Final status (infected, immune, susceptible)
     Infection counter: how many times during the simulation did the person become infected

The final output will be saved in files. If input file was  f.txt, then output files are following the name convention f_serial_out.txt, f_omp1_out.txt and f_omp2_out.txt

Only the final result is saved – intermediate status at every simulation time moment is not saved in files.

Implement an automatic verification method to compare that the serial and parallel versions produce the same result.  

The program must provide 2 modes of running: the interactive (DEBUG) mode, when the evolution of the persons is printed after each generation, and the normal mode (without printing) for performance measurements.

Measure serial and parallel runtime and compute the speedup. The measured runtime does NOT include reading initial configuration from file and writing the final configuration in a file.

Repeat measurements for different sizes of the population, number of simulated time units, and different number of threads.

 Provide a meaningful discussion of your experimental results.

Grading

Implemented serial version - your own from assignment1 or implemented now  5 points

Implement parallel version1 5 points

Implement parallel version2 5 points

A working program, reading input data in the required format  2 points

Perform comparison between serial and parallel result (provide automated possibility of comparing outputs - they must be the same as the simulation scenario is deterministic) 1 point

Time Measurement, Speedup, Graphs, Discussion 2 point

Your submitted code must at least compile. Code with compilation errors gets zero points.
