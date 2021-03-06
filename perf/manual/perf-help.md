PERF-HELP(1)                           perf Manual                          PERF-HELP(1)

NAME
       perf-help - display help information about perf

SYNOPSIS
       perf help [-a|--all] [COMMAND]

DESCRIPTION
       With no options and no COMMAND given, the synopsis of the perf command and a list
       of the most commonly used perf commands are printed on the standard output.

       If the option --all or -a is given, then all available commands are printed on
       the standard output.

       If a perf command is named, a manual page for that command is brought up. The man
       program is used by default for this purpose, but this can be overridden by other
       options or configuration variables.

       Note that perf --help ... is identical to perf help ... because the former is
       internally converted into the latter.

OPTIONS
       -a, --all
           Prints all the available commands on the standard output. This option
           supersedes any other option.

PERF
       Part of the perf(1) suite

perf                                   03/29/2022                           PERF-HELP(1)
