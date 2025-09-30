This variant has a maximum number of 20 points
Problem description

Tic-tac-toe or Xs and Os is a game for two players who take turns marking the spaces in a three-by-three grid with X or O. The player who succeeds in placing three of their marks in a horizontal, vertical, or diagonal row is the winner.

In this assignment, we address a generalized form of the game, where the board can have a bigger size of a N-by-N grid. The player who succeeds in placing N of their marks in a horizontal, vertical, or diagonal row is the winner.

In file XXXXXXX  you are given a simple serial implementation of the game when a Player plays against the Computer.

Use parallelization in order to speed up the time needed by a computer to decide its moves.

Implement Player vs Computer and Computer vs Computer scenarios. 

You must implement a switch menu such that, based on a given input, the user 
is able to choose the playing scenario and whether parallelism is used or not.

The purpose of the Computer vs Computer scenario is exclusively for performance measurement purposes. The first computer can always start with the same move. The computer vs computer scenario should support two runtime modes: DEBUG mode, where intermediate  boards are printed, and otherwise in performance mode no intermediate boards are printed.

Performance measurements: For different sizes of the board (N>4) and different depths of the minimax search algorithm, for different number of threads (2, 4, 8), with and without parallelism:

    the duration of each computer move in the Player vs Computer scenario
    the average duration of a computer move in an end-to-end computer vs computer scenario. Compute the obtained speedup obtained by parallelization

Grading

Complete the serial version based on the code already provided - 5 points

Implement parallel version - 12 points

Time Measurement, Speedup, Graphs, Discussion - 3 points

Your submitted code must at least compile. Code with compilation errors gets zero points.

 Code for serial implementation can be found here: https://github.com/RyanKrech/PDA-APD-game
