# MP_Java: Simplified MPI Infrastructure (max 20 points)

## Overview

Build a very simplified MPI infrastructure. The goals are:

- learn socket communication between processes
- understand how MPI can be implemented

Recall the lecture discussion about implementing MPI over sockets.

### Part 1 (10 points): Process Manager and Launcher

Implement your homemade simplified variant of mpiexec-smpd.

#### smpd (server)

Implement a process manager deployable on different hosts. It acts as a server that receives requests to launch programs over sockets. It can launch any program found as an executable file in its local file system.

#### mpiexec (client)

Client program that transmits requests to smpd servers.

Usage with multiple hosts:

``` shell
mpiexec -hosts N IPADDRESS_1 IPADDRESS_2 ... IPADDRESS_N program.exe
```

Usage with multiple smpd on localhost (different ports):

``` shell
mpiexec -processes N port_1 port_2 ... port_N program.exe
```

In both cases, create N processes running `program.exe` and aggregate their standard outputs in the `mpiexec` console.

Notes:

- This part does NOT require a messaging library implementation.
- For working with processes in Java, see `java.lang.ProcessBuilder` (create processes, redirect I/O to parent).

## Part 2 (10 points): Simplified Messaging Library

Implement a simplified messaging library used by the programs launched by `mpiexec`.

### Required operations

- `init` — must be first thing called by a program
- `comm_size` — returns the number of processes
- `comm_rank` — returns the rank of the current process
- `send(dest, string)` — sends the string message to process with rank `dest`
- `receive` — receives a message from any process, returns the message

### Demonstration

Show usage by implementing a program that uses the messaging functions to communicate between processes.
