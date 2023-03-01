# Commands
Commando voor het openen van de config terminal
```bash
enable
config t
```
Interfacing
```bash
Router(config)#interface FastEthernet0/0

Router(config-if)#ip address 192.168.10.1 255.255.255.0

Router(config-if)#no shutdown

Router(config-if)#

%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

Router(config-if)#interface FastEthernet0/1

Router(config-if)#ip address 192.168.20.1 255.255.255.0

Router(config-if)#no shutdown
```
Serial port openen
```bash
interface serial 0/1/0
ip address 192.168.1.1 255.255.255.0
no shut
```
![[Pasted image 20230225134332.png]]

Router 1
```bash
Router>enable 
Router#config t
Router(config)#int Gig0/0
Router(config-if)#ip address 172.16.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#int Se0/0/0
Router(config-if)#ip address 192.168.0.1 255.255.255.0
Router(config-if)#no shutdown 
Router(config-if)#exit
Router(config)#int Se0/0/1
Router(config-if)#ip address 192.168.0.3 255.255.255.0
Router(config-if)#no shutdown 
---
Nu moeten de routes bepaalt worden
---
Router(config)# ip route 172.16.1.0 255.255.255.0 192.168.0.2
Router(config)# ip route 172.16.3.0 255.255.255.0 192.168.1.2
Router(config)#ip route 192.168.1.1 255.255.255.0 192.168.0.0
```

Router 2 
```bash
Router>enable 
Router#config t
Router(config)#int Gig0/0
Router(config-if)#ip address 172.16.1.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#int Se0/0/0
Router(config-if)#ip address 192.168.0.2 255.255.255.0
Router(config-if)#no shutdown 
---
Nu moeten de routes bepaalt worden
---
Router(config)# ip route 172.16.2.0 255.255.255.0 192.168.0.1
Router(config)# ip route 172.16.3.0 255.255.255.0 192.168.1.2
Router(config)#ip route 192.168.1.1 255.255.255.0 192.168.0.0
```

Router 3
```bash
Router>enable 
Router#config t
Router(config)#int Gig0/0
Router(config-if)#ip address 172.16.3.1 255.255.255.0
Router(config-if)#no shutdown 
Router(config-if)#exit
Router(config)#int Se0/0/1
Router(config-if)#ip address 192.168.0.4 255.255.255.0
Router(config-if)#no shutdown
---
Nu moeten de routes bepaalt worden
---
Router(config)# ip route 172.16.1.0 255.255.255.0 192.168.0.1
Router(config)# ip route 172.16.2.0 255.255.255.0 192.168.0.2
Router(config)#ip route 192.168.0.0 255.255.255.0 192.168.1.1
```

Voor de computers zijn de ips hetzelfde als de router maar het laatse getal is 1 hoger 