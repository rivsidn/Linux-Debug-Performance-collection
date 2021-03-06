PERF-BENCH(1)                          perf Manual                         PERF-BENCH(1)

NAME
       perf-bench - General framework for benchmark suites
                    基准测试组建的通用框架

SYNOPSIS
       perf bench [<common options>] <subsystem> <suite> [<options>]

DESCRIPTION
       This perf bench command is a general framework for benchmark suites.

COMMON OPTIONS
       -r, --repeat=
           Specify amount of times to repeat the run (default 10).
	   指定循环执行的次数

       -f, --format=
           Specify format style. Current available format styles are:
	   指定输出格式

       default
           Default style. This is mainly for human reading.

           .ft C
           % perf bench sched pipe                      # with no style specified
           (executing 1000000 pipe operations between two tasks)
                   Total time:5.855 sec
                           5.855061 usecs/op
                           170792 ops/sec
           .ft

       simple
           This simple style is friendly for automated processing by scripts.

           .ft C
           % perf bench --format=simple sched pipe      # specified simple
           5.988
           .ft

SUBSYSTEM
       sched
           Scheduler and IPC mechanisms.
	   调度和IPC机制

       mem
           Memory access performance.
	   内存访问性能

       numa
           NUMA scheduling and MM benchmarks.
	   numa调度和内存基准

       futex
           Futex stressing benchmarks.

       epoll
           Eventpoll (epoll) stressing benchmarks.

       all
           All benchmark subsystems.

   SUITES FOR sched
       messaging
           Suite for evaluating performance of scheduler and IPC mechanisms. Based on
           hackbench by Rusty Russell.
	   用于评估调度器和IPC机制的组建.

       Options of messaging
           -p, --pipe
               Use pipe() instead of socketpair()

           -t, --thread
               Be multi thread instead of multi process

           -g, --group=
               Specify number of groups

           -l, --nr_loops=
               Specify number of loops

       Example of messaging
               .ft C
               % perf bench sched messaging                 # run with default
               options (20 sender and receiver processes per group)
               (10 groups == 400 processes run)

                     Total time:0.308 sec

               % perf bench sched messaging -t -g 20        # be multi-thread, with 20 groups
               (20 sender and receiver threads per group)
               (20 groups == 800 threads run)

                     Total time:0.582 sec
               .ft

           pipe
               Suite for pipe() system call. Based on pipe-test-1m.c by Ingo Molnar.

       Options of pipe
           -l, --loop=
               Specify number of loops.

       Example of pipe
               .ft C
               % perf bench sched pipe
               (executing 1000000 pipe operations between two tasks)

                       Total time:8.091 sec
                               8.091833 usecs/op
                               123581 ops/sec

               % perf bench sched pipe -l 1000              # loop 1000
               (executing 1000 pipe operations between two tasks)

                       Total time:0.016 sec
                               16.948000 usecs/op
                               59004 ops/sec
               .ft

   SUITES FOR mem
       memcpy
           Suite for evaluating performance of simple memory copy in various ways.

       Options of memcpy
           -l, --size
               Specify size of memory to copy (default: 1MB). Available units are B, KB,
               MB, GB and TB (case insensitive).

           -f, --function
               Specify function to copy (default: default). Available functions are
               depend on the architecture. On x86-64, x86-64-unrolled, x86-64-movsq and
               x86-64-movsb are supported.

           -l, --nr_loops
               Repeat memcpy invocation this number of times.

           -c, --cycles
               Use perf’s cpu-cycles event instead of gettimeofday syscall.

           memset
               Suite for evaluating performance of simple memory set in various ways.

       Options of memset
           -l, --size
               Specify size of memory to set (default: 1MB). Available units are B, KB,
               MB, GB and TB (case insensitive).

           -f, --function
               Specify function to set (default: default). Available functions are
               depend on the architecture. On x86-64, x86-64-unrolled, x86-64-stosq and
               x86-64-stosb are supported.

           -l, --nr_loops
               Repeat memset invocation this number of times.

           -c, --cycles
               Use perf’s cpu-cycles event instead of gettimeofday syscall.

   SUITES FOR numa
       mem
           Suite for evaluating NUMA workloads.
	   NUMA工作负载测试组件

   SUITES FOR futex
       hash
           Suite for evaluating hash tables.

       wake
           Suite for evaluating wake calls.

       wake-parallel
           Suite for evaluating parallel wake calls.

       requeue
           Suite for evaluating requeue calls.

       lock-pi
           Suite for evaluating futex lock_pi calls.

   SUITES FOR epoll
       wait
           Suite for evaluating concurrent epoll_wait calls.

       ctl
           Suite for evaluating multiple epoll_ctl calls.

SEE ALSO
       perf(1)

perf                                   03/29/2022                          PERF-BENCH(1)
