<a>Binaire representatie/antwoorden worden aangegeven als 1 byte grootte</a>
1. Hoe schrijf je 62 in het binaire talstelsel? 
| 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- |
| 1   | 1   | 1   | 1   | 1   | 0   |
$32 + 16 + 8 + 4+ 2 = 62$

2. Hoe schrijf je $10 {5\over16}$ in het fixed <8, 4> formaat? 
| 8   | 4   | 2   | 1   | $1\over2$ | $1\over4$ | $1\over8$ | $1\over16$ |
| --- | --- | --- | --- | --------- | --------- | --------- | ---------- |
| 1   | 0   | 1   | 0   | 0         | 1         | 0         | 1           |
$8 + 2 + {1\over4} + {1\over16}= 10 {5\over16}$

3. Wat is de representatie van het negatieve getal -120 volgens 2s-complement? 
| -128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| ---- | --- | --- | --- | --- | --- | --- | --- |
| 1    | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 
$-128 + 8 = 120$

4. Gegeven de code 10011001 volgens het bias-systeem. Welk decimaal getal wordt hiermee gerepresenteerd?
 | 128  | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
 | --- | --- | --- | --- | --- | --- | --- | --- |
 | 1   | 0   | 0   | 1   | 1   | 0   | 0   | 1   |
 Som zonder bias $128 + 16 + 8 + 1 = 153$
 Met bias $153 - 128 = 25$

5. Wat is de representatie van het negatieve getal -16 volgens het sign-magnitude systeem?
| S   | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- |
| 1   | 1   | 0   | 0   | 0   | 0    |
$-16_b = 110000$

6. Hoe schrijf je de binaire code 11111001 in het decimale talstelsel? 
7. Gegeven de code 10011001 volgens 2s-complment. Welk decimaal getal wordt hiermee gerepresenteerd? 
8. Wat is de representatie van het negatieve getal -88 volgens het bias-systeem? 
9. Gegeven de code 10011001 volgens fixed <8,2> formaat. Welke breuk wordt hiermee gerepresenteerd? 
10. Gegeven de code 00101001 volgens fixed <8,5> formaat. Welke breuk wordt hiermee gerepresenteerd? 
11. Reken het decimale getal 9,0 om naar enkelvoudige precisie IEEE754. 
12. Reken het decimale getal −8 7 16 om naar enkelvoudige precisie. 
13. Reken het decimale getal 100 19 64 om naar enkelvoudige precisie. 
14. Reken het decimale getal 6,125 om naar enkelvoudige precisie. 
15. Converteer het floating-pointgetal 0x42E48000 naar decimaal. 
16. Converteer het floating-pointgetal 0x3F880000 naar decimaal. 
17. Converteer het floating-pointgetal 0x00800000 naar decimaal. 
18. Converteer het floating-pointgetal 0xC7F00000 naar decimaal. 
19. Wat is de hexadecimale code voor 0,0 bij enkelvoudige precisie? 
20. Wat is de hexadecimale code voor −∞ bij enkelvoudige precisie? 
21. Geef een voorbeeld van hoe NaN kan worden gerepresenteerd als hexadecimale code bij enkelvoudige precisie. Licht je antwoord toe. 
22. Maak een waarheidstabel voor een NAND met 3 ingangen. Noteer ook de bijbehorende formule. 
23. Maak een waarheidstabel voor een NOR met 3 ingangen. Noteer ook de bijbehorende formule. 
24. Maak een waarheidstabel voor een XOR met 3 ingangen. Noteer ook de bijbehorende formule. 
25. Maak een waarheidstabel voor een XNOR met 3 ingangen. Noteer ook de bijbehorende formule. 

Minimaliseer en berekenen 2x de kosten: 
26. $𝑓(𝐴, 𝐵, 𝐶) = ∑ 𝑚(0,2,3,4,6)$ 
27. 𝑓(𝐴, 𝐵, 𝐶) = ∑ 𝑚(1,3,4,5)
28. 𝑓(𝐴, 𝐵, 𝐶,𝐷) = ∑ 𝑚(3,4,6,7,11,12,14,15) 
29. 𝑓(𝐴, 𝐵, 𝐶,𝐷) = ∑ 𝑚(0,2,8,10)