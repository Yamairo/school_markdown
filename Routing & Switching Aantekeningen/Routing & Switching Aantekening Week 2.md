# IPv4 adressen 
<a>IPv4 adressen zijn 32 bits</a>

####  Een Ip adres bestaat uit twee delen
	- Netwerkdeel:
	- Hostdeel
  Het **netwekmasker** bepaalt het netwerkdeel van het adres 

## Notaties :
	- Dotted decimal 255.255.255.0

## Adressentypen

### Netwerkdeel 
### Netmasker : 255.255.255.0

### Hostadressen
### Netmasker : 255.255.255.0

**Broadcastadres:** wordt gebruikt om data te versturen naar alle hosts in het netwerk

| Netmask              | $1^e$ octet | $2^e$ octet    | $3^{e}$ octet | $4^e$ octet |
| -------------------- | ----------- | ------- | ------------- | ----------- |
| 255.0.0.0 of /8      | Network     | host    | host          | host        |
| 255.255.0.0 of /16   | network     | network | host          | host        |
| 255.255.255.0 of /24 | network     | network | network       | host        |

^e8e8c4

#### 172.16.20.0 / 25
- Bereken het netwerkadres 
  *172.16.20.0*
- Bereken het broadcastadres 
- Bereken  het laagste hostadres
- Bereken het hoogste hostadres

| Subnet mask     | Prefix | Hosts             |
| --------------- | ------ | ----------------- |
| 255.255.0       | /24    | 256               |
| 255.255.128.0 | /25    | 128               |
| 255.255.192.0 | /26    | 64                |
| 255.255.224.0 | /27    | 32                |
| 255.255.240.0 | /28    | 16                |
| 255.255.248.0 | /29    | 8                 |
| 255.255.252.0 | /30    | 4                 |
| 255.255.254.0 | /31    | 2 (niet gebruikt) |
| 255.255.255.0 | /32    | 1 (voor loopback)|

## Binair bekeken 
Gegeven hostadres: 192.168.131.99 / 27
$Binair: 11000000.10101000.10000011.\underline{01100011}$
netwerkdeel $\underline{Hostdeel}$

| $\underline{Hostdeel}$ |     | $\underline{Netwerkadres}$ |     | $\underline{}$ |
| ---------------------- | --- | -------------------------- | --- | ---------------------- |






