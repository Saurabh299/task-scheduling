# task-scheduling
CPU Scheduling Simulator (FCFS)
A simple C++ console program that simulates the First Come First Serve (FCFS) CPU scheduling algorithm with per-process metrics and averages.

Features
Takes process list input with Arrival Time, Burst Time, and Priority fields.

Computes start, completion, turnaround, and waiting times for each process.

Prints a simple Gantt-like “Chart” order and averages for WT and TAT.

Algorithm
FCFS is a non-preemptive scheduling algorithm that schedules processes in the order of arrival and computes: 
TAT
=
CT
−
AT
TAT=CT−AT and 
WT
=
TAT
−
BT
WT=TAT−BT.

Requirements
C++17-compatible compiler (g++/clang++ or MSVC).

A terminal/shell environment to compile and run.

Build and Run
Using g++
Compile:

Single source file:

g++ -std=c++17 -O2 -Wall -Wextra -o fcfs main.cpp

Run:

./fcfs

If there are multiple .cpp files in the project later, compile with:

g++ -std=c++17 -O2 -Wall -Wextra *.cpp -o fcfs

Windows (MSVC Developer Command Prompt)
cl /std:c++17 /O2 /W4 /Fe:fcfs.exe main.cpp

VS Code or IDEs
Use a C++ environment configured per platform guides; VS Code docs provide a setup walkthrough for Linux/macOS/WSL/Windows.

Usage
Start the program and enter the number of processes.

For each process, input: Arrival Time, Burst Time, Priority (priority is stored but not used by FCFS).

Choose option 1 (FCFS) to compute results, or 2 to exit.

Example interaction:

Enter number of processes: 3

Enter Arrival Time, Burst Time and Priority for Process 1: 0 5 1

Enter Arrival Time, Burst Time and Priority for Process 2: 2 3 2

Enter Arrival Time, Burst Time and Priority for Process 3: 4 2 1

Select 1 for FCFS to see per-process CT, TAT, WT and averages.

Output
The program prints:

A simple execution order line like: “| p1 | p2 | p3” (arrival-sorted). 

A table with columns: AT, BT, CT, TAT, WT.

Averages for Waiting Time and Turnaround Time with two-decimal formatting.

Formulas used:

Turnaround Time
=
Completion Time
−
Arrival Time
Turnaround Time=Completion Time−Arrival Time

Waiting Time
=
Turnaround Time
−
Burst Time
Waiting Time=Turnaround Time−Burst Time

Notes and Known Issues
In FCFS, completion progresses by burst time, not arrival time; ensure the implementation updates current_time with burst time when processing a job.

Priority is currently unused in FCFS; it exists for potential future algorithms (e.g., Priority Scheduling).

The “Chart” is a textual hint of execution order and is not a scaled Gantt chart.

Project Structure
main.cpp — All logic (Process struct/class, FCFS function, input menu).

README.md — This file with build, run, and algorithm notes.

Extending
Potential additions:

Add SJF, SRTF, Round Robin, and Priority Scheduling into the same menu.

Render a proper Gantt chart string with time markers.

Validate inputs and handle edge cases like idle gaps between arrivals.

References
FCFS algorithm concepts and examples, including TAT/WT formulas.

General README writing guidelines and structure.

g++ usage for compiling C++ programs and multi-file builds.

Minimal example of compiling and running a C++ console program.

VS Code C++ environment setup reference.

