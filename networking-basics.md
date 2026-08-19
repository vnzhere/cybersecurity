ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 60:45:bd:72:e5:e0 brd ff:ff:ff:ff:ff:ff
    inet 10.0.13.22/16 metric 100 brd 10.0.255.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::6245:bdff:fe72:e5e0/64 scope link 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:ba:88:56:1c brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever

     % ping google.com
PING google.com (192.178.134.139): 56 data bytes
Request timeout for icmp_seq 0
64 bytes from 192.178.134.139: icmp_seq=1 ttl=107 time=49.028 ms
64 bytes from 192.178.134.139: icmp_seq=2 ttl=107 time=49.110 ms
64 bytes from 192.178.134.139: icmp_seq=3 ttl=107 time=50.584 ms
64 bytes from 192.178.134.139: icmp_seq=4 ttl=107 time=49.480 ms
64 bytes from 192.178.134.139: icmp_seq=5 ttl=107 time=49.562 ms
64 bytes from 192.178.134.139: icmp_seq=6 ttl=107 time=48.386 ms
64 bytes from 192.178.134.139: icmp_seq=7 ttl=107 time=48.611 ms
64 bytes from 192.178.134.139: icmp_seq=8 ttl=107 time=49.245 ms
64 bytes from 192.178.134.139: icmp_seq=9 ttl=107 time=73.621 ms
64 bytes from 192.178.134.139: icmp_seq=10 ttl=107 time=70.100 ms
64 bytes from 192.178.134.139: icmp_seq=11 ttl=107 time=58.295 ms
64 bytes from 192.178.134.139: icmp_seq=12 ttl=107 time=49.254 ms
64 bytes from 192.178.134.139: icmp_seq=13 ttl=107 time=49.466 ms
64 bytes from 192.178.134.139: icmp_seq=14 ttl=107 time=47.514 ms
64 bytes from 192.178.134.139: icmp_seq=15 ttl=107 time=48.843 ms
64 bytes from 192.178.134.139: icmp_seq=16 ttl=107 time=49.535 ms
64 bytes from 192.178.134.139: icmp_seq=17 ttl=107 time=56.192 ms

traceroute google.com
traceroute: Warning: google.com has multiple addresses; using 192.178.134.138
traceroute to google.com (192.178.134.138), 64 hops max, 40 byte packets
 1  reliance.reliance (192.168.29.1)  3.190 ms  2.557 ms  1.809 ms
 2  10.96.136.1 (10.96.136.1)  5.611 ms  5.188 ms  8.480 ms
 3  172.16.26.1 (172.16.26.1)  8.645 ms
    172.16.18.1 (172.16.18.1)  7.664 ms  8.011 ms
 4  192.168.128.134 (192.168.128.134)  7.670 ms  12.258 ms  6.767 ms
 5  172.27.248.52 (172.27.248.52)  9.243 ms  16.015 ms  18.334 ms
 6  172.27.248.35 (172.27.248.35)  14.402 ms  5.675 ms  6.698 ms
 7  192.168.44.24 (192.168.44.24)  6.178 ms  7.790 ms  7.740 ms
 8  * * *
 9  * * *
10  * * *
11  * * *
12  * *^C

% nslookup google.com
Server:		2405:201:404f:70b4::c0a8:1d01
Address:	2405:201:404f:70b4::c0a8:1d01#53

Non-authoritative answer:
Name:	google.com
Address: 192.178.177.101
Name:	google.com
Address: 192.178.177.100
Name:	google.com
Address: 192.178.177.113
Name:	google.com
Address: 192.178.177.139
Name:	google.com
Address: 192.178.177.138
Name:	google.com
Address: 192.178.177.102
