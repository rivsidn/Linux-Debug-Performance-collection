```
NETSTAT(8)                 Linux System Administrator's Manual                NETSTAT(8)

NAME
       netstat  -  Print network connections, routing tables, interface statistics,
                   masquerade connections, and multicast memberships
		   输出网络连接，路由表，接口统计，伪装链接，多播等信息


SYNOPSIS
       此处的语法已经列出了命令支持的子命令以及子命令支持的选项，查阅选项的描述即可以明确
       命令如何使用。

       输出网络链接信息
       netstat [address_family_options] [--tcp|-t] [--udp|-u] [--udplite|-U] [--sctp|-S]
       [--raw|-w]  [--l2cap|-2] [--rfcomm|-f] [--listening|-l] [--all|-a] [--numeric|-n]
       [--numeric-hosts]     [--numeric-ports]     [--numeric-users]     [--symbolic|-N]
       [--extend|-e[--extend|-e]] [--timers|-o] [--program|-p] [--verbose|-v]
       [--continuous|-c] [--wide|-W]

       输出路由信息
       netstat {--route|-r} [address_family_options] [--extend|-e[--extend|-e]]
       [--verbose|-v]  [--numeric|-n]  [--numeric-hosts]  [--numeric-ports]
       [--numeric-users] [--continuous|-c]

       输出接口信息
       netstat {--interfaces|-i}  [--all|-a]  [--extend|-e[--extend|-e]]  [--verbose|-v]
       [--program|-p]  [--numeric|-n]  [--numeric-hosts]  [--numeric-ports]
       [--numericusers] [--continuous|-c]

       输出多播组信息
       netstat   {--groups|-g}   [--numeric|-n]   [--numeric-hosts]    [--numeric-ports]
       [--numeric-users] [--continuous|-c]

       输出伪装链接信息
       netstat    {--masquerade|-M}   [--extend|-e]   [--numeric|-n]   [--numeric-hosts]
       [--numeric-ports] [--numeric-users] [--continuous|-c]

       输出统计信息
       netstat  {--statistics|-s}  [--tcp|-t]  [--udp|-u]   [--udplite|-U]   [--sctp|-S]
       [--raw|-w]

       输出当前版本信息
       netstat {--version|-V}

       输出帮助信息
       netstat {--help|-h}

       address_family_options:
       地主族选项:

       [-4|--inet]  [-6|--inet6]
       [--protocol={inet,inet6,unix,ipx,ax25,netrom,ddp,bluetooth, ...  }  ]
       [--unix|-x]  [--inet|--ip|--tcpip]  [--ax25]  [--x25]  [--rose]
       [--ash] [--bluetooth] [--ipx] [--netrom] [--ddp|--appletalk] [--econet|--ec]

NOTES
       This program is mostly obsolete.  Replacement for netstat is ss.  Replacement for
       netstat -r is ip route.  Replacement for netstat -i is ip -s  link.   Replacement
       for netstat -g is ip maddr.
       该程序已经过时，已经由于下边几个程序替代了。

DESCRIPTION(描述)
       Netstat  prints  information  about  the Linux networking subsystem.  The type of
       information printed is controlled by the first argument, as follows:

   (none)
       By default, netstat displays a list of open sockets.  If you  don't  specify  any
       address families, then the active sockets of all configured address families will
       be printed.
       输出开启的socket信息，如果没有地址族，会输出所有地址族使能的socket。

   --route, -r
       Display the kernel routing tables. See the description in route(8)  for  details.
       netstat -r and route -e produce the same output.

   --groups, -g
       Display multicast group membership information for IPv4 and IPv6.

   --interfaces, -i
       Display a table of all network interfaces.

   --masquerade, -M
       Display a list of masqueraded connections.

   --statistics, -s
       Display summary statistics for each protocol.
       显示统计信息

OPTIONS
   --verbose, -v
       Tell  the  user  what  is going on by being verbose. Especially print some useful
       information about unconfigured address families.

   --wide, -W
       Do not truncate IP addresses by using output as wide as needed. This is  optional
       for now to not break existing scripts.

   --numeric, -n
       Show  numerical  addresses  instead of trying to determine symbolic host, port or
       user names.
       显示IP地址而不是符号信息

   --numeric-hosts
       shows numerical host addresses but does not affect the resolution of port or user
       names.
       IP地址不通过符号信息

   --numeric-ports
       shows  numerical  port numbers but does not affect the resolution of host or user
       names.
       端口号不通过符号显示

   --numeric-users
       shows numerical user IDs but does not affect  the  resolution  of  host  or  port
       names.
       用户不通过符号显示

   --protocol=family, -A
       Specifies  the address families (perhaps better described as low level protocols)
       for which connections are to be shown.  family is a comma (',') separated list of
       address  family  keywords like inet, inet6, unix, ipx, ax25, netrom, econet, ddp,
       and bluetooth.  This has the same effect  as  using  the  --inet|-4,  --inet6|-6,
       --unix|-x, --ipx, --ax25, --netrom, --ddp, and --bluetooth options.
       指定底层协议

       The  address  family inet (Iv4) includes raw, udp, udplite and tcp protocol sock‐
       ets.

       The address family bluetooth (Iv4) includes l2cap and rfcomm protocol sockets.

   -c, --continuous
       This will cause netstat to print the selected information every  second  continu‐
       ously.
       输出选中的信息，每秒输出一次.

   -e, --extend
       Display additional information.  Use this option twice for maximum detail.
       输出附加信息，可以两次使用，输出更多细节信息.

   -o, --timers
       Include information related to networking timers.
       输出网络定时器信息

   -p, --program
       Show the PID and name of the program to which each socket belongs.
       显示每个scoket对应的PID和程序名.

   -l, --listening
       Show only listening sockets.  (These are omitted by default.)
       只显示正在监听的socket，默认是不显示的.

   -a, --all
       Show  both  listening  and  non-listening sockets.  With the --interfaces option,
       show interfaces that are not up
       显示所有监听的、没监听的socket.

   -F
       Print routing information from the FIB.  (This is the default.)
       输出FIB的路由表信息

   -C
       Print routing information from the route cache.
       输出路由缓存的路由信息

OUTPUT(输出信息解释)
   Active Internet connections (TCP, UDP, UDPLite, raw)
   Proto
       The protocol (tcp, udp, udpl, raw) used by the socket.
       socket的协议类型

   Recv-Q
       Established: The count of bytes not copied by the user program connected to this socket.
       Listening: Since Kernel 2.6.18 this column contains the current syn backlog.

   Send-Q
       Established: The count of bytes not acknowledged by the remote host.
       Listening: Since Kernel 2.6.18 this column contains the maximum size of the syn backlog.

   Local Address
       Address  and  port  number  of the local end of the socket.  Unless the --numeric
       (-n) option is specified, the socket address is resolved to  its  canonical  host
       name  (FQDN),  and  the  port number is translated into the corresponding service
       name.

   Foreign Address
       Address and port number of the remote end of the  socket.   Analogous  to  "Local
       Address".

   State
       The  state  of  the  socket. Since there are no states in raw mode and usually no
       states used in UDP and UDPLite, this column may be left blank. Normally this  can
       be one of several values:

       ESTABLISHED
              The socket has an established connection.

       SYN_SENT
              The socket is actively attempting to establish a connection.
	      正积极尝试建立链接.

       SYN_RECV
              A connection request has been received from the network.
	      接收到了一个链接请求.

       FIN_WAIT1
              The socket is closed, and the connection is shutting down.

       FIN_WAIT2
              Connection  is  closed,  and the socket is waiting for a shutdown from the
              remote end.

       TIME_WAIT
              The socket is waiting after close to handle packets still in the network.

       CLOSE  The socket is not being used.

       CLOSE_WAIT
              The remote end has shut down, waiting for the socket to close.

       LAST_ACK
              The remote end has shut down,  and  the  socket  is  closed.  Waiting  for
              acknowledgement.

       LISTEN The  socket  is  listening for incoming connections.  Such sockets are not
              included in the output unless you specify the --listening  (-l)  or  --all
              (-a) option.
	      监听状态的socket，此类的socket只有在指定了-l 或者-a 选项的时候才会显示.

       CLOSING
              Both sockets are shut down but we still don't have all our data sent.
	      两个套接字都已经关闭，但是仍然没有发送所有数据.

       UNKNOWN
              The state of the socket is unknown.

   User
       The username or the user id (UID) of the owner of the socket.
       拥有该socket 的用户.

   PID/Program name
       Slash-separated pair of the process id (PID) and process name of the process that
       owns the socket.  --program causes this column to be  included.   You  will  also
       need superuser privileges to see this information on sockets you don't own.  This
       identification information is not yet available for IPX sockets.

   Timer
       (this needs to be written)

   Active UNIX domain Sockets
   Proto
       The protocol (usually unix) used by the socket.

   RefCnt
       The reference count (i.e. attached processes via this socket).
       引用计数.

   Flags
       The flags displayed  is  SO_ACCEPTON  (displayed  as  ACC),  SO_WAITDATA  (W)  or
       SO_NOSPACE (N).  SO_ACCECPTON is used on unconnected sockets if their correspond‐
       ing processes are waiting for a connect request. The other flags are not of  nor‐
       mal interest.

   Type
       There are several types of socket access:

       SOCK_DGRAM
              The socket is used in Datagram (connectionless) mode.

       SOCK_STREAM
              This is a stream (connection) socket.

       SOCK_RAW
              The socket is used as a raw socket.

       SOCK_RDM
              This one serves reliably-delivered messages.

       SOCK_SEQPACKET
              This is a sequential packet socket.

       SOCK_PACKET
              Raw interface access socket.

       UNKNOWN
              Who ever knows what the future will bring us - just fill in here :-)

   State
       This field will contain one of the following Keywords:

       FREE   The socket is not allocated

       LISTENING
              The  socket  is listening for a connection request.  Such sockets are only
              included in the output if you specify the --listening (-l) or  --all  (-a)
              option.

       CONNECTING
              The socket is about to establish a connection.

       CONNECTED
              The socket is connected.

       DISCONNECTING
              The socket is disconnecting.

       (empty)
              The socket is not connected to another one.

       UNKNOWN
              This state should never happen.

   PID/Program name
       Process  ID (PID) and process name of the process that has the socket open.  More
       info available in Active Internet connections section written above.

   Path
       This is the path name as  which  the  corresponding  processes  attached  to  the
       socket.

   Active IPX sockets
       (this needs to be done by somebody who knows it)

   Active NET/ROM sockets
       (this needs to be done by somebody who knows it)

   Active AX.25 sockets
       (this needs to be done by somebody who knows it)

FILES
       /etc/services -- The services translation file
                        服务翻译文件

       /proc -- Mount point for the proc filesystem, which gives access to kernel status
       information via the following files.
       通过/proc 文件可以查看到内核的状态信息.

       /proc/net/dev -- device information
                        设备信息

       /proc/net/raw -- raw socket information

       /proc/net/tcp -- TCP socket information

       /proc/net/udp -- UDP socket information

       /proc/net/udplite -- UDPLite socket information

       /proc/net/igmp -- IGMP multicast information

       /proc/net/unix -- Unix domain socket information

       /proc/net/ipx -- IPX socket information

       /proc/net/ax25 -- AX25 socket information

       /proc/net/appletalk -- DDP (appletalk) socket information

       /proc/net/nr -- NET/ROM socket information

       /proc/net/route -- IP routing information

       /proc/net/ax25_route -- AX25 routing information

       /proc/net/ipx_route -- IPX routing information

       /proc/net/nr_nodes -- NET/ROM nodelist

       /proc/net/nr_neigh -- NET/ROM neighbours

       /proc/net/ip_masquerade -- masqueraded connections

       /sys/kernel/debug/bluetooth/l2cap -- Bluetooth L2CAP information

       /sys/kernel/debug/bluetooth/rfcomm -- Bluetooth serial connections

       /proc/net/snmp -- statistics

SEE ALSO
       route(8), ifconfig(8), iptables(8), proc(5) ss(8) ip(8)

BUGS
       Occasionally strange information may appear if a socket changes as it is  viewed.
       This is unlikely to occur.

AUTHORS
       The    netstat    user    interface    was    written    by    Fred    Baumgarten
       <dc6iq@insu1.etec.uni-karlsruhe.de>,  the  man  page  basically  by  Matt   Welsh
       <mdw@tc.cornell.edu>.  It  was  updated by Alan Cox <Alan.Cox@linux.org>, updated
       again by Tuan Hoang <tqhoang@bigfoot.com>. The man page and the command  included
       in the net-tools package is totally rewritten by Bernd Eckenfels <ecki@linux.de>.
       UDPLite options were added by Brian Micek <bmicek@gmail.com>

net-tools                              2014-10-07                             NETSTAT(8)
```
