```prolog
eet(beer, vis) 
eet(vis, plankton) 
eet(plankton, zeewier) 
eet(wasbeer, vis) 
eet(beer, wasbeer) 
eet(beer, vos) 
eet(vos, konijn) 
eet(konijn, gras) 
eet(beer, hert) 
eet(hert, gras) 
eet(wilde_kat, hert) 

dier(beer) 
dier(vis) 
dier(plankton) 
dier(wasbeer) 
dier(vos) 
dier(konijn) 
dier(hert) 
dier(wilde_kat) 

plant(gras) 
plant(zeewier) 

prooi(X) <= eet(Y, X) and dier(X)
```
1. 
   ```prolog
   ?dier(wilde_kat)
   ```
   > yes
   
2.  
   ```prolog
   ?plant(wasbeer)
   ```
   > no

3.  
   ```prolog
   ?eet(beer, plankton)
   ```
   > no
   
4.  
   ```prolog
   ?eet(vos, konijn)
   ```
   > yes

5.  
   ```prolog
   ?eet(wasbeer, X)
   ```
   > X = vis, want eerder was aangegeven dat de wasbeer vis eet

6. 
   ```prolog
   ?eet(X, gras) 
   ```
   > X = konijn en X = hert, want eerder was aangegeven dat het hert en het konijn gras eten

7. 
   ```prolog
   ?eet(beer, X) and eet(X, konijn)  
   ```
   > Vos want een vos wordt gegeten door een beer en de vos eet een konijn
   
8. 
   ```prolog
   ?prooi(X) and not eet(vos, X)  
   ```
   > Er komt hier vis, plankton, vos, hert uit omdat deze allemaal gegeten kunnen worden maar geen konijn zijn.
   
Schrijf vervolgens zelf een nieuwe regel voor de database die “herbivoor” wordt genoemd. <a style="color:inherit">Een herbivoor is een planteneter</a>. Geef daarna het resultaat van de query:
9. 
   ```prolog
   ?herbivoor(X)  
   ```
> Dit is mijn query
```prolog
herbivoor(X) ⇐ eet (X, Y) and plant (Y)  
   ```
> Hieruit krijg je bij X de dieren die planten eten, dit zijn plankton, konijn, hert

Voeg de volgende feiten aan de database toe: dier(wolf), eet(wolf, vos) en eet(wolf, hert). Voeg ook de regel voedselketen(X, Y) toe volgens voedselketen(X, Y) ⇐  eet(X, Y) voedselketen(X, Y) ⇐  eet(X, Z) and voedselketen(Z, Y)
10.  
```prolog
   ?voedselketen(wolf, X)  
   ```
> Hieruit volgt
```prolog
   voedselket(wolf, vos) yes
	voedselket(wolf, hert) yes
	voedselket(wolf, konijn) yes
	voedselket(wolf, gras) yes
	voedselket(wolf, gras) yes  
   ```