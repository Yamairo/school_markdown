```toc
```

## Cyber security
---
### Cybersecurity (week 1)
#### Inleiding
In week 1 werd er een korte herhaling van Security essentials gehouden

**Een voorbeeld van Risico**
![[Pasted image 20230301140121.png]]

---

#### Belangrijke begrippen
- **Incident**: Event dat tot schade gaat leiden (zonder verdere maatregelen)
	- *bijv. Host wordt overgenomen (pwnd), website down*
- **(Be)dreiging (threat)**: Oorzaak van een incident (het bestaan van deze oorzaken ligt buiten de controle van de risicopartij)
	- *bijv: malware,  hacker, vijandelijke staat, APT, boze werknemer*
- **Kwetsbaarheid (vulnerability)**: escalatiefactor die de risicopartij  gevoelig maakt voor een bepaalde dreiging;
	- *bijv: bug in de software, slechte configuratie, onvoorzichtige gebruiker*
- **(Beheers)maatregel (control)**: reduceert de <a style="color:inherit">waarchijnlijkheid</a>  van een incident en/of de <a style="color:inherit">impact/gevolgen</a> van een incident.
	- *bijv: firewall, awareness-cursus*
- **Impact/Gevolgen**: (negatief) gevolg van een incident in de vorm van schade aan assets.
	– Informatiebeveiliging: impact vaak uitgedruikt in **B**eschikbaarheid, **I**ntegriteit en **V**eiligheid
	– Cybersecurity : Impact omvat ook anderssoortige gevolgen
	- *bijv: Data onbeschikbaar door onvrijwillige encryptie, Staatsgeheimen opwikileaks, Fabriek plat door een succesvolle malware-attack*

---
####  Beveiligingscyclus
![[Pasted image 20230301142809.png]]

- **Preventieve maatregelen (werken voorafgaand aan het incident)**
	- *niet verwarren met proactieve maatregelen, deze neem je ook voorafgaand aan het incident. Maar deze werken pas tijdens of na het incident*
- **Reactieve maatregelen (werken tijdens of na het incident)** 
	- *= detectieve + repressieve (+ correctieve maatregelen)*

---

#### Logische/Organisatorische/Fysieke Maatregelen 
- Voorbeeld: beveiliging webserver:
	- **Logische maatregelen** (ook wel **Digitale maatregelen**):
		- *encryptie in de communicatie, firewall , software up-to-date, acces control voor gebruikers, AV-solution, IDS, Log-Monitoring*
	- **Organisatorische maatregelen**
		- *Beleid wie toegang heeft tot de serverruimte, IAM(Identity and access management voor users, admins, …), SLA’s (Service Level Agreements) over bijvoorbeeld storing en uitwijk, Security awareness, Scholing*
	- **Fysieke maateregelen**
		- *Server in beveiligde serverruimte met bewaking, slot op de deur, cameratoezicht*

**Schematische weergave van maatregelen**
![[Pasted image 20230301143858.png]]

---

### Cybersecurity (week 2)
Voor meer informatie over cryptografie zie [[Aantekeningen Cyber 1]], [[Aantekeningen Cyber 2]] 
#### Inleiding
In week 2 hebben we het gehad over verschillende methodes voor cryptografie. De voorbeelden die besproken worden zijn: Caesar

#### Substitutie 1 : Caesar
[Meer info...](<Aantekeningen Cyber 1>)
Bij Caesar encryptie word er een vaste verschuiving gebruikt zoals te zien in de afbeelding hieronder. In dit voorbeeld wordt er een verschuiving van <span style="color:red">A →  D</span>. Dit is een verschuiving van 3.
**Voorbeeld**
![[Pasted image 20230301153348.png]]

---

#### Substitutie 2: S-box
[Meer info...](<Aantekeningen Cyber 1>)
S-box cryptografie maakt gebruik van een lookup-table zoals hieronder. 
**Voorbeeld**
![[Pasted image 20230301155038.png]]

---

#### Substitutie 3: Poly-alfabetische substitutie: Vignère
[Meer info...](<Aantekeningen Cyber 1>)
In plaats van een vaste verschuiving zoals bij [[#Substitutie 1 : Caesar]] wordt er met meerdere verschuivigen gewerkt, vandaar **Poly-alfabetisch**.
<span style="color:red">Er zijn 26<sup>n</sup> sleutelmogelijkheden bij keylengte n</span>

**Tabel van Vignère**
![[Pasted image 20230301155703.png]]

**Voorbeeld**
– Stel de sleutel is <span style="font-weight:bold">"nse"</span>. De letters geven drie verschillende Caesaroptellingen aan <span style="color:blue">(n=13, s=18, e=4)</span>. Bij de $4^{e}$ letter van de plaintext, wordt opnieuw de eerste optelling gebruikt.
– Plain text is <span style="font-weight:bold">"hallo"</span> (5 tekens) dus de 5 sleutel-rijen zijn **nsens**. Cyphertext is het snijpunt van plaintextletter en bijbehorende sleutelletter
– Dus hallo ⇒ <span style="font-weight:bold">"uspyh"</span>

---

#### Substitutie 4: Enigma
Meerdere rotors substitueren de letters en draaien steeds zelf verder, er is dus weer sprake van **poly-alfabetisch substitutie**

Je kunt dit alleen met de juiste beginstand van de rotors decrypten.

**Schematische weergave van rotors**
![[Pasted image 20230301161254.png]]

---

#### Vernam
Vernam encryptie is [[#Substitutie 3: Poly-alfabetische substitutie: Vignère]] waarbij <a style="color:inherit">legte van de key = lengte plain text</a> 

---

## Routing & Switching

### Routing & Switching (week 1)

- **WAN**
	- "Wide Area Network"
	- ISP (Internet Service Provider)
	- Verbindt netwerken

- **LAN**
	- "Local Area Network"
	- Thuis- of bedrijfsnetwerk
	- Verbindt clients

![[Pasted image 20230306114311.png]]

---

### Netwerk-infrastructuur

1. **Services view**
2. **Components view**
3. **Protocols view**

#### 1. Services view
```
De technische infrastructuur die bekeken vanuit de diensten die geleverd moet worden
```
![[Pasted image 20230306114642.png]]

##### Aspecten
- Fault tolerance
	- Weerbaarheid van een netwerk tegen fouten/uitval 
	- Moet blijven werken bij als een gedeelte uitvalt
- Beschikbaarheid (availability)
	- Beschikbaarheid van de services 
	- Moet blijven werken bij als een gedeelte uitvalt
- Schaalbaarheid (scalability)
- Quality of service 
- Beveiliging (security)
	- Vertrouwelijkheid 
		- De data is niet toegankelijk voor onbevoegden
	- Integriteit 
		- De data verandert niet onderweg
	- Beschikbaarheid
		- Het werkt zoals het zou moeten werken

De belangrijkste manier om Fault tolerance en beschikbaarheid te behouden is redundancy (redundantie). Hierbij heb je een backup voor als de hoofd apparatuur niet werkend is.

---

#### 2. Protocols view
Op een computernetwerk gebruikt software databussen. Maar het daadwerkelijke transport gaat via elektromagnetische golven door bv: *fiber, kabel, ether*.
Netwerk -hardware en Software vertaalt de informatie behoefte van de applicatie naar elektrische signalen die worden verzonden via elektromagnetische golven.
Om dit te doen hebben we <a style="color:inherit">netwerkprotocollen</a> nodig.

**Representatie van Protocols View (Layered View)**
![[Pasted image 20230306115601.png]]
##### Osi model
**Lagen van het OSI model**
![[Pasted image 20230221112047.png]]

Elke laag van het OSI model levert een service aan de laag eronder

###### Voordelen
- Protocollen worden per laag ontwikkeld dus een verandering van een protocol hoeft geen gevolgen op de andere lagen te hebben
- Omdat er een gemeenschappelijke manier van communiceren is zorgt dit voor consistentie in de systemen

---

##### Internet model (TCP-IP model / DOD model)
![[Pasted image 20230306120828.png]]
![[Pasted image 20230306120922.png]]

---

##### Inpakken van data (Encapsulation) 

<a style="color:inherit">Applicatie-laag</a> : produceert data en geeft het door aan de Transport-laag 
<a style="color:inherit">Transport-laag</a>: 
- Deelt data op in segmenten 
- Voegt aan elk segment een <b style="color:khaki">header</b> toe en geeft het door aan de Netwerk-laag 

<a style="color:inherit">Netwerk-laag</a>: Voegt een <b style="color:salmon">header</b> toe em geeft het door aan de Datalink-laag 
<a style="color:inherit">Datalink-laag</a> Voegt een <b style="color:darkseagreen">header</b> en een <b style="color:darkseagreen">trailer</b> toe dit wordt doorgegeven aan de Fysieke laag
<a style="color:inherit">Fysieke Laag</a> Voegt bits toe voor error-correctie
---
In de afbeelding hieronder zie je de Encapsulation en decapsulation van
![[Pasted image 20230306122638.png]]

