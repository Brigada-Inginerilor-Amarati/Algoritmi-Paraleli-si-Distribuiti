# POSIX Threads: Barrier (max 20 points)

## Problem description
A barrier is a synchronization primitive that blocks all participants at a synchronization point until all participants reach that point.

POSIX defines a barrier interface for Pthreads, but some implementations don’t provide it. Implement a portable barrier with an API similar to Pthreads:

- `pthread_barrier_t` → `my_barrier_t`
- `pthread_barrier_init` → `my_barrier_init`
- `pthread_barrier_destroy` → `my_barrier_destroy`
- `pthread_barrier_wait` → `my_barrier_wait`

## Requirements
Implement the following API:

```c
typedef struct {
   int count; // counts threads in barrier
   // … add other fields necessary for your implementation
} my_barrier_t;

void my_barrier_init(my_barrier_t *b, int count);
void my_barrier_destroy(my_barrier_t *b);
void my_barrier_wait(my_barrier_t *b);
```

Usage: declare a `my_barrier_t` and initialize it with `my_barrier_init(count)`. Each participating thread calls `my_barrier_wait()` at the synchronization point. If initialized with `count = N`, the first `N-1` threads block until the last arrives; then all continue and the barrier resets.

You may use pthread mutexes and condition variables. Maintain a shared counter of threads reaching the barrier; the last thread signals the others.

## Demonstration
Model the daily life of the Jones Family with threads: Mama, Papa, Alice, Bob, Chris, Dave. Each thread executes its daily schedule, with barriers for group activities (breakfast, study pairs, football, dinner). Simulate Monday–Friday. Print start/end of activities and readiness for group activities.

Example excerpt:

```text
Alice is ready to learn math with Bob
Dave is ready to play football with Chris
Chris is ready to play football with Dave
Chris plays football with Dave
Dave plays football with Chris
Dave is ready to eat dinner with family
Chris is ready to eat dinner with family
Bob is ready to learn math with Alice
Alice learns math with Bob
Bob learns math with Alice
Papa is ready to eat dinner with family
```

## Benchmark and comparison
Create a benchmark with `NUMTHREADS` threads; in each of `REPEATS` iterations, do dummy work in `do_work` and wait at the barrier:

```c
for (i = 0; i < REPEATS; i++) {
   do_work(thread_id);
   barrier_wait(&barrier);
}
```

Provide two versions: one using `pthread_barrier_t`, one using `my_barrier_t`. For various `NUMTHREADS` and `REPEATS`, measure runtimes, repeating experiments to compute averages. Compare average times.

## Grading
- Implementation of `my_barrier`: 7 points
- Jones family demo: 6 points
- Benchmark programs: 5 points
- Measurements, comparison, discussion: 2 points