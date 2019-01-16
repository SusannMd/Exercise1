# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency refers to the ability of different parts or units of a program, algorithm, or problem to be executed out-of-order or in partial order, without affecting the final outcome.
 Parallelism is a form of parallel computing for multiple processors using a technique for a distributing the data across different parallel processor nodes.

 Difference: Parallelism runs more CPUs at the same time. Concurrencu has one processor for each clock

 ### Why have machines become increasingly multicore in the past decade?
 > Kan kjøre parallelism, får en bedre kapasitet

 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Hjelper når man ikke kan kjøre ting samtidig, og må være en viss rekkefølge

 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > Maybe both?!

 ### What are the differences between processes, threads, green threads, and coroutines?
 > Processes: OS-managed (possibly) truly concurrent, at least in the presence of a sutible hardware support. Exists withing their own address space
 Threads: OS-managed, within their same address space as thye parent and all its other threads. Possibly truly concurrent, and multi-tasking is pre-emptive
 Green threads: emulate multithread environments without relying on any native OS capabilities
 Coroutines: Exactly fivers, except not OS-managed

 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 >  pthread_create() - create a thread
 threading.Thread() -
 go creates a gorutine - which is a green thread


 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > Protcts access to Python objects, preventing multiple threads from executing Pyhton bytecodes at once. Necessary mainly becouse CPython's meomory management is not thread-safe. Syncronize

 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > Multiprocessing - can use parallelism. Instead of threads they use sub-processes

 ### What does `func GOMAXPROCS(n int) int` change?
 > Sets the maxmimum number of CPUs that can be executed simultaneously and returns the previous setting.
