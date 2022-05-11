PERF-BUILDID-LIST(1)                   perf Manual                  PERF-BUILDID-LIST(1)

NAME
       perf-buildid-list - List the buildids in a perf.data file

SYNOPSIS
       perf buildid-list <options>

DESCRIPTION
       This command displays the buildids found in a perf.data file, so that other tools
       can be used to fetch packages with matching symbol tables for use by perf report.

       It can also be used to show the build id of the running kernel or in an ELF file
       using -i/--input.

OPTIONS
       -H, --with-hits
           Show only DSOs with hits.

       -i, --input=
           Input file name. (default: perf.data unless stdin is a fifo)

       -f, --force
           Don’t do ownership validation.

       -k, --kernel
           Show running kernel build id.

       -v, --verbose
           Be more verbose.

SEE ALSO
       perf-record(1), perf-top(1), perf-report(1)

perf                                   03/29/2022                   PERF-BUILDID-LIST(1)