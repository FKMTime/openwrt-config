# SETUP CMDS

## WAN on eth (with 192.168.3.1 address and port 22 and 80 port forwarded to wan)
```bash
# /etc/config/dhcp
uci del dhcp.lan.ra_slaac
uci set dhcp.lan.ra_preference='medium'
# /etc/config/firewall
uci add firewall redirect # =cfg0e3837
uci set firewall.@redirect[-1].dest='lan'
uci set firewall.@redirect[-1].target='DNAT'
uci set firewall.@redirect[-1].name='ssh'
uci set firewall.@redirect[-1].src='wan'
uci set firewall.@redirect[-1].src_dport='22'
uci set firewall.@redirect[-1].dest_ip='192.168.3.1'
uci set firewall.@redirect[-1].dest_port='22'
uci add firewall redirect # =cfg0f3837
uci set firewall.@redirect[-1].dest='lan'
uci set firewall.@redirect[-1].target='DNAT'
uci set firewall.@redirect[-1].name='web'
uci set firewall.@redirect[-1].src='wan'
uci set firewall.@redirect[-1].src_dport='80'
uci set firewall.@redirect[-1].dest_ip='192.168.3.1'
uci set firewall.@redirect[-1].dest_port='80'
# /etc/config/network
uci del network.cfg030f15.ports
uci del network.lan.device
uci set network.lan.multipath='off'
uci del network.cfg030f15
uci set network.globals.packet_steering='1'
uci set network.wan=interface
uci set network.wan.proto='dhcp'
uci set network.wan.device='eth0'
uci set network.wan.multipath='off'
uci del network.lan.ipaddr
uci add_list network.lan.ipaddr='192.168.3.1/24'
uci set network.wan.peerdns='0'
uci add_list network.wan.dns='1.1.1.1'
```

```bash

```

```bash
```
