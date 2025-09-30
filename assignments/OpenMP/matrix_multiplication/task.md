# OpenMP: Matrix Multiplication (max 30 points)

## Problem description
Provide several implementations of matrix multiplication algorithms, both serial and parallel, and analyze their performance. This assignment continues the discussion from `DenseMatrix.pdf`.

### (i, j, k) loop permutations
Explore implementations of square matrix multiplication for all 6 permutations of (i, j, k):
- i-j-k, i-k-j, j-i-k, j-k-i, k-i-j, k-j-i

The variants i-j-k and i-k-j are discussed in Lecture and implemented in `omp_matrix_mult.c`.

### Blocked matrix multiplication
Implement the blocked matrix multiplication algorithm (as suggested in `DenseMatrix.pdf`) in serial and with OpenMP.
- Handle cases where matrix size is not evenly divisible by the block size
- Determine a good block size empirically for your computer

### Dataset
- Square matrices N×N, where N varies between 1000 and 3000
- Values can be generated randomly

### Validation
For each version, validate results by automatic comparison with the classical i-j-k version.

## Grading
- Serial versions of all (ijk) permutation algorithms: 6 points
- Parallel versions of all (ijk) permutation algorithms: 6 points
- Serial version of blocked algorithm: 7 points
- Parallel version of blocked algorithm: 7 points
- Automatic validation vs classical i-j-k: 1 point
- Performance measurements and discussion for (ijk) algorithms (serial and parallel): 1.5 points
- Performance measurements and discussion for blocked algorithm + block size experiments: 1.5 points

Notes:
- Your submitted code must at least compile. Code with compilation errors gets zero points.
