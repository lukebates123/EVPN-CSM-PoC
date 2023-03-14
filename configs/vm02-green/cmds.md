```bash 
root@vm02-green:~# ip r
default via 10.252.0.1 dev enp1s0 proto static
10.252.0.0/24 dev enp1s0 proto kernel scope link src 10.252.0.101
```

```bash 
root@vm02-green:~# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 52:54:00:fc:95:09 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.101/24 brd 10.252.0.255 scope global enp1s0
       valid_lft forever preferred_lft forever
    inet6 fe80::5054:ff:fefc:9509/64 scope link
       valid_lft forever preferred_lft forever
3: ens1: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 52:54:00:4f:47:f2 brd ff:ff:ff:ff:ff:ff
    altname enp8s1
4: enp9s0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 52:54:00:59:f1:52 brd ff:ff:ff:ff:ff:ff
5: enp10s0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 52:54:00:38:3b:fa brd ff:ff:ff:ff:ff:ff
```