# Asymetrische cryptografie
Problemen met MAC zijn dat je vooraf de key moet uitwisselen anders kan je de encryptie niet decrypten.
```mermaid
flowchart TD
1[SUB] --- 2[Shift row] --- 3[Mix column] --- 4[xor]
key --- 5[gen] --- subkey --- 4
```


### Cryptografie gebasseerd op getaltheorie
Je neemt een getal bijvoorbeeld 91 wat zijn $a\cdot{b}=91$. Dit is lastig snel te bedenken en benodigd brute force om tot het antwoord $17\cdot{3}=91$ te krijgen.

### Machtsverheffen & Grote getallen
Bij het gebruik van machtsverheffen krijg je grote getallen wat tot overflows kaan leiden.

### Reeks en herhalen
$\mathbb{Z}_{n}$ waarbij n de limiet is van het getalruimte gaat via de natuurlijke getallen. $\mathbb{N}={1,2,3,4,5,...}$. Stel je neemt $\mathbb{Z}_{7}={1,2,3,4,5,6}$ dan wordt de reeks.
```mermaid
flowchart LR
1[3] --> 2[2] --> 3[6] --> 4[4] --> 5[5] --> 6[1] --> 7[3] -->8[6]
```

En dan herhaald het.

### Diffie Helmann Key Exchange
```mermaid
sequenceDiagram
Alice-)Bob: A, G, P
Bob-)Alice: X
```

$B^{x}=(g^{y})^{x}=g^{yx}$

## Certificaat keten


