
```bash
# ip r
default via 192.168.1.1 dev ens33 proto static 
10.10.10.1 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
10.30.30.1 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
10.252.0.0/24 dev NMN_BLUE proto kernel scope link src 10.252.0.1
192.168.1.0/24 dev ens33 proto kernel scope link src 192.168.1.94
192.168.100.0/31 nhid 44 via 192.168.200.0 dev ens38 proto ospf metric 20
192.168.100.2/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.100.4/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.100.6/31 nhid 35 via 192.168.200.2 dev ens37 proto ospf metric 20
192.168.100.8/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.100.10/31 nhid 35 via 192.168.200.2 dev ens37 proto ospf metric 20
192.168.100.12/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.100.14/31 nhid 44 via 192.168.200.0 dev ens38 proto ospf metric 20
192.168.100.24/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.100.26/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.122.0/24 dev virbr0 proto kernel scope link src 192.168.122.1 linkdown
192.168.200.0/31 dev ens38 proto kernel scope link src 192.168.200.1
192.168.200.2/31 dev ens37 proto kernel scope link src 192.168.200.3
192.168.200.4/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
192.168.200.6/31 nhid 56 proto ospf metric 20
        nexthop via 192.168.200.2 dev ens37 weight 1
        nexthop via 192.168.200.0 dev ens38 weight 1
```

```
# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet 10.20.20.1/32 brd 10.20.20.1 scope global lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:79:9b:dd brd ff:ff:ff:ff:ff:ff
    altname enp2s1
    inet 192.168.1.94/24 brd 192.168.1.255 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe79:9bdd/64 scope link
       valid_lft forever preferred_lft forever
3: ens37: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:79:9b:e7 brd ff:ff:ff:ff:ff:ff
    altname enp2s5
    inet 192.168.200.3/31 brd 255.255.255.255 scope global ens37
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe79:9be7/64 scope link
       valid_lft forever preferred_lft forever
4: ens38: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:79:9b:f1 brd ff:ff:ff:ff:ff:ff
    altname enp2s6
    inet 192.168.200.1/31 brd 255.255.255.255 scope global ens38
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fe79:9bf1/64 scope link
       valid_lft forever preferred_lft forever
5: NMN_BLUE: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 08:00:27:4b:1d:46 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.1/24 brd 10.252.0.255 scope global NMN_BLUE
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe4b:1d46/64 scope link
       valid_lft forever preferred_lft forever
6: virbr0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 52:54:00:2f:a2:8a brd ff:ff:ff:ff:ff:ff
    inet 192.168.122.1/24 brd 192.168.122.255 scope global virbr0
       valid_lft forever preferred_lft forever
7: vni110: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_BLUE state UNKNOWN group default qlen 1000
    link/ether ee:fd:d1:6c:10:8b brd ff:ff:ff:ff:ff:ff
8: vrf-green: <NOARP,MASTER,UP,LOWER_UP> mtu 65575 qdisc noqueue state UP group default qlen 1000
    link/ether 0e:8e:e0:7a:f8:ec brd ff:ff:ff:ff:ff:ff
9: NMN_GREEN: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master vrf-green state UP group default qlen 1000
    link/ether aa:bb:cc:00:00:d1 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.1/24 scope global NMN_GREEN
       valid_lft forever preferred_lft forever
    inet6 fe80::a8bb:ccff:fe00:d1/64 scope link
       valid_lft forever preferred_lft forever
10: vni200: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_GREEN state UNKNOWN group default qlen 1000
    link/ether be:a8:7c:e1:ce:85 brd ff:ff:ff:ff:ff:ff
11: vnet0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_BLUE state UNKNOWN group default qlen 1000
    link/ether fe:54:00:06:3d:44 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::fc54:ff:fe06:3d44/64 scope link
       valid_lft forever preferred_lft forever
12: vnet1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master NMN_GREEN state UNKNOWN group default qlen 1000
    link/ether 62:56:c3:f9:3f:cb brd ff:ff:ff:ff:ff:ff
    inet6 fe80::6056:c3ff:fef9:3fcb/64 scope link
       valid_lft forever preferred_lft forever
```