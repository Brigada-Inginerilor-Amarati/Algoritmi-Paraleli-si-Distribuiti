Implement 2 different parallel version using MPI:

    Use 1D data partitioning (10 points)
    Use 2D data partitioning (10 points)

The initial configuration is read from a input file and the final configuration is saved in a output file.  The program must works if it is deployed with all processes on the same localhost or with processes deployed on several hosts! 

Make sure that serial and parallel versions always produce the same results!

Implement efficient patterns of communication between processes. Use collective communication operation where appropriate.

Measure Speedup for different input sizes for  the 1D version, for numbers of processes appropriate for the degree of physical parallelism of your testing environment.

For the 2D version, start with a bigger number of processes (p=16, p=25) and compare with the 1D version with the same number of processes.