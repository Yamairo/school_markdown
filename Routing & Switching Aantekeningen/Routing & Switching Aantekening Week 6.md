---
datum : 21-03-2023
---

```toc
```

## VTP (VLAN Trunking protocol)
Er is hier geen sprake van daadwerkelijke Trunking maar het maakt verbindingen tussen databases makkelijker. 

### VTP Modes
---

#### Client Mode

#### Server Mode

#### Transparant Mode
Het is aanwezig maar niet zichtbaar dus *Transparant*.

---
### Pruning
Met pruning haal je onnodige netwerken weg


---

## DHCP
Het gevaar met DHCP is dat iedereen hier berichten naar kan sturen, en deze ook kan intercept-en als [[MITM]] .

![[Pasted image 20230321110905.png]]

### DHCP Relay
Door het gebruik van **Helper adressen** op tussenliggende routers zal deze DHCP broadcasts doorsturen.

---

## First Hop redundancy Protocols
1. HSRP
	- Cisco proprietary
2. VRRP
	- IEEE Standard
	- Similar to HSRP
	- Niet daadwerkelijk tussen routers gebruiken
3. GLHP