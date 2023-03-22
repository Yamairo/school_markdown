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
	2. $P(a) \rightarrow Q(a)$ Universele Instantiatie
	3. $(\forall{x})P(x)$ Universele Generalisatie
	4. $P(a)$ 
	5. $Q(a)$ 
	6. $(\exists{x})Q(x)$ Existientiële Generalisatie 
