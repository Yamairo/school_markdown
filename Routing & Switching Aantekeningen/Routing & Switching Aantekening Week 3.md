 ```toc
```
## Voorbeeld simpel netwerk
#voorbeeld
![[Routing switching server.canvas]]
Het gele netwerk stelt een VLAN voor, deze zorgt ervoor dat 1 switch voor meerdere LAN's kan worden gebruikt.

Het zwarte netwerk is een normaal netwerk waarbij 2 PC's aan een server zijn aangesloten.

---

## Netwerk  architectuur
- Verdeel het netwerk in delen (lagen)
- Elke laag heeft een specefieke functie

Voorbeeld van een optimaal netwerk
![[optimaal netwerk.jpg]] ^0f2f32

In principe kun je elk netwerk gebasserd op dit voorbeeld maken

---
## Lagen
### Acces layer

^cf746f

De laag met de end devices (PC's, servers, printers, wireless acces points)

### Distribution layer 
- Aggregatie van/naar de acces layer 
- Hier komen de meeste security en routing regels
- Verdeelt doorgaans de acces laag in VLANs

### Core Layer 
- High speed backbone van het netwerk Hoge availability en redundant uitgevoerd
	- Moet snel, veel data kunnen forwarden
	- Bij kleinere netwerken, collapsed model (Core and distribution samengevoegd) 

---

## High availability 
- High availability  minimizes $\underline{downtime}$
- Involving redundancy in:
	1. Equipment
	2. Technology - hardware and software
	3. People
	4. Processes 
	5. Tools

---

## Switches

### Poorten
**Poort density**: Geeft het aantal poorten van de switch aan

 -  Forwarding rate: 
	- Definieert hoeveel data de switch kan verwerken per seconde 
	- lower performing switches gaan op de acces layer 
	- higher performing  switches gaan op de distribution en care layers
	- Als de forwarding rate te laag is, kan de switch $\underline{downtime}$

### Types
Layer 2: werkt met MAC-adressen
Layer 3: werk met IP-adressen

### POE 
**Power over ethernet:**
Stroomvervoer over dezelfde ethernet  kabel als het dataverkeer

## Types
1. Store and forward
	- Ontvangt het totale frame
	- Berekent de CRC (Cyclic Redundancy Check) en checkt de frame lengte
2. Cut-through
	- Er moet minimaal de MAC-adressen worden gelezen
	- Forward een frame direct nadat het destination adres gelezen is
	- Sneller dan store and forward 
3. Cut-through / Fragment-free
	- Slaat de eerste 64 bits van het frame op voordat het wordt geforward

---

## Symmetrisch
- Symmetrisch 
	- Alle poorten hebben dezelfde bandbreedtes 
	- Voor netwerk(deel) met stabiel netwerkverkeer
## Asymmetrisch switching 
- Asymmetrisch 
	- Sommige poorten hebben verschillende bandbreedtes
	- Bijv: meer bandbreedte voor een server om een bottleneck te voorkomen

---

## OSI Model 
![[Pasted image 20230221112047.png]]

---


## Netwerken met VLANs 
- Een VLAN id wordt toegekend aan een switchpoort
- Hosts die tot een gemeenschappelijk VLAN behoren, worden geconfigureerd in hetzelfde IP subnet
- Iedere VLAN beschikt over een uniek default-gateway adres.  De default-gateway is een router of multilayer switching
De VLAN kan niet door de andere LAN's bereikt worden
Zie #voorbeeld 

## Trunking 
De frames uit verschillende VLANs kunnen over een verbinding verplaats worden naar een andere switch of router. 
Dit heet trunking en word met de IEEE 802.1q standaard gedaan

---

## Speciale VLANs 
- Native VLANs 
- Een van de VLANs is benoemd als native VLAN
	- Zender: voegt geen tag toe voor nativ-VLAN over de trunk
	- Ontvanger: als een frame uit een trunk komt zonder tag dan wordt deze geplaatst in de nativ-VLAN 
	- Wordt gebruikt voor on-switch-protocollen
	- Default is iedere switchpoort van VLAN 1

## VLAN configureren
1. Configureer het VLAN
2. Toekennen aan een poort
3. Verificatie
4. Configureer een 802.1Q Trunk
5. Verify trunks

## Routeren tussen VLANs 
**AKA: Inter VLAN Routing**
- VLANs zijn gescheiden van elkaar
- Hosts in verschillende VLANs kunnen elkaar dus niet pingen
- Om data van een VLAN naar een host in een ander VLAN te sturen heb je dus een router nodig
- Dat kan met een "Router on a stick configuratie"

---
## Configuratie voorbeeld router "On a stick"

^a4804f

![[Pasted image 20230221114256.png]]
Vergeet niet om de no shutdown command toe te voegen
```bash
$ no shutdown
```
Met dit netwerk kun je zowel pc 1 als pc 2 pingen 

---
