# Inhoudsopgave
```toc
```

## Dubbelzinnig
Bij dubbelzinnigheid is de intentie van de opgave niet correct begrepen door de uitvoerder, waardoor een ander resultaat dan gevraagd wordt geleverd.

### Krantenkoppen
Een goed voorbeeld hiervan zijn krantenkoppen want deze zijn vaak misleidend.

## Ambiguïteit
- Ook in de <span style="color:blue;:">software-ontwikkeling</span> speelt <span style="color:blue">ambiguïteit </span> een rol.
  
## Preconditie
Bij programmeren is de <p style="color:red">preconditie<p> een voorwaarde die *altijd waar moet zijn*.  

$$
I \epsilon \mathbb{N} \land j \epsilon \mathbb{N}
$$

## PoC (Proof of Correctness)

Met gebruik van Hoare calculus kijken we of de inputvariabelen voldoen aan de preconditie.

Programma P is alleen correct als deze implicatie correct is


1. 
$$
\color{red}{(\forall X)[I (X \rightarrow O (X, Y)] }
$$ ^e43eed ^e1fd27

### Hoare Tripple **
![Formule 1](#^e1fd27)

Wordt in de Hoare Tripple gegeven als

<span style="color:blue;:">{I} P {O}</span>
I is de Preconditie van P

$I \land P \rightarrow O$

Dit geld alleen als:
- Preconditie I voldoet
- Dit moet na het uitvoeren van P
- Ook moet de postconditie (O) voldoen

---

## Een rij predicaten
$$
{R_{0}=\color{red}{I}}
$$

$$
S_0
$$

$$
{R_{1}}
$$

$$
S_1
$$

$$
R_{n}=\color{red}{O}
$$

---
Deze russenstappen kan je controleren door <span style ="color:blue">bottom up te werken</span>

--- 

## Voorbeelden

### Voorbeeld 1

$$
\color{red}{x>10}
$$

$$
x = x - 4;
$$

$$
\color{red}{x>6}
$$

In de postconditie word $x=x-4$ in de formule gestopt
Dus
$$
\color{red}\{x - 4>6\} \iff \{x>10\}
$$

### Voorbeeld 2
$x = x+y$
$y = x - y$
$x = x-y$<br>
*Kan je met deze formules de waarde van x en y omdraaien?*
**Stel** <span style="color:blue">x = 30 en y = 10</span>
$x = x+y$ dus $x = 40$ en $y = 10$
$y = x - y$ dus $x = 40$ en $y = 30$
$x = x-y$ dus $x = 10$ en $y = 30$<br>
In dit geval werkt het maar dit bewijst niet dat het voor alles geldt

---
$x = x+y$
$y = x - y$
$x = x-y$

### Voorbeeld 3
```c
x = 4
if x<5:
		y =x-1
else:
		y = 7
```
Hieruit volgt dat y = 3.