```
PERF-SCHED(1)                          perf Manual                         PERF-SCHED(1)

NAME
       perf-sched - Tool to trace/measure scheduler properties (latencies)
                    追踪/衡量调度器特性

SYNOPSIS
       perf sched {record|latency|map|replay|script|timehist}

DESCRIPTION
       There are several variants of perf sched:

           'perf sched record <command>' to record the scheduling events
           of an arbitrary workload.
	   记录调度事件

           'perf sched latency' to report the per task scheduling latencies
           and other scheduling properties of the workload.
	   显示调度器延迟

           'perf sched script' to see a detailed trace of the workload that
            was recorded (aliased to 'perf script' for now).
	    显示追踪记录的详细信息

           'perf sched replay' to simulate the workload that was recorded
           via perf sched record. (this is done by starting up mockup threads
           that mimic the workload based on the events in the trace. These
           threads can then replay the timings (CPU runtime and sleep patterns)
           of the workload as it occurred when it was recorded - and can repeat
           it a number of times, measuring its performance.)
	   模拟记录的工作量

           'perf sched map' to print a textual context-switching outline of
           workload captured via perf sched record.  Columns stand for
           individual CPUs, and the two-letter shortcuts stand for tasks that
           are running on a CPU. A '*' denotes the CPU that had the event, and
           a dot signals an idle CPU.
	   输出记录的上下文切换大纲

           'perf sched timehist' provides an analysis of scheduling events.
	   输出调度时间的分析

           Example usage:
               perf sched record -- sleep 1
               perf sched timehist

           By default it shows the individual schedule events, including the wait
           time (time between sched-out and next sched-in events for the task), the
           task scheduling delay (time between wakeup and actually running) and run
           time for the task:
	   显示独立的调度事件，等待时间、调度时间、运行时间。

                       time    cpu  task name             wait time  sch delay   run time
                                    [tid/pid]                (msec)     (msec)     (msec)
             -------------- ------  --------------------  ---------  ---------  ---------
               79371.874569 [0011]  gcc[31949]                0.014      0.000      1.148
               79371.874591 [0010]  gcc[31951]                0.000      0.000      0.024
               79371.874603 [0010]  migration/10[59]          3.350      0.004      0.011
               79371.874604 [0011]  <idle>                    1.148      0.000      0.035
               79371.874723 [0005]  <idle>                    0.016      0.000      1.383
               79371.874746 [0005]  gcc[31949]                0.153      0.078      0.022
           ...

           Times are in msec.usec.
	   时间单位为 毫秒.纳秒

OPTIONS
       -i, --input=<file>
           Input file name. (default: perf.data unless stdin is a fifo)
           输入文件名

       -v, --verbose
           Be more verbose. (show symbol address, etc)

       -D, --dump-raw-trace=
           Display verbose dump of the sched data.

OPTIONS FOR PERF SCHED MAP
       map命令的选项:

       --compact
           Show only CPUs with activity. Helps visualizing on high core count systems.

       --cpus
           Show just entries with activities for the given CPUs.

       --color-cpus
           Highlight the given cpus.
	   高亮指定的cpus

       --color-pids
           Highlight the given pids.
	   高亮指定的进程

OPTIONS FOR PERF SCHED TIMEHIST
       -k, --vmlinux=<file>
           vmlinux pathname

       --kallsyms=<file>
           kallsyms pathname

       -g, --no-call-graph
           Do not display call chains if present.

       --max-stack
           Maximum number of functions to display in backtrace, default 5.

       -p=, --pid=
           Only show events for given process ID (comma separated list).

       -t=, --tid=
           Only show events for given thread ID (comma separated list).

       -s, --summary
           Show only a summary of scheduling by thread with min, max, and average run
           times (in sec) and relative stddev.

       -S, --with-summary
           Show all scheduling events followed by a summary by thread with min, max, and
           average run times (in sec) and relative stddev.

       --symfs=<directory>
           Look for files with symbols relative to this directory.

       -V, --cpu-visual
           Show visual aid for sched switches by CPU: i marks idle time, s are scheduler
           events.

       -w, --wakeups
           Show wakeup events.

       -M, --migrations
           Show migration events.

       -n, --next
           Show next task.

       -I, --idle-hist
           Show idle-related events only.

       --time
           Only analyze samples within given time window: <start>,<stop>. Times have the
           format seconds.microseconds. If start is not given (i.e., time string is
           ,x.y) then analysis starts at the beginning of the file. If stop time is not
           given (i.e, time string is x.y,) then analysis goes to end of file.

       --state
           Show task state when it switched out.

SEE ALSO
       perf-record(1)

perf                                   04/14/2022                          PERF-SCHED(1)
```
