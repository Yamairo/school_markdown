```toc
```
## Opdracht 3
1. **VRAAG**: Geef de PARI-routine:
   ```
   Mod(22, 37)
   Mod(16, 37)
   Mod(0, 37)
   Mod(2, 37)
   Mod(16, 37)
   Mod(1, 37)
   Mod(16, 37)
   Mod(14, 37)
   Mod(13, 37)
   Mod(25, 37)
   Mod(21, 37)
   Mod(31, 37)
   Mod(1, 37)
   Mod(6, 37)
   Mod(22, 37)
   Mod(33, 37)
   Mod(16, 37)
   Mod(5, 37)
   ```
2. **VRAAG**: Hoeveel vermenigvuldigingen zijn er uitgevoerd?
      > 18
3. **VRAAG**: Bereken de bovenstaande tussenantwoorden (Stap 1) en bepaal nu uit de antwoorden op een slimme manier 1319 (Stap 2).
   ```
   gp > a = Mod(13,37); b=a*a; c=b*b; d=c*c; e=d*d; print(e * b * a)
   ``` 
4. **VRAAG**: Hoeveel vermenigvuldigingen waren er in totaal nodig?
   > 3 vermenigvuldigingen 
5. **VRAAG**: Hoe denk je dat het binnen PARI is uitgerekend?
   > Door een versimpeling van de machtsverheffing

---

## Opdracht 4
1. **VRAAG**: Geef de gekozen a en b: a= b=
   > a = 23, b = 21
2. **VRAAG**: Geef de mogelijke minimum en maximum waarde voor een zinvolle a en b en leg uit waarom.
   > Een mogelijk minimum zou 13 zijn omdat dit de generator is en het maximum 37 omdat dit het priemgetal is.
3. **VRAAG**:: Geef de gekozen A=13a en B=13b (in Z37 * ):
   > A = 2, B = 23
4. **VRAAG**: Waarom is deze berekening altijd snel uit te voeren door Alice en Bob?
   > Omdat Z 37 een relatief kleine berekening is voor computers
5. **VRAAG**:: Hoe zou je a of b kunnen terugrekenen uit de berekende publieke getallen? Geef ook aan of dat lastig is in verhouding tot (Indisch) machtsverheffen.
   > Je zou dit kunnen doen door het te brute forcen maar dit kan lang duren. Dit is een stuk lastiger dan Indisch machtsverheffen omdat je hier al weet waar je naartoe werkt.
6. **VRAAG**: Wat is de session key en geef de formule waarmee deze is uitgerekend en check deze in PariGP?
   > De session key is **29** 
7. **VRAAG**:: Wat kun je met het Diffie Hellman protocol?
   > Je kan een gedeelde geheime key maken tussen mensen die elkaar nog niet eerder hebben ontmoet

---

## Opdracht 5
1. **VRAAG**: Wat is de modulus N (=p x q) :
   > 31571
2. **VRAAG**: Wat zijn de public en private keys:
   > Private : 21473
   > Public : 2^16+1
3. **VRAAG**:: Ga terug naar Pari GP en voer de volgende acties uit. 
   Tekenen
   $signature = Mod(hash, N)^{Kpriv}$
   Controle
   $hash = hash = Mod(signature, N)^{Kpub}$
   >Tekenen
   ```
   gp > signature = Mod(69,31571)^21473;
   Mod(7907, 31571)
   ```
   >Controle
   ```
    gp > b=2^16+1;hash = Mod(signature, 31571);
    Mod(7907, 31571)
   ```
4. **VRAAG**: Waarom is de signature onweerlegbaar bij RSA?
   > Omdat alleen de verzender de private key heeft zal dit onweerlegbaar zijn
   
