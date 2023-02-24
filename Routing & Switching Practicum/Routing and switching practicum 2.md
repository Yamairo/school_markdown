```toc
```
---

## Vraag 1:
>Elk sub-sub-net kan 16 hosts adresseren

$1^{e}$ host
```js
1.2.3.32/28
```

$2^e$ host
```js
1.2.3.63/28
```
---
## Vraag 2:

```js
NA : 166.60.0.0/16
BA : 166.60.251.255/16
Subnetmask : 255.255.0.0
````
---
## Vraag 3:

```js
Hoofdnetwerk als binair : 1010 0110 . 0011 1100 . 0000 0000 .  0000 0000
```

### Subnet 0
#### Binair 
```js
NA : 1010 0110 . 0011 1100 . 0000 0000 . 0000 0000
BA : 1010 0110 . 0011 1100 . 0000 1111 . 1111 1111
```

#### IP - adres
```js
NA : 166.60.0.0/20
BA : 166.60.15.255/20
```
---
### Subnet 6
#### Binair 
```js
NA : 1010 0110 . 0011 1100 . 0110 0000 . 0000 0000
BA : 1010 0110 . 0011 1100 . 0110 1111 . 1111 1111
```

#### IP - adres
```js
NA : 166.60.96.0/20
BA : 166.60.111.255/20
```
---
## Vraag 4:

```js
Hoofdnetwerk : 166.60.96.0/20
Hoofdnetwerk als binair : 1010 0110 . 0011 1100 . 0110 0000 . 0000 0000
```
### Subnet 0
#### Binair
```js
NA : 1010 0110 . 0011 1100 . 0100 0000 . 0000 0000
BA : 1010 0110 . 0011 1100 . 0100 0000 . 1111 1111
Subnetmask : 1111 1111 . 1111 1111 . 1111 1100 . 0000 0000
```

#### IP - adres
```js
NA : 166.60.64.0/22
BA : 166.60.64.255/22
Subnetmask : 255.255.252.0
```

---

## Vraag 5
Gegeven een /24 netwerk, is het kleinste subnet dat je kan gebruiken /30 dit is omdat het maar 2 bruikbare IP-adressen heeft.

---

## Cisco
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 8   | 7   | 6   | 5   | 4   | 3   | 2   | 1    |
### Vraag 1
| IPv4 Addres/Prefix | Network Address  | Broadcast Address  | Total Number Of Hosts Bits | Total Number of Hosts |
| ------------------ | ---------------- | ------------------ | -------------------------- | --------------------- |
| 192.168.100.25/28  | 192.168.100.0/28 | 192.168.100.255/28 | 4                          | 14                    |
| 172.30.10.130/30   | 172.30.10.130/30 | 172.30.10.255/30   | 2                          | 2                     |
| 10.1.113.75/19     | 10.1.113.64/19   | 10.1.113.255       | 13                         | 8190                  |
| 198.133.219.250/24 | 198.133.219.0/24 | 198.133.219.255/24 | 8                          | 254                   |
| 128.107.14.191/22  | 128.107.12.0/22  | 128.107.12.255/22  | 10                         | 1022                  |
| 172.16.104.99/27   | 172.16.104.96/27 | 172.16.104.255/27  | 5                          | 30                      |

### Vraag 2

#### Pobleem 1
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               | 192.168.200.139 |
| Original subnet mask                        |  255.255.255.0  |
| New Subnet Mask:                            | 255.255.255.224 |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |       19        |
| Number of Subnets Created                   |       32        |
| Number of Host Bits per Subnet              |       13        |
| Number of Hosts per Subnet                  |      8190       |
| Network Address of this Subnet              |  192.168.192.0  |
| IPv4 Address of First Host on this Subnet   |  192.168.192.1  |
| IPv4 Address of Last Host on this Subnet    | 192.168.192.254 |
| IPv4 Broadcast Address on this Subnet       | 192.168.223.255                |

#### Pobleem 2
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               |  10.101.99.228  |
| Original subnet mask                        |    255.0.0.0    |
| New Subnet Mask:                            |  255.255.128.0  |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |        8        |
| Number of Subnets Created                   |       512       |
| Number of Host Bits per Subnet              |       24        |
| Number of Hosts per Subnet                  |      32766      |
| Network Address of this Subnet              |    10.0.0.0     |
| IPv 4 Address of First Host on this Subnet  |    10.0.0.1     |
| IPv 4 Address of Last Host on this Subnet   | 10.255.255.254  |
| IPv 4 Broadcast Address on this Subnet      | 10.255.255.254  |

#### Pobleem 3
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               |  172.22.32.12   |
| Original subnet mask                        |   255.255.0.0   |
| New Subnet Mask:                            |  255.255.224.0  |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |       16        |
| Number of Subnets Created                   |       32        |
| Number of Host Bits per Subnet              |       24        |
| Number of Hosts per Subnet                  |      32766      |
| Network Address of this Subnet              |   172.22.0.0    |
| IPv 4 Address of First Host on this Subnet  |   172.22.0.1    |
| IPv 4 Address of Last Host on this Subnet   | 172.22.255.254  |
| IPv 4 Broadcast Address on this Subnet      | 172.22.255.255  |

#### Pobleem 4
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               |  192.168.1.245  |
| Original subnet mask                        |   255.255.0.0   |
| New Subnet Mask:                            | 255.255.255.252 |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |       16        |
| Number of Subnets Created                   |      16384      |
| Number of Host Bits per Subnet              |        8        |
| Number of Hosts per Subnet                  |        2        |
| Network Address of this Subnet              |   192.168.0.0   |
| IPv 4 Address of First Host on this Subnet  |   192.168.0.1   |
| IPv 4 Address of Last Host on this Subnet   | 192.168.255.254 |
| IPv 4 Broadcast Address on this Subnet      | 192.168.255.255 |

#### Pobleem 5
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               |  128.107.0.55   |
| Original subnet mask                        |   255.255.0.0   |
| New Subnet Mask:                            |  255.255.255.0  |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |       15        |
| Number of Subnets Created                   |       512       |
| Number of Host Bits per Subnet              |       13        |
| Number of Hosts per Subnet                  |       254       |
| Network Address of this Subnet              |   128.106.0.0   |
| IPv 4 Address of First Host on this Subnet  |   128.106.0.1   |
| IPv 4 Address of Last Host on this Subnet   | 128.107.255.254 |
| IPv 4 Broadcast Address on this Subnet      | 128.107.255.255 |

#### Pobleem 6
| Given                                       |                 |
|:------------------------------------------- |:---------------:|
| Host IP Adres                               | 192.135.250.180 |
| Original subnet mask                        |  255.255.255.0  |
| New Subnet Mask:                            | 255.255.255.248 |
| ------------------------------------------- | --------------- |
| Find                                        |                 |
| Number of Subnet Bits                       |       24        |
| Number of Subnets Created                   |       32        |
| Number of Host Bits per Subnet              |        8        |
| Number of Hosts per Subnet                  |        6        |
| Network Address of this Subnet              |  192.135.250.0  |
| IPv 4 Address of First Host on this Subnet  |  192.135.250.1  |
| IPv 4 Address of Last Host on this Subnet   | 192.135.250.254 |
| IPv 4 Broadcast Address on this Subnet      | 192.135.250.254 |
