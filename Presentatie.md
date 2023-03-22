```toc
```
## Overzicht
### Groep 1:
**Redundancy** is key

#### Rotterdam
4 switches
2 Multi-layer  switches
1 Wireless Acces Point
De  Multi-layer  switches gebruiken inter-vlan switching en trunking

#### Maastricht
2 Multi-layer Switches 
Maar 1 router omdat customer service "minder belangrijk is" 

#### Lelystad
2 Multi-layer Switches 

#### Utrecht
2 Multi-layer Switches

#### Globaal
Maakt gebruik van SEC, een soort VPN.
Fibre optic kabels tussen router en Multi-layer Switches.

----

### Groep 2
#### Utrecht
Redundantie in de distributie laag

#### Maastricht 
Geen redundantie 

#### Lelystad 
Firewall in core laag
Redundantie in distributie laag

#### Rotterdam 
Redundantie in de distributie laag

#### Security
- Firewall 
- VLAN's 
- OSPF 
- Toegangsbeleid (Wachtwoorden)

#### Protocollen
- OSPF
- IPV 4
- NAT
- STP
- DNS
- SSH
- VLAN
---

**Opmerking van Adri**: OSPF is nog niet behandeld

---

### Groep 3
Ik was lui

---

**Opmerkingen van Adri**: 

---

### Groep 4
#### Eisen
- Netwerkapparatuur van Cisco
- Overal LAN
- Vaste Desktop
- Alle pc's hebben toegang tot Lelystad 
- Beveiligd
- Eigen systemen per locatie
#### Ontwerp
Full-mesh en Semi-mesh

##### Rotterdam 
Redundantie door twee multi-layer switches met inter-VLAN routing.
En een Wireless Acces Point.

##### Utrecht 
Redundantie door twee Multi-layer switches. En 2 Wireless Acces Points

##### Maastricht 
Redundantie door twee Multi-layer switches

##### Lelystad
2 switches bij de servers voor redundantie.

#### Protocollen 
- RIP version 2
- STP
- HSRP
  
#### Beveiliging
- ASM
- Switchport security/ MAC-address sticky

---

**Opmerking van Adri**: Moet er niet 2 switches als je ook 2 Acces points hebt voor redundantie 

---