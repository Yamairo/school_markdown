# Inhoudsopgave
```toc
```

## Routing & Switching

### Week 5 STP

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

### Week 6 Routing intro, MLS, SVI's
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