```bash 
root@vm02-blue:~# ip r
default via 10.252.0.1 dev enp1s0 proto static 
10.252.0.0/24 dev enp1s0 proto kernel scope link src 10.252.0.101
```

```bash 
root@vm02-blue:~# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 52:54:00:79:12:57 brd ff:ff:ff:ff:ff:ff
    inet 10.252.0.101/24 brd 10.252.0.255 scope global enp1s0
       valid_lft forever preferred_lft forever
    inet6 fe80::5054:ff:fe79:1257/64 scope link
       valid_lft forever preferred_lft forever
3: enp7s0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 52:54:00:92:83:84 brd ff:ff:ff:ff:ff:ff
```