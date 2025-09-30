This assignment brings max 20 points.

Build a very simplified MPI infrastructure.  The goal of this assignment is twofold: to learn to work with socket communication between processes, and to better understand how MPI can be implemented. Recall the discussion at the end of last lecture about a MPI implementation over sockets.

Part 1 (10 points)

Implement your "homemade" simplified variant of mpiexec-smpd.   

Implement smpd, a  process manager that can be deployed on different hosts. Smpd acts as a server that receives requests to launch programs. It uses sockets to receive requests. It can launch any program found as an executable file in its local file system.

Implement mpiexec, a client program that transmits requests to smpd servers. It  should be used in the form:

mpiexec -hosts N  IPADDRESS_1 IPADDRESS_2 ....  IPADDRESS_N program.exe

In order to be able to develop and test your implementation on a single computer, have also the scenario when multiple smpd servers are started as distinct processes on different ports on localhost. In this case, mpiexec should be used in this form:

mpiexec -processes N port_1 port_2 .... port_N program.exe

In both cases, there will be created N processes running program.exe and the resulting standard outputs must be shown in the console of mpiexec.

This part does NOT require that you also implement a messaging library.

For  working with processes in Java: see java.lang.ProcessBuilder. It can be used to create processes and to redirect I/O to the parent process.

Part 2 (10 points)

Implement a simplified messaging library that can be used by the programs launched by mpiexec.  Following operations should be  included: 

init - must be first thing called by a program

comm_size  - returns the number of processes

comm_rank  - returns the rank of the current process

send(dest, string)  - sends  the string message to the process with rank dest

receive - receives a message from any process, returns the received message

Demonstrate the usage of your messaging library by implementing a program that uses the implemented messaging functions to communicate between processes. 