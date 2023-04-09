```toc
```

## Logic

$S(x)$ staat voor "x is een student"
$I(x)$ staat voor "x is intelligent"
$M(x)$ staat voor "x houdt van muziek"

1. Alle studenten zijn intelligent 
   $(\forall x)(S(x)\rightarrow I(x))$
2. Sommige intelligente studenten houden van muziek
   $(\forall x)[((S(x)\land I(x))\rightarrow M(x))]$
3. Iedereen die van muziek houdt is een niet intelligente student
   $(\forall{x})(M(x)\rightarrow (\neg{I(x)}\land S(x)))$


   $(\forall{x})[P(x)\land Q(x)]\rightarrow (\exists x)[P(x)\land Q(x)]$

$(\exists x)[P(x) \rightarrow Q(x)]$ $\color{red}{\rightarrow}$ $(\forall x)P(x)\rightarrow (\exists x)Q(x)$
1. $(\exists x)[P(x) \rightarrow Q(x)]$ hypothese
2. $(\forall{x} )P(x)$ deductiehypothese
3. $P(a)\rightarrow Q(a)$ 1, Existentiële Instantiatie
4. $P(a)$ 2, Universele Instantiatie 
5. $Q (a)$ 3,4 Modus Ponens
6. $(\exists x)Q(x)$ Existentiële generalisatie

$(\forall{x})(\exists y)Q(x,y)\rightarrow (\exists x)(\forall y) Q(x,y)$

---
1. Wat moet volgens de ‘assignment regel’ de preconditie zijn van het onderstaande codefragment?
{preconditie}
	$x = x + 1;$
{$x = y - 1$}

$x = y - 2$

2. Wat moet volgens de ‘assignment regel’ de preconditie zijn van het onderstaande codefragment? 
{preconditie} 
	x = 2 * x; 
{x > y}

$2 \cdot x > y$
$x > \frac{1}{2}y$

3.  Wat moet volgens de ‘assignment regel’ de preconditie zijn van het onderstaande codefragment? 
{preconditie} 
	x = 3 * x - 1;
{x = 2 * y – 1}



4.  Wat moet volgens de ‘assignment regel’ de preconditie zijn van het onderstaande codefragment? 

{preconditie} 
	y = 3 * x + 7; 
{y = x + 1}

5. Verifieer de correctheid van het onderstaande codefragment. 
{x = 1} 
	y = x + 3; **(y=4)**
	y = 2 * y; **(y=8)**
{y = 8}

6. Verifieer de correctheid van het onderstaande codefragment. 
{x > 0}
	y = x + 2; y > 2, want x is groter dan 0 en hier tel je 2 bij op
	z = y + 1; z > 3, want y is groter dan 2 en hier tel je 1 bij op
{z > 3}

7. Verifieer de correctheid van het onderstaande codefragment. 
   {x < 8} 
	   z = x - 1; x < 8
	   y = z - 5; z <7
   {y < 2}


8. Verifieer de correctheid van het onderstaande codefragment. 
 ```c
y = 0 
	   if (y < 5) // 0 < 5
		   y = y + 1; // y = 0 + 1 = 1
	   else y = 5; 
```
Dus, y = 1, want y is kleiner dan 5

9. Verifieer de correctheid van het onderstaande codefragment. 
   ```c
{x = 7} 
	   if (x <= 0) // x !<= 0
		   y = x; 
	   else 
		   y = 2 * x; // y = 2 * 7 = 14
```
   Dus y = 14 want x is groter dan 0

10. Verifieer de correctheid van het onderstaande codefragment. 
    ```c
{x ≠ 0} 
	    if (x > 0) //x != 0 dus als x > 0
		    y = 2 * x; // word y > 0
		else //x != 0 dus als x < 0
			y = -2 * x; // word y > 0
```
	{y > 0}

| 8   | 4   | 2   | 1   | 1/2 | 1/4 | 1/8 |
| --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   |     |     |     |     |     |
