```
PERF-RECORD(1)                         perf Manual                        PERF-RECORD(1)

NAME
       perf-record - Run a command and record its profile into perf.data
                     运行命令，将信息搜集到perf.data 中

SYNOPSIS
       命令没有参数的写法。
       注意，此处执行命令意思是在命令退出之前进行统计信息记录，并不是只搜集该命令的记录信息。
       perf record [-e <EVENT> | --event=EVENT] [-a] <command>
       命令带参数的写法
       perf record [-e <EVENT> | --event=EVENT] [-a] — <command> [<options>]

DESCRIPTION
       This command runs a command and gathers a performance counter profile from it,
       into perf.data - without displaying anything.

       This file can then be inspected later on, using perf report.
       搜集信息，搜集信息之后可以通过perf report 查看.

OPTIONS
       <command>...
           Any command you can specify in a shell.
	   可以是任意在shell中执行的命令.

       -e, --event=
           Select the PMU event. Selection can be:
	   指定一个PMU事件，事件可以为:

           •   a symbolic event name (use perf list to list all events)
               一个符号事件名(通过perf list显示所有事件)

           •   a raw PMU event (eventsel+umask) in the form of rNNN where NNN is a
               hexadecimal event descriptor.
	       一个原始的PMU事件

           •   a symbolic or raw PMU event followed by an optional colon and a list of
               event modifiers, e.g., cpu-cycles:p. See the perf-list(1) man page for
               details on event modifiers.
	       一个符号或者原始的PMU事件，可以通过一个紧跟着的冒号+修改符修改，比如cpu-cycles:p.
	       详细信息查看perf-list(1).

           •   a symbolically formed PMU event like pmu/param1=0x3,param2/ where param1,
               param2, etc are defined as formats for the PMU in
	       符号形式的PMU事件可以加参数，参数在下边定义:
               /sys/bus/event_source/devices/<pmu>/format/*.

           •   a symbolically formed event like pmu/config=M,config1=N,config3=K/

                   where M, N, K are numbers (in decimal, hex, octal format). Acceptable
                   values for each of 'config', 'config1' and 'config2' are defined by
                   corresponding entries in /sys/bus/event_source/devices/<pmu>/format/*
                   param1 and param2 are defined as formats for the PMU in:
                   /sys/bus/event_source/devices/<pmu>/format/*

                   There are also some parameters which are not defined in .../<pmu>/format/*.
                   These params can be used to overload default config values per event.
                   Here are some common parameters:
                   - 'period': Set event sampling period
		               设置事件采样间隔
                   - 'freq': Set event sampling frequency
		             设置事件采样频率
                   - 'time': Disable/enable time stamping. Acceptable values are 1 for
                             enabling time stamping. 0 for disabling time stamping.
                             The default is 1.
			     禁止/使能时间采样
                   - 'call-graph': Disable/enable callgraph. Acceptable str are "fp" for
                                  FP mode, "dwarf" for DWARF mode, "lbr" for LBR mode and
                                  "no" for disable callgraph.
                   - 'stack-size': user stack size for dwarf mode
                   - 'name' : User defined event name. Single quotes (') may be used to
                             escape symbols in the name from parsing by shell and tool
                             like this: name=\'CPU_CLK_UNHALTED.THREAD:cmask=0x1\'.
                   - 'aux-output': Generate AUX records instead of events. This requires
                                   that an AUX area event is also provided.

                   See the linkperf:perf-list[1] man page for more parameters.

                   Note: If user explicitly sets options which conflict with the params,
                   the value set by the parameters will be overridden.

                   Also not defined in .../<pmu>/format/* are PMU driver specific
                   configuration parameters.  Any configuration parameter preceded by
                   the letter '@' is not interpreted in user space and sent down directly
                   to the PMU driver.  For example:

                   perf record -e some_event/@cfg1,@cfg2=config/ ...

                   will see 'cfg1' and 'cfg2=config' pushed to the PMU driver associated
                   with the event for further processing.  There is no restriction on
                   what the configuration parameters are, as long as their semantic is
                   understood and supported by the PMU driver.

           •   a hardware breakpoint event in the form of \mem:addr[/len][:access] where
               addr is the address in memory you want to break in. Access is the memory
               access type (read, write, execute) it can be passed as follows:
               \mem:addr[:[r][w][x]]. len is the range, number of bytes from specified
               addr, which the breakpoint will cover. If you want to profile read-write
               accesses in 0x1000, just set mem:0x1000:rw. If you want to profile write
               accesses in [0x1000~1008), just set mem:0x1000/8:w.

           •   a BPF source file (ending in .c) or a precompiled object file (ending in
               .o) selects one or more BPF events. The BPF program can attach to various
               perf events based on the ELF section names.

                   When processing a '.c' file, perf searches an installed LLVM to compile it
                   into an object file first. Optional clang options can be passed via the
                   '--clang-opt' command line option, e.g.:

                   perf record --clang-opt "-DLINUX_VERSION_CODE=0x50000" \
                               -e tests/bpf-script-example.c

                   Note: '--clang-opt' must be placed before '--event/-e'.

           •   a group of events surrounded by a pair of brace ("{event1,event2,...}").
               Each event is separated by commas and the group should be quoted to
               prevent the shell interpretation. You also need to use --group on "perf
               report" to view group events together.

       --filter=<filter>
           Event filter. This option should follow an event selector (-e) which selects
           either tracepoint event(s) or a hardware trace PMU (e.g. Intel PT or CoreSight).
	   事件过滤，过滤不必要的事件，需要跟在是-e 事件选择器之后.

           •   tracepoint filters

                   In the case of tracepoints, multiple '--filter' options are combined
                   using '&&'.

           •   address filters

                   A hardware trace PMU advertises its ability to accept a number of
                   address filters by specifying a non-zero value in
                   /sys/bus/event_source/devices/<pmu>/nr_addr_filters.

                   Address filters have the format:

                   filter|start|stop|tracestop <start> [/ <size>] [@<file name>]

                   Where:
                   - 'filter': defines a region that will be traced.
                   - 'start': defines an address at which tracing will begin.
                   - 'stop': defines an address at which tracing will stop.
                   - 'tracestop': defines a region in which tracing will stop.

                   <file name> is the name of the object file, <start> is the offset to the
                   code to trace in that file, and <size> is the size of the region to
                   trace. 'start' and 'stop' filters need not specify a <size>.

                   If no object file is specified then the kernel is assumed, in which case
                   the start address must be a current kernel memory address.

                   <start> can also be specified by providing the name of a symbol. If the
                   symbol name is not unique, it can be disambiguated by inserting #n where
                   'n' selects the n'th symbol in address order. Alternately #0, #g or #G
                   select only a global symbol. <size> can also be specified by providing
                   the name of a symbol, in which case the size is calculated to the end
                   of that symbol. For 'filter' and 'tracestop' filters, if <size> is
                   omitted and <start> is a symbol, then the size is calculated to the end
                   of that symbol.

                   If <size> is omitted and <start> is '*', then the start and size will
                   be calculated from the first and last symbols, i.e. to trace the whole
                   file.

                   If symbol names (or '*') are provided, they must be surrounded by white
                   space.

                   The filter passed to the kernel is not necessarily the same as entered.
                   To see the filter that is passed, use the -v option.

                   The kernel may not be able to configure a trace region if it is not
                   within a single mapping.  MMAP events (or /proc/<pid>/maps) can be
                   examined to determine if that is a possibility.

                   Multiple filters can be separated with space or comma.

       --exclude-perf
           Don’t record events issued by perf itself. This option should follow an event
           selector (-e) which selects tracepoint event(s). It adds a filter expression
           common_pid != $PERFPID to filters. If other --filter exists, the new filter
           expression will be combined with them by &&.
	   不追踪perf 发出的事件

       -a, --all-cpus
           System-wide collection from all CPUs (default if no target is specified).
	   搜集系统范围内所有CPU的信息.

       -p, --pid=
           Record events on existing process ID (comma separated list).

       -t, --tid=
           Record events on existing thread ID (comma separated list). This option also
           disables inheritance by default. Enable it by adding --inherit.

       -u, --uid=
           Record events in threads owned by uid. Name or number.

       -r, --realtime=
           Collect data with this RT SCHED_FIFO priority.
	   以实时进程优先级统计信息

       --no-buffering
           Collect data without buffering.

       -c, --count=
           Event period to sample.
	   事件采样时间间隔

       -o, --output=
           Output file name.
	   输出文件名

       -i, --no-inherit
           Child tasks do not inherit counters.
	   TOOD: 这个的用处？

       -F, --freq=
           Profile at this frequency. Use max to use the currently maximum allowed
           frequency, i.e. the value in the kernel.perf_event_max_sample_rate sysctl.
           Will throttle down to the currently maximum allowed frequency. See
           --strict-freq.

       --strict-freq
           Fail if the specified frequency can’t be used.

       -m, --mmap-pages=
           Number of mmap data pages (must be a power of two) or size specification with
           appended unit character - B/K/M/G. The size is rounded up to have nearest
           pages power of two value. Also, by adding a comma, the number of mmap pages
           for AUX area tracing can be specified.

       --group
           Put all events in a single event group. This precedes the --event option and
           remains only for backward compatibility. See --event.
	   仅仅是向后兼容.

       -g
           Enables call-graph (stack chain/backtrace) recording.

       --call-graph
           Setup and enable call-graph (stack chain/backtrace) recording, implies -g.
           Default is "fp".

               Allows specifying "fp" (frame pointer) or "dwarf"
               (DWARF's CFI - Call Frame Information) or "lbr"
               (Hardware Last Branch Record facility) as the method to collect
               the information used to show the call graphs.
	       允许指定"fp"、"dwarf"、"lbr" 方法搜集调用栈信息

               In some systems, where binaries are build with gcc
               --fomit-frame-pointer, using the "fp" method will produce bogus
               call graphs, using "dwarf", if available (perf tools linked to
               the libunwind or libdw library) should be used instead.
               Using the "lbr" method doesn't require any compiler options. It
               will produce call graphs from the hardware LBR registers. The
               main limitation is that it is only available on new Intel
               platforms, such as Haswell. It can only get user call chain. It
               doesn't work with branch stack sampling at the same time.

               When "dwarf" recording is used, perf also records (user) stack dump
               when sampled.  Default size of the stack dump is 8192 (bytes).
               User can change the size by passing the size after comma like
               "--call-graph dwarf,4096".

       -q, --quiet
           Don’t print any message, useful for scripting.

       -v, --verbose
           Be more verbose (show counter open errors, etc).

       -s, --stat
           Record per-thread event counts. Use it with perf report -T to see the values.

       -d, --data
           Record the sample virtual addresses.

       --phys-data
           Record the sample physical addresses.

       -T, --timestamp
           Record the sample timestamps. Use it with perf report -D to see the
           timestamps, for instance.
	   记录时间戳信息，通过 perf report -D 查看时间戳.

       -P, --period
           Record the sample period.

       --sample-cpu
           Record the sample cpu.

       -n, --no-samples
           Don’t sample.

       -R, --raw-samples
           Collect raw sample records from all opened counters (default for tracepoint counters).

       -C, --cpu
           Collect samples only on the list of CPUs provided. Multiple CPUs can be
           provided as a comma-separated list with no space: 0,1. Ranges of CPUs are
           specified with -: 0-2. In per-thread mode with inheritance mode on (default),
           samples are captured only when the thread executes on the designated CPUs.
           Default is to monitor all CPUs.

       -B, --no-buildid
           Do not save the build ids of binaries in the perf.data files. This skips post
           processing after recording, which sometimes makes the final step in the
           recording process to take a long time, as it needs to process all events
           looking for mmap records. The downside is that it can misresolve symbols if
           the workload binaries used when recording get locally rebuilt or upgraded,
           because the only key available in this case is the pathname. You can also set
           the "record.build-id" config variable to 'skip to have this behaviour
           permanently.
	   不在perf.data 中保存二进制数据，这步通常会在最后进行，占用很长一段时间.
	   副作用就是如果保存之后二进制文件改变了，可能会导致解析的符号不对.

       -N, --no-buildid-cache
           Do not update the buildid cache. This saves some overhead in situations where
           the information in the perf.data file (which includes buildids) is
           sufficient. You can also set the "record.build-id" config variable to
           no-cache to have the same effect.

       -G name,..., --cgroup name,...
           monitor only in the container (cgroup) called "name". This option is
           available only in per-cpu mode. The cgroup filesystem must be mounted. All
           threads belonging to container "name" are monitored when they run on the
           monitored CPUs. Multiple cgroups can be provided. Each cgroup is applied to
           the corresponding event, i.e., first cgroup to first event, second cgroup to
           second event and so on. It is possible to provide an empty cgroup (monitor
           all the time) using, e.g., -G foo,,bar. Cgroups must have corresponding
           events, i.e., they always refer to events defined earlier on the command
           line. If the user wants to track multiple events for a specific cgroup, the
           user can use -e e1 -e e2 -G foo,foo or just use -e e1 -e e2 -G foo.

       If wanting to monitor, say, cycles for a cgroup and also for system wide, this
       command line can be used: perf stat -e cycles -G cgroup_name -a -e cycles.

       -b, --branch-any
           Enable taken branch stack sampling. Any type of taken branch may be sampled.
           This is a shortcut for --branch-filter any. See --branch-filter for more
           infos.

       -j, --branch-filter
           Enable taken branch stack sampling. Each sample captures a series of
           consecutive taken branches. The number of branches captured with each sample
           depends on the underlying hardware, the type of branches of interest, and the
           executed code. It is possible to select the types of branches captured by
           enabling filters. The following filters are defined:

           •   any: any type of branches
	            任意类型的分支

           •   any_call: any function call or system call
	                 函数调用或者系统调用

           •   any_ret: any function return or system call return
	                函数返回或者系统调用返回

           •   ind_call: any indirect branch
	                 任意间接分支

           •   call: direct calls, including far (to/from kernel) calls
	             直接调用

           •   u: only when the branch target is at the user level
	          分支目标在用户态

           •   k: only when the branch target is in the kernel
	          分支目标在内核态

           •   hv: only when the target is at the hypervisor level
	           分支目标在虚拟机管理器层

           •   in_tx: only when the target is in a hardware transaction
	              目标处于硬件事务中时

           •   no_tx: only when the target is not in a hardware transaction
	              目标没处于硬件事务中

           •   abort_tx: only when the target is a hardware transaction abort

           •   cond: conditional branches
	             条件分支

           •   save_type: save branch type during sampling in case binary is not
               available later

           The option requires at least one branch type among any, any_call, any_ret,
           ind_call, cond.
	   The privilege levels may be omitted, in which case, the
           privilege levels of the associated event are applied to the branch filter.
           Both kernel (k) and hypervisor (hv) privilege levels are subject to
           permissions. When sampling on multiple events, branch stack sampling is
           enabled for all the sampling events. The sampled branch type is the same for
           all events. The various filters must be specified as a comma separated list:
           --branch-filter any_ret,u,k Note that this feature may not be available on
           all processors.

       --weight
           Enable weightened sampling. An additional weight is recorded per sample and
           can be displayed with the weight and local_weight sort keys. This currently
           works for TSX abort events and some memory events in precise mode on modern
           Intel CPUs.

       --namespaces
           Record events of type PERF_RECORD_NAMESPACES.

       --transaction
           Record transaction flags for transaction related events.

       --per-thread
           Use per-thread mmaps. By default per-cpu mmaps are created. This option
           overrides that and uses per-thread mmaps. A side-effect of that is that
           inheritance is automatically disabled. --per-thread is ignored with a warning
           if combined with -a or -C options.
	   使用线程mmaps.

       -D, --delay=
           After starting the program, wait msecs before measuring. This is useful to
           filter out the startup phase of the program, which is often very different.

       -I, --intr-regs
           Capture machine state (registers) at interrupt, i.e., on counter overflows
           for each sample. List of captured registers depends on the architecture. This
           option is off by default. It is possible to select the registers to sample
           using their symbolic names, e.g. on x86, ax, si. To list the available
           registers use --intr-regs=\?. To name registers, pass a comma separated list
           such as --intr-regs=ax,bx. The list of register is architecture dependent.

       --user-regs
           Similar to -I, but capture user registers at sample time. To list the
           available user registers use --user-regs=\?.

       --running-time
           Record running and enabled time for read events (:S)
	   TODO: 没理解?

       -k, --clockid
           Sets the clock id to use for the various time fields in the perf_event_type
           records. See clock_gettime(). In particular CLOCK_MONOTONIC and
           CLOCK_MONOTONIC_RAW are supported, some events might also allow
           CLOCK_BOOTTIME, CLOCK_REALTIME and CLOCK_TAI.

       -S, --snapshot
           Select AUX area tracing Snapshot Mode. This option is valid only with an AUX
           area tracing event. Optionally, certain snapshot capturing parameters can be
           specified in a string that follows this option: e: take one last snapshot on
           exit; guarantees that there is at least one snapshot in the output file;
           <size>: if the PMU supports this, specify the desired snapshot size.
	   TODO: AUX 是什么?

       In Snapshot Mode trace data is captured only when signal SIGUSR2 is received and
       on exit if the above e option is given.

       --proc-map-timeout
           When processing pre-existing threads /proc/XXX/mmap, it may take a long time,
           because the file may be huge. A time out is needed in such cases. This option
           sets the time out limit. The default value is 500 ms.

       --switch-events
           Record context switch events i.e. events of type PERF_RECORD_SWITCH or
           PERF_RECORD_SWITCH_CPU_WIDE.

       --clang-path=PATH
           Path to clang binary to use for compiling BPF scriptlets. (enabled when BPF
           support is on)

       --clang-opt=OPTIONS
           Options passed to clang when compiling BPF scriptlets. (enabled when BPF
           support is on)

       --vmlinux=PATH
           Specify vmlinux path which has debuginfo. (enabled when BPF prologue is on)

       --buildid-all
           Record build-id of all DSOs regardless whether it’s actually hit or not.

       --aio[=n]
           Use <n> control blocks in asynchronous (Posix AIO) trace writing mode
           (default: 1, max: 4). Asynchronous mode is supported only when linking Perf
           tool with libc library providing implementation for Posix AIO API.

       --affinity=mode
           Set affinity mask of trace reading thread according to the policy defined by
           mode value:
	   	node - thread affinity mask is set to NUMA node cpu mask of the processed mmap buffer
                cpu - thread affinity mask is set to cpu of the processed mmap buffer

       --mmap-flush=number
           Specify minimal number of bytes that is extracted from mmap data pages and
           processed for output. One can specify the number using B/K/M/G suffixes.

       The maximal allowed value is a quarter of the size of mmaped data pages.

       The default option value is 1 byte which means that every time that the output
       writing thread finds some new data in the mmaped buffer the data is extracted,
       possibly compressed (-z) and written to the output, perf.data or pipe.

       Larger data chunks are compressed more effectively in comparison to smaller
       chunks so extraction of larger chunks from the mmap data pages is preferable from
       the perspective of output size reduction.

       Also at some cases executing less output write syscalls with bigger data size can
       take less time than executing more output write syscalls with smaller data size
       thus lowering runtime profiling overhead.

       -z, --compression-level[=n]
           Produce compressed trace using specified level n (default: 1 - fastest
           compression, 22 - smallest trace)

       --all-kernel
           Configure all used events to run in kernel space.

       --all-user
           Configure all used events to run in user space.

       --kernel-callchains
           Collect callchains only from kernel space. I.e. this option sets
           perf_event_attr.exclude_callchain_user to 1.

       --user-callchains
           Collect callchains only from user space. I.e. this option sets
           perf_event_attr.exclude_callchain_kernel to 1.

       Don’t use both --kernel-callchains and --user-callchains at the same time or no
       callchains will be collected.

       --timestamp-filename Append timestamp to output file name.

       --timestamp-boundary
           Record timestamp boundary (time of first/last samples).

       --switch-output[=mode]
           Generate multiple perf.data files, timestamp prefixed, switching to a new one
           based on mode value: "signal" - when receiving a SIGUSR2 (default value) or
           <size> - when reaching the size threshold, size is expected to be a number
           with appended unit character - B/K/M/G <time> - when reaching the time
           threshold, size is expected to be a number with appended unit character -
           s/m/h/d

               Note: the precision of  the size  threshold  hugely depends
               on your configuration  - the number and size of  your  ring
               buffers (-m). It is generally more precise for higher sizes
               (like >5M), for lower values expect different sizes.

       A possible use case is to, given an external event, slice the perf.data file that
       gets then processed, possibly via a perf script, to decide if that particular
       perf.data snapshot should be kept or not.

       Implies --timestamp-filename, --no-buildid and --no-buildid-cache. The reason for
       the latter two is to reduce the data file switching overhead. You can still
       switch them on with:

           --switch-output --no-no-buildid  --no-no-buildid-cache

       --switch-max-files=N
           When rotating perf.data with --switch-output, only keep N files.

       --dry-run
           Parse options then exit. --dry-run can be used to detect errors in cmdline
           options.
	   尝试运行然后退出.

       perf record --dry-run -e can act as a BPF script compiler if llvm.dump-obj in
       config file is set to true.

       --tail-synthesize
           Instead of collecting non-sample events (for example, fork, comm, mmap) at
           the beginning of record, collect them during finalizing an output file. The
           collected non-sample events reflects the status of the system when record is
           finished.

       --overwrite
           Makes all events use an overwritable ring buffer. An overwritable ring buffer
           works like a flight recorder: when it gets full, the kernel will overwrite
           the oldest records, that thus will never make it to the perf.data file.

       When --overwrite and --switch-output are used perf records and drops events until
       it receives a signal, meaning that something unusual was detected that warrants
       taking a snapshot of the most current events, those fitting in the ring buffer at
       that moment.

       overwrite attribute can also be set or canceled for an event using config terms.
       For example: cycles/overwrite/ and instructions/no-overwrite/.

       Implies --tail-synthesize.

SEE ALSO
       perf-stat(1), perf-list(1)

perf                                   03/29/2022                         PERF-RECORD(1)
```
