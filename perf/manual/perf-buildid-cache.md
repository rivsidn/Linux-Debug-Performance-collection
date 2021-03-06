PERF-BUILDID-CACHE(1)                  perf Manual                 PERF-BUILDID-CACHE(1)

NAME
       perf-buildid-cache - Manage build-id cache.
                            管理build-id 缓存信息

SYNOPSIS
       perf buildid-cache <options>

DESCRIPTION
       This command manages the build-id cache. It can add, remove, update and purge
       files to/from the cache. In the future it should as well set upper limits for the
       space used by the cache, etc. This also scans the target binary for SDT
       (Statically Defined Tracing) and record it along with the buildid-cache, which
       will be used by perf-probe. For more details, see perf-probe(1).
       管理缓存信息，可以用于将文件从缓存中添加、删除、更新、清除等。

OPTIONS
       -a, --add=
           Add specified file to the cache.
	   添加特定文件到缓存中.

       -f, --force
           Don’t complain, do it.
	   不要抱怨，干就完了.

       -k, --kcore
           Add specified kcore file to the cache. For the current host that is
           /proc/kcore which requires root permissions to read. Be aware that running
           perf buildid-cache as root may update root’s build-id cache not the user’s.
           Use the -v option to see where the file is created. Note that the copied file
           contains only code sections not the whole core image. Note also that files
           "kallsyms" and "modules" must also be in the same directory and are also
           copied. All 3 files are created with read permissions for root only. kcore
           will not be added if there is already a kcore in the cache (with the same
           build-id) that has the same modules at the same addresses. Use the -v option
           to see if a copy of kcore is actually made.

       -r, --remove=
           Remove a cached binary which has same build-id of specified file from the
           cache.
	   删除文件

       -p, --purge=
           Purge all cached binaries including older caches which have specified path
           from the cache.

       -P, --purge-all
           Purge all cached binaries. This will flush out entire cache.
	   清楚所有缓存二进制文件，该命令会刷新整个缓存.

       -M, --missing=
           List missing build ids in the cache for the specified file.

       -u, --update=
           Update specified file of the cache. Note that this doesn’t remove older
           entires since those may be still needed for annotating old (or remote)
           perf.data. Only if there is already a cache which has exactly same build-id,
           that is replaced by new one. It can be used to update kallsyms and kernel dso
           to vmlinux in order to support annotation.

       -l, --list
           List all valid binaries from cache.

       -v, --verbose
           Be more verbose.

       --target-ns=PID: Obtain mount namespace information from the target pid. This is
       used when creating a uprobe for a process that resides in a different mount
       namespace from the perf(1) utility.

SEE ALSO
       perf-record(1), perf-report(1), perf-buildid-list(1)

perf                                   03/29/2022                  PERF-BUILDID-CACHE(1)
