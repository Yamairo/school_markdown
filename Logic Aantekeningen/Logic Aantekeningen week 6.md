```toc
```
## Prolog
### Database 
Gegeven de feiten
```prolog
eet(beer,vis)
eet(beer,vos)
eet(beer,gras)
```

Hier kan je mee aangeven dat een beer een vis/vos/gras eet. Dit is een <b style="color:red">afspraak</b>

### Query
```prolog
?eet(beer,vis)
```

Geeft <b style="color:red">yes</b> omdat een beer vis eet volgens de database
```prolog
?eet(beer,X)
```

Geef 
<p style="color:red">vis</p>
<p style="color:red">vos</p>
<p style="color:red">gras</p>
Omdat een beer vis, vos en gras eet
