# Inhoudsopgave
```toc
```

## Routing & Switching

### Week 4 STP

#### Switching Loops
1. Multiple Frames
	- Intentieel geen entries in mac-table S 1
	- Host A zend een frame naar host B
	- S 1 (lege mac-table) flood de switch
	- Host B zal nu twee frames ontvangen

![[Pasted image 20230403135747.png]]

2. Broadcast Storm
	- Host A zend een broadcast frame
	- Dit wordt ge-flood door alle switches 
	- Een broadcast storm resulteert

![[Pasted image 20230403140019.png]]

#### Protocol 802.1 D
Bij [[#Switching Loops]] werden problemen gegeven die kunnen voorkomen bij het aansluiten van meerdere switches. Deze problemen zijn op te lossen met [[STP]], met een **Spanning Tree Algoritme** wordt de LAN verdeeld in een *boomstructuur*.
Daarna worden de beste paden gekozen door het netwerk en sommige paden worden afgesloten hierdoor heb je geen loops meer in het netwerk.

##### Voorbeeld
Door een van de poorten , in het broadcast domain, te blokkeren voorkom je dat er switching loops voorkomen. Dit is omdat een blocked switchport geen user data verstuurt.
![[Pasted image 20230403140529.png]]

#### BDPU
[[STP]] maakt gebruik van [[BPDU]] (Bridge Protocol Data Units)
Deze STP-frames worden tussen switches gestuurd om de "*Spanning Tree*" op te bouwen. En bepaalt welke paden het best zijn en welke poorten geblokkeerd moeten worden.

![[Pasted image 20230403141541.png]]

Belangrijke informatie voor BPDU is dat je een BID (Bridge Identifier) hebt die bestaat uit de <a style="font-weight:bold">Priority en MAC-adres</a>. Ook heb je een priority range van 1 t/m 32768 (in stappen van 4096) met default waarde **32768**

##### Gebruik
Bij het ontvangen van de BPDU zal in een switch de volgende stappen genomen worden:

#Handigvooropdetoets 
1. De <a style="color:inherit">laagste</a> waarde wint
2. Priority waardes worden eerst vergeleken, als gelijk dan wordt naar het MAC-gekeken (de bridge-ID bestaat uit deze twee componenten, ze worden niet opgeteld).
3. <a style="color:inherit">BID</a> is belangrijker dan
   <a style="color:inherit">root-path-cost</a> is belangrijker dan
   <a style="color:inherit">port-ID</a>

#### Werking
De manier waarop STP werkt kan in 3 fasen worden uitgelegd

1. De **root bridge**(*root war*) wordt gekozen
2. De **root ports**(ports die "wijzen" naar de root bridge) op de non-root bridges
3. De **designated ports**(ports die wijzen vanaf de root bridge) per segment worden gekozen en de overgebleven ports worden **geblokkeerd**

##### Fase 1
1. Elke switch gaat aan en gedraagt zich als de root. Elke 2 seconden wordt er een [[BPDU]] uit elke poort gestuurd waarbij de root-BID gelijk is aan de sender-BID
2. Als er een [[BPDU]] wordt ontvangen met een lagere root-BID dan de eigen BID dan zal het volgende gebeuren
	1. De switch gaat op alle andere poorten [[BPDU]] 's sturen met als root-BID de ontvangen BID
	2. De switch zal geen [[BPDU]] 's meer genereren (dat doet alleen de root bridge). Wel worden [[BPDU]] 's van de root bridge doorgestuurd
3. Herhaal dit proces op alle switches totdat er een echte root bridge is
4. De root bridge is nu de enige switch die nieuwe [[BPDU]] 's verzendt de rest stuurt alleen [[BPDU]] 's die ze ontvangen van de Root Bridge door naar de volgende switch
![[Pasted image 20230403143120.png]]
![[Pasted image 20230403143135.png]]

##### Fase 2
1. Op de <a style="color:inherit">non-root bridges</a> moet gekozen worden welke poorten wel en niet gebruikt moeten worden
2. Dit wordt gedaan door het snelste pad naar de Root Bridge te zoeken d.m.v. *[[root-path-cost]]*.
3. De poort met de laagste root-path-cost wordt root-port
![[Pasted image 20230403143820.png]]
![[Pasted image 20230403143837.png]]
![[Pasted image 20230403143900.png]]
##### Fase 3
1. Alle poorten van de root bridge zijn *designated* ports
2. Voor de andere ports bepaalt de sender-BID welke port actief blijft (*designated*) en welke niet.
3. Als een switch op twee manieren met één andere switch is verbonden dan zal er een lus zijn, hierbij wordt de port-ID bepaalt om een *designated* port aan te wijzen. De andere port wordt uitgeschakeld
![[Pasted image 20230403144238.png]]
![[Pasted image 20230403144250.png]]

#### Port roles
#Handigvooropdetoets 
- <span style="color:red">Root Port</span>
	- Port met het beste pad naar de root switch
	- Deze poort stuurt verkeer naar de root switch
- <span style="color:red">Designated Port</span>
	- Alle root poorten
	- Bij de non-root bridges is het de port die van de root afwijst
	- Er kan maar een designated port per segment zijn
- <span style="color:red">Non-Designated Port</span>
	- Blokkeert frames (**niet** [[BPDU]] 's)
	- Voegt geen ingang in aan de MAC-tabel
- <span style="color:red">Disabled Port</span>
	- Handmatig uitgezet
![[Pasted image 20230403144822.png]]

### Week 5 Routing intro, MLS, SVI's
Routers werken op lagen 1,2 en 3 en worden gebruikt om het juiste pad in een netwerk te bepalen. Ook kunnen ze gebruikt worden om: een koppeling tussen twee datalink protocollen te maken; een scheiding van het (inter) netwerk d.m.v. bepaalde regels (bv et blokkeren van gevaarlijk verkeer); en het blokkeren van MAC-broadcasts tussen verschillende netwerkdelen.

![[Pasted image 20230403145405.png]]

#### IP Routing
Als een packet aankomt bij een router zal de  source MAC-adres  worden aangepast naar de MAC-adres van deze router port. Vervolgens zal de destination MAC-adres worden aangepast naar die van de router.
![[Pasted image 20230403150213.png]]
Je kan IP routing gebruiken om te supernetten
![[Pasted image 20230403150240.png]]
Je kan ook een loopback interface aanmaken dit is geen fysieke poort maar wordt als een software interface gezien. Dit is handig voor het testen van netwerken.
![[Pasted image 20230403150432.png]]

#### SVI (Switched Virtual Interfaces)
##### Inter VLAN-Routing
Je kan met gebruik van **Routing-on-a-stick** tussen VLAN's routeren
![[Routing & Switching Aantekening Week 3#Configuratie voorbeeld router "On a stick"]]

Maar dit kan ook met gebruik van een MLS (Multi Layer Switch), dit wordt gedaan met gebruik van SVI. Deze SVI is een virtuele interface voor een VLAN naar een laag 3 routing systeem. SVI wordt 1 op 1 met een VLAN ingesteld er kan dus maar een SVI per VLAN zijn.

![[Pasted image 20230403153925.png]]

![[Pasted image 20230403154008.png]]
Hierboven is een configuratie van een SVI te zien, het is belangrijk dat je altijd *ip routing* aanzet anders werkt dit niet.

Je kan SVI ook gebruiken voor remote management met SSH
![[Pasted image 20230403154142.png]]

Er zijn 3 factoren die bepalen ofdat een SVI aanstaat
1. De VLAN bestaat en is *actief* in de VLAN database op de switch
2. De VLAN interface *bestaat* en is niet administratively down
3. Ten minste een laag 2 (acces of trunk) port bestaat op de switch en heeft een verbinding met de *up state* van deze VLAN, en deze staat in de spanning-tree *forwarding* state op de VLAN

Als dit alles waar is kan je de SVI controleren als volgt
![[Pasted image 20230403154618.png]]

##### Voor en Nadelen
<span style="color:green">Voordelen</span>
1. Het is veel *sneller* dan *routing-on-a-stick* omdat alles via *hardware* word gerouteerd.
2. Er is **geen** nood voor *externe* verbindingen van de switch naar de router voor routering.
3. Ook kunnen laag 2 *EtherChannels* gebruikt worden om meer bandbreedte te gebruiken tussen switches
4. *Latency* is veel lager omdat de switch niet verlaten wordt
   
<span style="color:red">Nadelen</span>
Je moet een *laag 3 switch* hebben om Inter-VLAN routing te gebruiken, en deze zijn erg duur.

Op een multi layer switch kan gebruik gemaakt wordenvan
1. Laag 2 switchpoorten
2. Laag 3 SVI's
3. Laag 3 ports(routed ports)

##### Routed ports
Een routed port is een fysieke poort met laag 3 toepassingen. Deze port is niet verbonden met een VLAN, en heeft een soortgelijk interface aan dat van een router. Laag 2 functionaliteit is verwijdert en daarom kan deze niet geconfigureerd worden.

![[Pasted image 20230403160020.png]]

### Week 6 VTP (VLAN Trunk Protocol)
VTP Maakt het makkelijker om VLAN databases tussen switches te beheren. Dit is handig omdat naarmate je meer switches gebruikt in een netwerk het moeilijker wordt om VLANs en trunks te beheren.

VTP wordt gebruikt om **automatisch** informatie van VLANs tussen switches uit te wisselen

#### Voordelen en nadelen
<span style="color:green">Voordelen</span>
VTP maakt het beheren van de VLAN database tussen meerdere switches makkelijker en dus zal de VLAN configuratie constant blijven door het gehele netwerk. VTP log-melding kan worden gegeven als een VLAN wordt toegevoegd in het netwerk

<span style="color:red">Nadelen</span>
Je moet nog steeds poorten toewijzen aan de VLANs 

#### Revisienummer
Het configuratie-revisienummer is een 32-bits nummer dat het revisieniveau voor een VTP-frame aangeeft.
Het standaard configuratienummer voor een switch is nul.
Elke keer dat een VLAN wordt toegevoegd of verwijderd, wordt het configuratie-revisienummer verhoogd. Elk VTP-apparaat houdt het revisienummer van de VTP-configuratie bij dat eraan is toegewezen.

 - Note: Een wijziging van de VTP-domeinnaam verhoogt het revisienummer niet. In plaats daarvan wordt het revisienummer teruggezet naar nul.

<span style="color:red">Probleem met revisienummer </span>
- Als een nieuwe switch wordt toegevoegd aan het netwerk met een hoger revisienummer , wordt de server bijgewerkt met de VLAN-database van de nieuwe switch
- Hierdoor kan het netwerk onbruikbaar worden omdat de verkeerde VLAN-info door deze nieuwe *server* wordt doorgegeven

#### Pruning
Met pruning wordt de capaciteit van het netwerk verhoogt doordat je VTP-info alleen door trunk verbindingen, die gebruikt worden om betreffende hosts te bereiken, stuurt.
Switches communiceren dan over de VLANs die aan het eind van de trunk bereikbaar zijn
Je schakelt pruning in met het commando ```vtp pruning ```

#### Modes 
#Handigvooropdetoets 
Er zijn 3 VTP operating modes
- **Client**
	- Kan <a style="color:inherit">geen</a> VLANs creëren, verwijderen en veranderen
	- Krijgt VLAN informatie van server
- **Server**
	- Kan VLANs creëren, verwijderen en veranderen 
- **Transparant**
	- Kan <a style="color:inherit">lokaal</a> VLANs creëren, verwijderen en veranderen 
	- Stuurt VTP-berichten door

---

#### DHCP
Voor het toekennen van **dynamische** adressen wordt **DHCP** gebruikt
- Schaalbaar
- Simpel
- Een router kan als DHCP server worden geconfigureerd 
- Dure serverapparatuur is niet nodig

![[Pasted image 20230403194607.png]]

##### Werking
- DHCP levert IP-gerelateerde informatie van een (DHCP) sever aan clients deze gegevens worden tijdelijk als *lease* verstreken.
- Hierdoor kunnen later andere clients het IP-adres krijgen
- Naast het <a style=color:inherit>IP-address</a> en <a style=color:inherit>netmask</a> levert DHCP ook : <a style=color:inherit>default-gateway (router)</a>, <a style=color:inherit>DNS-adres</a>, <a style=color:inherit>WINS-server</a>, <a style=color:inherit>lease-duur</a>, <a style=color:inherit>domain-name</a>, ...

##### Configuratie
![[Pasted image 20230403195140.png]]
![[Pasted image 20230403195153.png]]

##### Relay
<span style="color:red">Probleem met DHCP </span>
Als een DHCP server in een ander netwerk staat dan worden discover messages van de host niet ontvangen.
![[Pasted image 20230403195317.png]]

###### Oplossing: IP Helper Address
Door een **helper address** te configureren op tussenliggende routers zullen de DHCP broadcasts doorgestuurd worden naar de betreffende servers.
![[Pasted image 20230403195549.png]]

Deze helper adressen kunnen ook op SVI gebruikt worden
![[Pasted image 20230403195622.png]]

DHCP is niet het enige protocol waar broadcasts gebruikt worden
![[Pasted image 20230403195721.png]]

Voor info over de lagen zie
![[Routing & Switching Aantekening Week 3#Lagen]]

---

#### Redundantie
![[Routing & Switching Aantekening Week 6#First Hop redundancy Protocols]] 

##### HSRP (Hot Standby Routing Protocol)
![[Pasted image 20230403200551.png]]
![[Pasted image 20230403200607.png]]
![[Pasted image 20230403200617.png]]
![[Pasted image 20230403200627.png]]

- *Active router* -Doet het doorsturen van datapakketten en verzendt hallo-berichten naar andere routers om hen op de hoogte te stellen van de status ervan?
- *Standby router* - Bewaakt de status van de actieve router en begint snel met het doorsturen van pakketten in het geval van een actieve routerstoring.
- *Virtual Router* - **Bestaat niet!** Vertegenwoordigt een consistent beschikbare router met een IP-adres en een MAC-adres voor de hosts op een netwerk.
- *Other routers* - Houd HSRP-hallo-berichten in de gaten, maar reageer niet. Functioneren als normale routers die naar hen verzonden pakketten doorsturen, maar geen pakketten doorsturen die zijn geadresseerd aan de virtuele router.
###### Progression
![[Pasted image 20230403200931.png]]
Beide switches starten in de Initial status, verwerken de configuraties en gaan dan verder naar de Listening status, terwijl ze HSRP-hello's op het netwerk verwachten: 
- Als hello's na een time-out niet worden ontvangen, gaat een switch naar de speak status en kiest actief een nieuw actief en standby-apparaat door naar elkaars hello-pakketten te kijken om te bepalen welke router welke rol moet aannemen.
- Als hello's wordt ontvangen voordat de time-out is verstreken, blijft de switch in de listening status en wordt afhankelijk van de prioriteit naar Actief of Stand-by verplaatst.

###### Operation
![[Pasted image 20230403201037.png]]
- The virtual router is a virtual IP and MAC address pair that end devices have configured as their default gateway. 
- The active router processes all packets and frames sent to the virtual router address. 
- The HSRP standby router monitors the operational status of the HSRP group and quickly assumes packet-forwarding responsibility if the active router becomes inoperable.

---

- Wanneer de standby-router geen hello-berichten meer ontvangt van de actieve router, wordt deze een actieve router.
- Omdat de hosts een virtueel IP- en MAC-adres gebruiken, zien ze weinig tot geen onderbreking van de service.
- In het zeldzame geval dat zowel de actieve als de standby-routers falen, zullen alle andere routers in de groep worden gekozen voor de actieve en standby-rollen;
- De router met het hoogste IP-adres op de HSRP-interface wordt de actieve router, tenzij er een HSRP-prioriteit is geconfigureerd.

###### MAC-adres
<span style="color:red">0000.0c</span><span style="color:green">06.ac</span><span style="color:blue">01</span>

- <span style="color:red">Vendor ID (Vendor Code)</span> - De eerste 3 bytes van het MAC-adres , als deze onbekend is wordt het gelijk gezet aan 0000.0c
- <span style="color:green">HSRP Code (HSRP standard virtual MAC address)</span> - De volgende 2 bytes van het MAC-adres *zijn altijd 07.ac*
- <span style="color:blue">Group ID (HSRP group number in hex)</span> - De laatste byte van het MAC-adres 

###### Configuratie
![[Pasted image 20230403201733.png]]
![[Pasted image 20230403201746.png]]

###### Spanning Tree (HSRP)
De STP *root* van elke VLAN zal gelijk moeten zijn aan de *actieve* HSRP uitvoering. Op deze manier is er ook load balancing.
![[Pasted image 20230403201915.png]]
![[Pasted image 20230403201925.png]]
![[Pasted image 20230403201931.png]]
![[Pasted image 20230403201938.png]]

---

### Week 7 ACLs, NAT

#### ACL Acces Control List
Een ACL is een lijst met *permit* en *deny* statements 
![[Pasted image 20230403215507.png]]

Het doel hiervan is om verkeertypes te selecteren die je wilt filteren, analyseren, forwarden, of op een andere manier wilt verwerken.

![[Pasted image 20230403215529.png]]

##### Type ACLs
![[Routing & Switching Aantekening Week 7#^c03b04]]
![[Routing & Switching Aantekening Week 7#^c1727b]]

##### Configuratie
![[Pasted image 20230403215939.png]]

#Handigvooropdetoets 
Standard ACL 1-99
Extended ACL 100-199

![[Pasted image 20230403220020.png]]
![[Pasted image 20230403220040.png]]
![[Pasted image 20230403220053.png]]
![[Pasted image 20230403220106.png]]

##### Inbound of Outbound
Inbound of outbound wordt per interface bepaald.
Hierbij is Inbound [in] het ingaand verkeer
En
Outbound [out] is het uitgaand verkeer

**Inbound**
![[Pasted image 20230403221243.png]]

**Outbound**
![[Pasted image 20230403221316.png]]

##### Standard of Extended
###### Standaard
**Standard** is dichtbij de **destination**
Als je dit niet doet dan zal een *deny* statement ervoor zorgen dat heel het source netwerk geen toegang heeft tot geen enkel ander netwerk.

Dat is omdat een standaard ACL alleen kan filteren *vanaf* eem bepaald netwerk en niet *naar* een bepaald netwerk. Er kan ook geen onderscheid gemakt worden tussen protocols.
![[Pasted image 20230403220538.png]]
![[Pasted image 20230403221538.png]]
Hieronder zie je wat er gebeurd als de standard ACL vlakbij de source is
![[Pasted image 20230403220607.png]]

###### Extended
**Extended** is dichtbij de **source**
Als een extended ACL dichtbij een destination wordt geplaatst dan wordt de bandbreedte verspild. Dit is omdat de packets pas gedropt worden als ze bij de destination komen (dit geld ook voor standaard ACL).

Een extended ACL wordt daarom zo dicht mogelijk bij de source geplaatst. Dit kan omdat deze veel specifieker is dan een standaard ACL

![[Pasted image 20230403221012.png]]

Syntax voor een extended ACL: access-list [nr] [permit|deny] [ip|icmp|tcp|udp] [source adres] [mask] [destination adres] [mask] [eq|ls|gt] [portnr|name] [log]
- access-list [nr] = het unieke nummer van de ACL
- [permit|deny] = het verkeer wordt toegelaten of geweigerd 
- [ip|icmp|tcp|udp] = het netwerk protocol of transport protocol dat gefilterd moet worden 
- [source adres] = het source IP/netwerk adres dat gefilterd moet worden 
- [mask] = wildcard mask dat bepaalt welk gedeelte van het source adresveld gefilterd moet worden 
- [port number] = poortnummer van belang (alleen als layer-4 protocol is geselecteerd)

Als het netwerkverkeer specifieker moet worden gefilterd, kunnen de volgende opties worden gebruikt: 
[eq|ls|gt]
- eq = gelijk aangepast 
- ls = kleiner dan
- gt = groter dan 

[portnr|name] = het poortnummer van het upper layer protocol (HTTP, FTP) dat gefilterd moet worden 
[log] deze optie logt al het verkeer dat niet door de ACL wordt toegelaten (dit heet een access-list violation)

![[Pasted image 20230403221946.png]]
![[Pasted image 20230403222003.png]]
##### De drie Per's
Een ACL moet aan de volgende eisen voldoen:
Een ACL...
1. Per protocol
2. Per interface
3. Per richting (in/uit)
 
#### NAT (Network Address Translation)
![[Routing & Switching Aantekening Week 7#NAT]] 

##### PAT
![[Routing & Switching Aantekening Week 7#Pat]]

###### Configuratie
Stel we hebben dit netwerk
![[Pasted image 20230403222816.png]]

**Dynamic NAT**
![[Pasted image 20230403222807.png]]

**Dynamic NAT met overload**
![[Pasted image 20230403222827.png]]

##### Port forwarding
![[Pasted image 20230403222959.png]]

----

