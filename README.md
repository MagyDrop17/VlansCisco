# VlansCisco

## Pas 1

### Switch esquerra 
> vlan 10
> name gestio
> vlan 20
> name dept
> vlan 30
> name secre

### Switch dreta 
> vlan 10
> name gestio
> vlan 20
> name dept
> vlan 30
> name secre


## Pas 2

### Switch esquerra 
> int fa0/2
> switchport mode access
> switchport access vlan 10
> int fa0/3
> switchport mode access
> switchport access vlan 20
> int fa0/4
> switchport mode access
> switchport access vlan 30

### Switch dreta 
> int fa0/2
> switchport mode access
> switchport access vlan 10
> int fa0/3
> switchport mode access
> switchport access vlan 20
> int fa0/4
> switchport mode access
> switchport access vlan 30


## Pas 3

### Switch esquerra 
> int fa0/1
> switchport mode trunk

### Switch dreta 
> int fa0/1
> switchport mode trunk

### Switch troncal 
> vlan 10
> name gestio
> vlan 20
> name dept
> vlan 30
> name secre
> int range fa0/1-3
> switchport mode trunk
> int fa0/1
> switchport mode trunk


## Pas 4

### Router
> int gi0/0.1
> encapsulation dot1Q 10
> ip address 192.168.10.1 255.255.255.0
> no shutdown
> int gi0/0.2
> encapsulation dot1Q 20
> ip address 192.168.20.1 255.255.255.0
> no shutdown
> int gi0/0.3
> encapsulation dot1Q 30
> ip address 192.168.30.1 255.255.255.0
> no shutdown
> int gi0/0
> no shutdown
