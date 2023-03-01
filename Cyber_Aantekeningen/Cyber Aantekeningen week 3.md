```toc
```
## Cyptografische methoden
### Oplossing 1: CBC-mode
![[Pasted image 20230223090245.png]]

### Oplossing 2: CTR (counter) mode

![[Pasted image 20230223090228.png]]

---

De volgende voorbeelden van cryptografie gaan alleen over de bescherming van integriteit

## Eerste poging tot cryptografie ter bescherming van integriteit 
![[integriteit.canvas]]
Stel Alice stuurt een bericht naar Bob, het gele blok representeert een encryptie en het rode blok een decryptie, zal het bovenstaande bericht hetzelfde zijn als de onderstaande en hoe doen we dit.

## Conclusie
- Het 2 x verzenden van (geëncrypt onencrypt) bericht is niet efficient en garandeert onvoldoende integriteit 
- Dit is op te lossen door de plaintekst en de geeëcrypte hash te sturen
- Deze 'hash' moet wel bepaalde eisen voldoen
Je kunt hierbij een MAC (Message Authentication Code) geven om het berichte te authenticaten

---

## Random oracle
![[random_oracle.canvas]]
Bij een random oracle wordt er een random hash teruggegeven maar deze zal altijd dezelfde random hash zijn. Dit zou een optimale hash zijn.

---

## Bekende hashfuncties
| hashfuncties | hashlengte | status (2019) |
| ------------ | ---------- | ------------- |
| MD 5         | 128 bit    | onveilig      |
| SHA 1        | 160 bit    | onveilig      |
| SHA 2 (256)        | 256 bit    | veilig        |
| SHA 2 (512)        | 512 bit    | veilig        |
| Sha 2 (1024)        | 1024 bit   | extreem veilig              |

---

## Toepassing 1 : Authenticatie met een hash
De gebruiker maakt een hash van een password, de server controleert deze en als de hashes overeenkomen dan krijgt de gebruiker toegang
![[hash.canvas]]

## Toepassing 2:  MAC
MAC kan leiden tot dubbele hashes dus dit is daarom minder handig

---
