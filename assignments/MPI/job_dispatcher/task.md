# MPI: Job Dispatcher (max 40 points)

## Problem description
Servers are often implemented as server clusters: a group of computer servers, in order to supply server functionality beyond the capability of a single machine. In this assignment you simulate the functionality of such a server cluster.

The main server acts as a job dispatcher. It continuously receives commands and dispatches the commands to worker servers out of his cluster. If there are no free servers at the moment, then it waits until one of them finishes its current work. 

The worker servers execute the commands and send results back to main server. The main server writes the results in files, having a file for each client. The main server also produces a log where it records the time moment when each command has been received, when it has been dispatched to a worker server, and when it has been finished.

The commands arriving at the server are simulated by a command file. A command file contains several lines, where each line may contain either a request from a client to execute a specific command, or an indication that the server must wait a period of time before reading the next request line. This wait is used to simulate a bursty arrival of client requests. The client requests can be:

- PRIMES N — find out how many primes there are in the first N natural numbers
- PRIMEDIVISORS N — find out how many prime divisors has the number N
- ANAGRAMS name — generates all anagrams (permutations) of name. LaterUpdate: it is ok to consider only names with up to 8 characters.

Commands may come in any order and in any combination. For example, a command file can be:

```text
CLI0 PRIMEDIVISORS 452876
CLI1 ANAGRAMS tralala
CLI2 PRIMEDIVISORS 129072
WAIT 2
CLI3 PRIMES 2908764
WAIT 1
CLI4 PRIMES 10000987
CLI5 PRIMES 12043876
CLI6 PRIMES 20876
CLI7 ANAGRAMS supercalifragilistic
WAIT 3
CLI8 ANAGRAMS caterpillar
CLI9 ANAGRAMS rainbow
CLI10 PRIMES 3451629
```

## Requirements
- Choose a good architecture for your server cluster; design the Main server to perform different concurrent activities and define its protocol of interactions with the other servers.
- Use MPI for the implementation.
- Ensure the application works when deployed with all processes on a single machine or distributed across multiple machines.

### Standard requirements (20 points)
Implement the server cluster with job dispatcher described above. Execute performance measurements and report your results: for a long list of random commands, without WAIT commands inserted between them, compare the total time needed to complete the list of commands executed serially with the total time needed by executing them on the server cluster.

### Bonus features (additional 20 points)
Some types of commands need more computational power and they will be assigned to a group of free servers to be executed in parallel. For example, MATRIX operations must be assigned to groups of servers if they operate on sizes bigger than some threshold. Extend the job dispatcher and its protocol of interaction with the other servers in order to handle this case.

Supported MATRIX operations to add:
- `MATRIXADD N filename1 filename2` — matrix addition of two matrices of size N×N, with elements given in files
- `MATRIXMULT N filename1 filename2` — matrix multiplication of two matrices of size N×N, with elements given in files

The filenames in these commands refer to files available in the local filesystem of the Main server. The results of matrix operations will be saved in files in the local filesystem of the Main server.