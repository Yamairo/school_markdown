1. Gegeven de volgende predicaten: 
	– $M(x):x$ is man
	–  $V(x):x$ is vrouw
	–  $L(x):x$ is lang
	Vertaal onderstaande uitspraken als een predicaat-wff
	1. Alle mannen zijn lang.
	   $$(\forall{x})(M(x) \rightarrow L(x))$$
	2. Sommige vrouwen zijn lang.
	   $$(\exists{x})(V(x) \land L(x))$$
	3. Alle mannen zijn lang maar geen enkele vrouw is lang.
	   $$(\forall{x})(M(x) \rightarrow L(x)) \land (\forall{x})(V(x) \rightarrow \neg L(x))$$
	4. Alleen vrouwen zijn lang.
	   $$(\exists{x})(V(x) \rightarrow L(x))\land (\forall{x} )(M(x) \rightarrow \neg{L(x)})$$
	5. Als iedere man lang is, dan is iedere vrouw ook lang.
	   $$(\forall{x})(M(x)\rightarrow L(x))\rightarrow (V(x) \rightarrow L(x))$$
2. Gegeven de volgende predicaten:
	– $M(x):x$ is man
	–  $V(x):x$ is vrouw
	–  $W(x, y):x$ x werkt voor y
	Vertaal onderstaande uitspraken als een predicaat-wff
	1. $(\exists{x})(V(x)\land (\forall{y})(M(y)\rightarrow \neg W(x,y)))$
	   >Er is een vrouw die niet werkt voor een man
	2. $(\forall{x})[M(x)\rightarrow (\exists{y})(V(y)\land W(x,y))]$
	   >Alle mannen werken voor een vrouw
	3. $(\forall{x})[M(x)\rightarrow (\forall{y})(W(x,y)\rightarrow V(y))]$
	   >Als een man voor iemand werkt dan is het een vrouw
	4. $(\forall{x})(\forall{y})(M(x)\land W(y,x)\rightarrow V(y))$
	   >Als iemand een man is en voor iemand anders werkt dan moet dit een vrouw zijn.
3. Geef in het onderstaande redeneerschema aan welke regels er gebruikt zijn om de geldigheid aan te tonen van het argument:
   $(\exists{x})[P(x)\rightarrow Q(x)]$ $\color{red}{\rightarrow}$$[(\forall{x})P(x)\rightarrow (\exists{x} )Q(x)]$ 
	1. $(\exists{x} )[P(x) \rightarrow Q(x)]$ Hypothese
	2. $P(a) \rightarrow Q(a)$ 1, Universele Instantiatie
	3. $(\forall{x})P(x)$ Hypothese
	4. $P(a)$ 3, Universele Instantiatie 
	5. $Q(a)$ 2, 4 Modus Ponens
	6. $(\exists{x})Q(x)$ 5, Existientiële Generalisatie 
4. Geef in het onderstaande redeneerschema aan welke regels er gebruikt zijn om de geldigheid aan te tonen van het argument:
   $(\exists{x})P(x)\land (\forall{x})(P(x)\rightarrow Q(x))$ $\color{red}{\rightarrow}$$(\exists{x})Q(x)$
	1. $(\exists{x} )(P(x))$ Hypothese
	2. $(\forall{x})(P(x)\rightarrow Q(x))$ Hypothese
	3. $P(a)$ 1, Existientiële Generalisatie 
	4. $P(a)\rightarrow Q(a)$ 2, Universele Instantiatie 
	5. $Q(a)$ 3,4 Modus Ponens
	6. $(\exists{x})Q(x)$ 5, Existientiële Generalisatie
5. Gegeven de wff $(\forall y)(\exists x)Q(x,y) \rightarrow (\exists x)(\forall y)Q(x,y)$
	1. Bedenk een interpertatie (= een tegenvoorbeeld) waaruit blijkt dat deze wff niet geldig is.
	   >Stel x is een mens en y is het aantal personen dat je kent. Dan zou er worden gezegd dat er een persoon is die iedereen kent wat niet kan.
	2. Ontdek de fout in het onderstaande redeneerschema. Licht je antwoord toe.
		1.  $(\forall y)(\exists x)Q(x, y)$
		2.  $(\exists x)Q(x, y)$ 1, ui
		3.  $Q(a, y)$ 2, ei
		4.  $(\forall y)Q(a, y)$ 3, ug
		5.  $(\exists x)(\forall y)Q(x, y)$ 4, eg
	   In stap 1 naar 2 wordt er vanuit gegaan dat $((\forall y)(\exists x)Q(x, y))$$\color{red}{\rightarrow}$$(\exists x)Q(x, y)$ maar dit klopt niet.
6. Bewijs met behulp van een redeneerschema de geldigheid van het argument  $(\forall x)P(x)$ $\color{red}{\rightarrow}$ $(\forall x)[P(x) \lor Q(x)]$
	1. $(\forall x)P(x)$ Hypothese 
	2. $P(t)$ 1, Universele Instantiatie 
	3. $P(t) \lor Q(a)$ 2, Additie of toevoeging
	4. $(\forall x)[P(x) \lor Q(x)]$ 3, 4 Universele Generalisatie
7. Bewijs met behulp van een redeneerschema de geldigheid van het argument  $(\exists x)(\exists y)P(x,y)$$\color{red}{\rightarrow}$$(\exists y)(\exists x)P(x,y)$
	1. $(\exists x)(\exists y)P(x,y)$ Hypothese
	2. $(\exists{y})P(a,y)$ 1, Existientiële Instantiatie 
	3. $P(a,b)$ 2, Existientiële Instantiatie 
	4. $(\exists x)P(x,b)$ 3, Existientiële Generalisatie 
	5. $(\exists y)(\exists x)P(x,y)$ Existientiële Generalisatie 
	   
