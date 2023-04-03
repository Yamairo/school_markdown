```toc
```

---

## ACL (Assign Client Lists)

### Doel van ACL

Een ACL wordt gebruikt om netwerkverkeer te filteren

Er zijn verschillende methodes om dit te doen:
1. **Standaard ACL**: Filtert alleen IP packets gebasseerd op het source address 
   ![[Pasted image 20230403215851.png]]^c03b04
2. **Extended ACL**: Filtert IP packets op meerdere attributen, zoals: ^c1727b
   - Source en destination IP adres
   - Source en destination TCP en UDP poorten
   - Protocol typen (IP, ICMP, enz.)
 ![[Pasted image 20230403215908.png]]

---

### Standaard / Extended
<p style="color:red">Dit is handig voor de toets</p>
Standaard ACL: 1-99
Extended ACL: 100-199

```bash
R1(config)# ip acces-list 6
```

#### Standaard
<p style="color:red">Standaard ACL komt zo dicht mogelijk bij de destination poort</p>
Dit is omdat als de standaard ACL naast de source zit dan kan deze niet meer naar de destination.

#### Extended 


#### Implicit deny
Elke acces list wordt afgesloten met een deny any.

---

## ACL
<p style="color:red">Inbound (in) en Outbound (out)</p>

### Inbound
![[Pasted image 20230328110447.png]]

---

### Outbound
![[Pasted image 20230328110534.png]]
Er wordt eerst naar de route tabel gekeken. Dit is omdat je wilt weten welke interface er gebruikt wordt.

---

## Private Address Ranges (RFC 1918)
| Class | RFC 1918 Internal Address Range |
| ----- | ------------------------------- |
| A     | 10.0.0.0 - 10.255.255.255       |
| B     | 172.16.0.0 - 172.16.255.255     | 
| C     | 192.168.0.0 - 192.168.255.0     |

---

## NAT

1. **Static NAT** 1 op 1 mapping tussen lokale en globale adressen.
2. **Dynamic NAT** een groot aantal private IP adressen mappen op een klein aantal publieke adressen.
3. **PAT (Port Address Translation; aka *Dynamic NAT with overload*)** Maakt gebruik van het poortnummer om een groot aantal private IP adressen te mappen op een klein aantal publieke adressen (vaakst gebruikt).

- Full cone NAT (=normaal PAT)
	- Elk device kan van buiten een verbinding maken als het de destination poort kent. Kan statisch toegewezen zijn. NAT kan de port mappen naar een andere destination port, dit heet port forwarding.
- Address Restricted Cone NAT
	- De NAT router houdt de source port en de destination adres bij nadat verkeer naar buiten is verstuurd. Dus inkomend verkeer moet die poort als destination poort gebruiken en ook het source IP-adres moet gelijk zijn aan het opgeslagen destination adres.
- Port Restricted Cone NAT
	- Net als hierboven maar nu moet ook de source port van het inkomende segment gelijk aan die van opgeslagen destination port.
- Symmetrisch NAT
	- Creëert unique mappings. Elke source port wordt vertaald naar een random (ephemeral) port. Voor elke verandering in het destination IP-adres wordt zo’n mapping gedaan. Dit levert een extra beveiligingslaag.

### Terminologie
- <a style="color:red">Inside Local Addresses</a> - Adres van eigen host gezien vanuit het eigen netwerk.
- <a style="color:red">Inside Global Addresses</a>- Adres van eigen host gezien door de provider.
- <a style="color:red">Outside Local Addresses</a>- Adres van een host in een ander bedrijfsnetwerk.
- <a style="color:red">Outside  Global Addresses</a>- Adres van een andere host, gezien vanaf de buitenwereld (b.v. een ge-NAT IP-adres of een remote server met publiek adres)

![[Pasted image 20230403222309.png]]
![[Pasted image 20230403222318.png]]

### Nat overload (PAT)
![[Pasted image 20230328114912.png]]

---

## Pat
- Gebruikt 16 bit poortnummers
- De PAT router voegt de poortnummers toe aan de inside global addressen, welke opgeslagen worden in de NAT tabel. In principe wordt het source portnummer gebruikt in het segment gebruikt, als dat overlapt met een bestaand adres wordt een alternatief poortnummer gezocht worden.
- Als de server een packet terugstuurt, zal nu het destination poortnummer uit het packet gehaald worden en vergeleken worden met de entries in de NAT table. Zo kan het lokale ip adres teruggevonden worden 
- Op deze manier wordt ook extra beveiliging toegevoegd omdat er gecheckt kan worden of de packets van die remote server inderdaad gewenst waren.


---

## Using Port Forwarding

