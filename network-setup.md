Router - Cisco 1941 Series
Switches - Cisco Catalyst 2960
PC-PT PC0 168.90.0.3
PC-PT PC1 168.90.0.2
PC-PT PC2 210.3.14.4
Laptop-PT Laptop 0 168.90.0.4
Server-PT Server 0 168.90.0.5
Server-PT Server 1 210.3.14.2
Server-PT Server 2 210.3.14.3

UPDATE:
PC-PT PC3 168.90.0.6
PC-PT PC4 210.3.14.5

DHCP commands and steps:
Firstly, I opened the routers CLI tab. I typed the following commands:
enable
configure terminal
interface gigabitEthernet 0/0
ip address 168.90.0.1 255.255.0.0
no shutdown
exit
interface gigabitEthernet 0/1
ip address 210.3.14.1 255.255.255.0
no shutdown
exit
ip dhcp pool Network1
network 168.90.0.0 255.255.0.0
default-router 168.90.0.1
exit
ip dhcp pool Network2
network 210.3.14.0 255.255.255.0
default-router 210.3.14.1
exit