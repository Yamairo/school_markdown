 **Inhoudsopgave**
```toc
```
### A1: IEEE-754 floating point standaard voor enkelvoudige precisie.
Converteer op papier de volgende twee decimale getallen naar floating point enkelvoudige precisie. Gebruik daarbij het stappenplan zoals is uitgelegd in hoorcollege 1.
1. 8,5
2. $-12{11\over16}$

## 1.
1. Tekenbit = 0 
2. 8,5 = %1000.1 = 1.0001 x 23 
3. Exp = 3 + 127 = 130 = 100000102 
4. 0100 0001 0000 1000 0000 0000 0000 0000
5. 4 1 0 8 0 0 0 0 6. 0 x 41080000


## 2.
1. Tekenbit = 1
2. -1211 16 = %1100.1011 = 1.1001011 x 23 
3. Exp = 3 = 127 = 130 = 100000102 
4. 1100 0001 0100 1011 0000 0000 0000 0000
5. C 1 4 B 0 0 0 0 6. 0 x C14B0000


Converteer de volgende floating point enkelvoudige precisie codes naar een decimaal getal geschreven als breuk. Gebruik daarbij het stappenplan zoals is uitgelegd in hoorcollege 1.
1. 0 × 41A60000
2. 0 × C16A0000 PDATR

# 1.
1. 0100 0001 1010 0110 0000 0000 0000 0000 
2. Tekenbit = 0 = positief 
3. Exp = 100000112 = 131 -127 = 4 
4. Frac = 01001100000000000000000 = 1.010011 
5. $1.010011 x 2 4 = 10100.11 = 20 \frac{3}{4}$
# 2.
1. 1100 0001 0110 1010 0000 0000 0000 0000 
2. Tekenbit = 1 = negatief 
3. Exp = 100000102 
4. Frac = 110101000000000000000000 = 1.1101010 
5. $1.1101010 x 23 = 1110.1010 = 14 \frac{5}{8}$

### A2: Circuit minimaliseren I. 

| A   | B   | C   | Q   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 1   |
| 0   | 0   | 1   | 1   |
| 0   | 1   | 0   | 1   |
| 0   | 1   | 1   | 0   |
| 1   | 0   | 0   | 0   |
| 1   | 0   | 1   | 1   |
| 1   | 1   | 0   | 0   |
| 1   | 1   | 1   | 0   |

1. $Q = \overline{a} \cdot \overline{b} \cdot \overline{c} + \overline{a} \cdot \overline{b} \cdot {c} + \overline{a} \cdot {b} \cdot \overline{c} + {a} \cdot \overline{b} \cdot {c}$ 
2. Na simulatie volgt dit circuit
   ![[Pasted image 20230409103819.png]]
3. $K[Q] = [3+3+3+3]+4=16$
4. Zie tabel 

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ | 00  |                     01                     | 11  | 10  |
| ------------------------------------------ |:---:|:------------------------------------------:|:---:|:---:|
| 0                                          |  1  | <div style="background-color:lime">1</div> |  0  |  1  |
| 1                                          |  0  | <div style="background-color:lime">1</div> |  0  |  0  |

| A   | B             | C   |
| --- | ------------- | --- |
| 0   | 0             | 1   |
| 1   | 0             | 1   |
| -   | $\overline B$ | $C$ | 

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ |                       00                        |                       01                        | 11  | 10  |
| ------------------------------------------ |:-----------------------------------------------:|:-----------------------------------------------:|:---:|:---:|
| 0                                          | <div style="background-color:lightblue">1</div> | <div style="background-color:lightblue">1</div> |  0  |  1  |
| 1                                          |                        0                        |                        1                        |  0  |  0  |

| A              | B   | C             |
| -------------- | --- | ------------- |
| 0              | 1   | 0             |
| 0              | 0   | 0             |
| $\overline{A}$ | -   | $\overline C$ | 


$Q'=\overline{B} \cdot C + \overline{A} \cdot \overline{C}$


5. $k[Q']=[2+2]+2=6$
6. Formule 
   ![[Formule.png]] p
   Circuit
   ![[Circuit.png]]

### A3: Circuit minimaliseren II.

| A   | B   | C   | D   | Q   |
| --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   |
| 0   | 0   | 0   | 1   | 1   |
| 0   | 0   | 1   | 0   | 0   |
| 0   | 0   | 1   | 1   | 0   |
| 0   | 1   | 0   | 0   | 0   |
| 0   | 1   | 0   | 1   | 1   |
| 0   | 1   | 1   | 0   | 0   |
| 0   | 1   | 1   | 1   | 0   |
| 1   | 0   | 0   | 0   | 1   |
| 1   | 0   | 0   | 1   | 1   |
| 1   | 0   | 1   | 0   | 0   |
| 1   | 0   | 1   | 1   | 0   |
| 1   | 1   | 0   | 0   | 1   |
| 1   | 1   | 0   | 1   | 1   |
| 1   | 1   | 1   | 0   | 0   |
| 1   | 1   | 1   | 1   | 0   |

1. $Q = \overline{a} \cdot \overline{b} \cdot \overline{c} \cdot {d} + \overline{a} \cdot {b} \cdot \overline{c} \cdot {d} + {a} \cdot \overline{b} \cdot \overline{c} \cdot \overline{d} + {a} \cdot \overline{b} \cdot \overline{c} \cdot {d} + {a} \cdot {b} \cdot \overline{c} \cdot \overline{d} + a \cdot b\cdot \overline{c} \cdot d$ 
3. $K[Q] = [4+4+4+4+4+4]+6=30$
4. Zie tabel 

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ | 00  | 01                                              | 11  | 10  |
| ------------------------------------------ | --- | ----------------------------------------------- | --- | --- |
| 00                                         | 0   | <div style="background-color:lightblue">1</div> | 0   | 0   |
| 01                                         | 0   | <div style="background-color:lightblue">1</div> | 0   | 0   |
| 11                                         | 1   | <div style="background-color:lightblue">1</div> | 0   | 0   |
| 10                                         | 1   | <div style="background-color:lightblue">1</div> | 0   | 0   |

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ | 00                                         | 01                                         | 11  | 10  |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | --- | --- |
| 00                                         | 0                                          | 1                                          | 0   | 0   |
| 01                                         | 0                                          | 1                                          | 0   | 0   |
| 11                                         | <div style="background-color:lime">1</div> | <div style="background-color:lime">1</div> | 0   | 0   |
| 10                                         | <div style="background-color:lime">1</div> | <div style="background-color:lime">1</div> | 0   | 0   |


1100
1000
1101
1001

---
1-0- is ${a} \cdot \overline{c}$

0101
0001
1101
1001

---
--01 is $\overline{c} \cdot {d}$

$Q'={a} \cdot \overline{c} + \overline{c} \cdot {d}$

5. $k[Q']=[2+2]+2=6$
6. Circuit
   ![[Cuircuit 2.png]]
Zoals je in in het circuit ziet komen de not en de and gates overeen met de vergelijking
