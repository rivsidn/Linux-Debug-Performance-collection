```
PERF-KMEM(1)                           perf Manual                          PERF-KMEM(1)

NAME
       perf-kmem - Tool to trace/measure kernel memory properties
                   追踪内核内存工具

SYNOPSIS
       perf kmem {record|stat} [<options>]

DESCRIPTION
       There are two variants of perf kmem:

           'perf kmem record <command>' to record the kmem events of an arbitrary workload.
	   记录内核内存事件
           'perf kmem stat' to report kernel memory statistics.
	   上报内核内存事件

OPTIONS
       -i <file>, --input=<file>
           Select the input file (default: perf.data unless stdin is a fifo)

       -f, --force
           Don’t do ownership validation

       -v, --verbose
           Be more verbose. (show symbol address, etc)

       --caller
           Show per-callsite statistics

       --alloc
           Show per-allocation statistics

       -s <key[,key2...]>, --sort=<key[,key2...]>
           Sort the output (default: frag,hit,bytes for slab and bytes,hit for page).
           Available sort keys are ptr, callsite, bytes, hit, pingpong, frag for slab
           and page, callsite, bytes, hit, order, migtype, gfp for page. This option
           should be preceded by one of the mode selection options - i.e. --slab,
           --page, --alloc and/or --caller.

       -l <num>, --line=<num>
           Print n lines only
	   输出行数

       --raw-ip
           Print raw ip instead of symbol
	   输出地址而不是符号表

       --slab
           Analyze SLAB allocator events.
	   分析SLAB事件

       --page
           Analyze page allocator events

       --live
           Show live page stat. The perf kmem shows total allocation stat by default,
           but this option shows live (currently allocated) pages instead. (This option
           works with --page option only)

       --time=<start>,<stop>
           Only analyze samples within given time window: <start>,<stop>. Times have the
           format seconds.microseconds. If start is not given (i.e., time string is
           ,x.y) then analysis starts at the beginning of the file. If stop time is not
           given (i.e, time string is x.y,) then analysis goes to end of file.
	   只分析时间间隔内的事件.

SEE ALSO
       perf-record(1)

perf                                   03/29/2022                           PERF-KMEM(1)
```
