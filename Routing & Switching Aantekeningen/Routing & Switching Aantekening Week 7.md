```toc
```

---

## ACL (Assign Client Lists)

### Doel van ACL

Een ACL wordt gebruikt om netwerkverkeer te filteren

Er zijn verschillende methodes om dit te doen:
1. **Standaard ACL**: Filtert alleen IP packets gebasseerd op het source address
2. **Extended ACL**: Filtert IP packets op meerdere attributen, zoals:
   - Source en destination IP adres
   - Source en destination TCP en UDP poorten
   - Protocol typen (IP, ICMP, enz.)

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

1. **Static NAT**
2. **Dynamic NAT**
3. **PAT (Port Address Translation; aka *Dynamic NAT with overload*)**

- Full cone NAT (=normaal PAT)
- Address Restricted Cone NAT
- Port Restricted Cone NAT
- Symmetrisch NAT

### Terminologie
- <a style="color:red">Inside Local Addresses</a> - Adres van eigen host gezien vanuit het eigen netwerk.
- <a style="color:red">Inside Global Addresses</a>- Adres van eigen host gezien door de provider.
- <a style="color:red">Outside Local Addresses</a>- Adres van een host in een ander bedrijfsnetwerk.
- <a style="color:red">Outside  Global Addresses</a>- Adres van een andere host, gezien vanaf de buitenwereld (b.v. een ge-NAT IP-adres of een remote server met publiek adres)

### Nat overload (PAT)
![[Pasted image 20230328114912.png]]

---

## Pat
- Gebruikt 16 bit poortnummers


---

## Using Port Forwarding

