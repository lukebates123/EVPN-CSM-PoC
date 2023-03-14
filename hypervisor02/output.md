
```bash
# ip r
default via 192.168.1.1 dev ens33 proto static 
10.20.20.1 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
10.30.30.1 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.1.0/24 dev ens33 proto kernel scope link src 192.168.1.93
192.168.1.0/24 dev CMN proto kernel scope link src 192.168.1.93
192.168.100.0/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.100.0/24 dev virbr1 proto kernel scope link src 192.168.100.1 linkdown 
192.168.100.2/31 nhid 37 via 192.168.200.6 dev ens37 proto ospf metric 20
192.168.100.4/31 nhid 39 via 192.168.200.4 dev ens38 proto ospf metric 20
192.168.100.6/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.100.8/31 nhid 37 via 192.168.200.6 dev ens37 proto ospf metric 20
192.168.100.10/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.100.12/31 nhid 39 via 192.168.200.4 dev ens38 proto ospf metric 20
192.168.100.14/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.100.24/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.100.26/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.200.0/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.200.2/31 nhid 62 proto ospf metric 20
        nexthop via 192.168.200.6 dev ens37 weight 1
        nexthop via 192.168.200.4 dev ens38 weight 1
192.168.200.4/31 dev ens38 proto kernel scope link src 192.168.200.5
192.168.200.6/31 dev ens37 proto kernel scope link src 192.168.200.7
```

```
# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet 10.10.10.1/32 brd 10.10.10.1 scope global lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel master CMN state UP group default qlen 1000
    link/ether 00:0c:29:6b:9e:d9 brd ff:ff:ff:ff:ff:ff
    altname enp2s1
    inet 192.168.1.93/24 brd 192.168.1.255 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe6b:9ed9/64 scope link
       valid_lft forever preferred_lft forever
3: ens37: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:6b:9e:e3 brd ff:ff:ff:ff:ff:ff
    altname enp2s5
    inet 192.168.200.7/31 brd 255.255.255.255 scope global ens37
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe6b:9ee3/64 scope link
       valid_lft forever preferred_lft forever
4: ens38: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:6b:9e:ed brd ff:ff:ff:ff:ff:ff
    altname enp2s6
    inet 192.168.200.5/31 brd 255.255.255.255 scope global ens38
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe6b:9eed/64 scope link
       valid_lft forever preferred_lft forever
5: NMN_BLUE: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master vrf-blue state UP group default qlen 1000
    link/ether aa:bb:cc:00:00:d2 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.1/24 brd 10.252.0.255 scope global NMN_BLUE
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe4b:1d46/64 scope link
       valid_lft forever preferred_lft forever
6: virbr1: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 52:54:00:2d:91:cc brd ff:ff:ff:ff:ff:ff
    inet 192.168.100.1/24 brd 192.168.100.255 scope global virbr1
       valid_lft forever preferred_lft forever
7: vni110: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_BLUE state UNKNOWN group default qlen 1000
    link/ether b2:5c:40:26:18:c6 brd ff:ff:ff:ff:ff:ff
8: vrf-green: <NOARP,MASTER,UP,LOWER_UP> mtu 65575 qdisc noqueue state UP group default qlen 1000
    link/ether 2e:24:f5:96:66:a3 brd ff:ff:ff:ff:ff:ff
9: NMN_GREEN: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master vrf-green state UP group default qlen 1000
    link/ether aa:bb:cc:00:00:d1 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.1/24 scope global NMN_GREEN
       valid_lft forever preferred_lft forever
    inet6 fe80::a8bb:ccff:fe00:d1/64 scope link
       valid_lft forever preferred_lft forever
10: vni200: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_GREEN state UNKNOWN group default qlen 1000
    link/ether 0e:1e:9c:bb:c2:60 brd ff:ff:ff:ff:ff:ff
11: vrf-blue: <NOARP,MASTER,UP,LOWER_UP> mtu 65575 qdisc noqueue state UP group default qlen 1000
    link/ether 72:59:ac:7e:ba:f6 brd ff:ff:ff:ff:ff:ff
12: vni250: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_BLUE state UNKNOWN group default qlen 1000
    link/ether 16:d4:2a:42:4b:b2 brd ff:ff:ff:ff:ff:ff
19: CMN: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether da:24:a9:51:af:85 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.93/24 scope global CMN
       valid_lft forever preferred_lft forever
    inet6 fe80::d824:a9ff:fe51:af85/64 scope link
       valid_lft forever preferred_lft forever
20: vnet6: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_GREEN state UNKNOWN group default qlen 1000
    link/ether fe:54:00:fc:95:09 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fefc:9509/64 scope link
       valid_lft forever preferred_lft forever
21: vnet7: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master CMN state UNKNOWN group default qlen 1000
    link/ether fe:54:00:4f:47:f2 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe4f:47f2/64 scope link
       valid_lft forever preferred_lft forever
22: vnet8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master CMN state UNKNOWN group default qlen 1000
    link/ether fe:54:00:59:f1:52 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe59:f152/64 scope link
       valid_lft forever preferred_lft forever
23: vnet9: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master CMN state UNKNOWN group default qlen 1000
    link/ether fe:54:00:38:3b:fa brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe38:3bfa/64 scope link
       valid_lft forever preferred_lft forever
24: vnet10: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_BLUE state UNKNOWN group default qlen 1000
    link/ether fe:54:00:79:12:57 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe79:1257/64 scope link
       valid_lft forever preferred_lft forever
25: vnet11: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master CMN state UNKNOWN group default qlen 1000
    link/ether fe:54:00:92:83:84 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe92:8384/64 scope link
       valid_lft forever preferred_lft forever
```