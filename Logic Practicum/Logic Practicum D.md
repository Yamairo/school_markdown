```toc
```
## Opdracht 1
${A}\land{B}\rightarrow{B}$

| A   | B   | $A\rightarrow{B}$ |
| --- | --- | ----------------- |
| F   | F   | T                 |
| F   | T   | T                 |
| T   | F   | T                 |
| T   | T   | T                 |

Omdat de laatste kolom uit allemaal enen bestaat is dit een tautologie 

## Opdracht 2

$({A}\lor{B})\land\neg{A}\rightarrow{B}$

| A | B | ¬A | A ∨ B | (A ∨ B) ∧ ¬A | (A ∨ B) ∧ ¬A → B |
|---|---|----|-------|--------------|------------------|
| 0 | 0 | 1  | 0     | 0            | 1                |
| 0 | 1 | 1  | 1     | 0            | 1                |
| 1 | 0 | 0  | 1     | 0            | 1                |
| 1 | 1 | 0  | 1     | 1            | 1                |

Omdat de laatste kolom uit allemaal enen bestaat is dit een tautologie 

## Opdracht 3
Het bestand is corrupt of de processor is niet snel, of de printer is niet langzaam.

## Opdracht 4
Olieverfschilderijen AND (van Gogh OR Rembrandt) NOT Vermeer

## Opdracht 5
*  a
	- Als je $\neg{A}$ hebt dan zal je voor $A=1, 1-1=0$ krijgen wat false is en dit klopt met de verwachting 
	- Als je $A\land{B}$ hebt dan zal er een true waarde zijn als A en B true zijn hierom kan je het minimum pakken want als een, of meer, van de twee false is dan zal de waarde false zijn.
	- Als je $A\lor{B}$ hebt dan zal er een true waarde teruggegeven worden als een van de twee true is hierom kan je het maximum pakken want als er een, of meer, true is dan zal de waarde true zijn.
- b 
	- De kans is dan $1.00-0.12=0.88$
- c
	- De kans is dan $0.84$ want je moet de hoogste kans pakken
-  d
	- De kans is dan $0.16$ want je moet de hoogste kans pakken en in dit geval $1-0.84=0.16$

   ## Opdracht 6
   Alle computers zijn geïnfecteerd, want als D geïnfecteerd is dan is C het ook. Als C geïnfecteerd is dan is A het ook. En als A geïnfecteerd is en C ook dan moet B dus ook geïnfecteerd zijn.
   
   ## Opdracht 7
   Nee want als A waar is en B niet, of B waar is en A niet, dan zal alsnog opdracht_1 worden uitgevoerd