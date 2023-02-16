 **Inhoudsopgave**
```toc
```
### A1: IEEE-754 floating point standaard voor enkelvoudige precisie.
Converteer op papier de volgende twee decimale getallen naar floating point enkelvoudige precisie. Gebruik daarbij het stappenplan zoals is uitgelegd in hoorcollege 1.
1. 8,5
2. $-12{11\over16}$

## 1.

$8,5 = 1. 000100\cdot2^3$

| 8   | 4   | 2   | 1   | 1/2 | 1/4 | 1/8 |
| --- | --- | --- | --- | --- | --- | --- |
| 1   | 0   | 0   | 0   | 1   | 0   | 0   | 

#### Exponent

$127 + 3 = 130$

| Delen | Resultaat | Overblijfsel |
| ----- | --------- | ------------ |
| 130/2 | 65        | 0            |
| 65/2  | 32        | 1            |
| 32/2  | 16        | 0            |
| 16/2  | 8         | 0            |
| 8/2   | 4         | 0            |
| 4/2   | 2         | 0            |
| 2/1   | 1         | 0            |
| 1/2   | 0         | 1            |

130 = 10000010 

#### Mantissa

$8,5 = 1. 000100\cdot2^3$
Mantissa = 000100

#### Binair

| 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  | 16  | 17  | 18  | 19  | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |

|21  | 22  | 23  | 24  | 25  | 26  | 27  | 28  | 29  | 30  | 31  | 32  | 
|--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |

$8,5 = 01000001000010000000000000000000_{2}$

## 2.

$-12{11\over16} = 1100.1011$

| 8   | 4   | 2   | 1   | 1/2 | 1/4 | 1/8 | 1/16 |
| --- | --- | --- | --- | --- | --- | --- | ---- |
| 1   | 1   | 0   | 0   | 1   | 0   | 1   | 1    |

#### Exponent

$-12{11\over16} = 1.1001011\cdot2^3$
$127 + 3 = 130$

| Delen | Resultaat | Overblijfsel |
| ----- | --------- | ------------ |
| 130/2 | 65        | 0            |
| 65/2  | 32        | 1            |
| 32/2  | 16        | 0            |
| 16/2  | 8         | 0            |
| 8/2   | 4         | 0            |
| 4/2   | 2         | 0            |
| 2/1   | 1         | 0            |
| 1/2   | 0         | 1            |

130 = 10000010

#### Mantissa

$-12{11\over16} = 1.1001011\cdot2^4$
Mantissa = 1001011

#### Binair

| 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  | 16  | 17  | 18  | 19  | 20  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 1   | 0   | 0   | 1   | 0   | 1   | 1   | 0   | 0   | 0   | 0   |

|21  | 22  | 23  | 24  | 25  | 26  | 27  | 28  | 29  | 30  | 31  | 32  | 
|--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |

$12{11\over16} = 11000001010010110000000000000000_{2}$

Converteer de volgende floating point enkelvoudige precisie codes naar een decimaal getal geschreven als breuk. Gebruik daarbij het stappenplan zoals is uitgelegd in hoorcollege 1.
1. 0 × 41A60000
2. 0 × C16A0000

# 1.

0 × 41A60000 
1. 0100 0001 1010 0110 0000 0000 0000 0000
2. Sign = 0, dus positief
3. Exponent = 1000 0011 = 131 - 127 = 4
4. Breuk = 0100 0011= 1.010011
5.  $1.010011 \cdot 2^{4}= 10100.11 = 20{3\over4}$

# 2.

0 × C16A0000
1. 1100 0001 0110 1010 0000 0000 0000 0000
2. Sign = 1, dus negatief
3. Exponent = 1000 0010 = 130 - 127 = 3
4. Breuk = 1101 0100= 1.11010100
5.  $1.11010100 \cdot 2^{4}= 1110.10100 = 14{5\over8}$

### A2: Circuit minimaliseren I. 

| A   | B   | C   | Q   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 1   |
| 0   | 0   | 1   | 1   |
| 0   | 1   | 0   | 1   |
| 0   | 1   | 1   | 1   |
| 1   | 0   | 0   | 1   |
| 1   | 0   | 1   | 1   |
| 1   | 1   | 0   | 1   |
| 1   | 1   | 1   | 0   |

1. $Q = \overline{a} \cdot \overline{b} \cdot \overline{c} + \overline{a} \cdot \overline{b} \cdot {c} + \overline{a} \cdot {b} \cdot \overline{c} + {a} \cdot \overline{b} \cdot {c}$ 
2. ![[screenshot 1.png]]
3. $K[Q] = [3+3+3+3]+4=16$
4. Zie tabel 

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ | 00  | 01  | 11  | 10  |
| ------------------------------------------ | --- | --- | --- | --- |
| 0                                          | 1   | 1   | 0   | 1   |
| 1                                          | 0   | 1   | 0   | 0    |

001
101

---
-10 is $\overline{b} \cdot c$

000
010

---
0-0 is $\overline{a} \cdot \overline{c}$

$Q'=\overline{b} \cdot c + \overline{a} \cdot \overline{c}$


5. $k[Q']=[2+2]+2=6$
6. Computer

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
| 1   | 0   | 0   | 0   |  1   |
| 1   | 0   | 0   | 1   |   1  |
| 1   | 0   | 1   | 0   |    0 |
| 1   | 0   | 1   | 1   |     0|
| 1   | 1   | 0   | 0   |   1  |
| 1   | 1   | 0   | 1   |   1  |
| 1   | 1   | 1   | 0   |   0  |
| 1   | 1   | 1   | 1   |    0 |

1. $Q = \overline{a} \cdot \overline{b} \cdot \overline{c} \cdot {d} + \overline{a} \cdot {b} \cdot \overline{c} \cdot {d} + {a} \cdot \overline{b} \cdot \overline{c} \cdot \overline{d} + {a} \cdot \overline{b} \cdot \overline{c} \cdot {d} + {a} \cdot {b} \cdot \overline{c} \cdot \overline{d}$ 
3. $K[Q] = [4+4+4+4+4+4]+6=30$
4. Zie tabel 

| $$\begin{matrix} & AB\\CD & \end{matrix}$$ | 00  | 01  | 11  | 10  |
| ------------------------------------------ | --- | --- | --- | --- |
| 00                                         | 0   | 1   | 0   | 0   |
| 01                                         | 0   | 1   | 0   | 0   |
| 11                                         | 1   | 1   | 0   | 0   |
| 10                                         | 1   | 1   | 0   | 0    |

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
6. Computer
7. Computer 
