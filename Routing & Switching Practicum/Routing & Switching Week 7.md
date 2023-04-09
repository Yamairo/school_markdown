1. Zorg ervoor dat alle VLANs en trunks correct geconfigureerd zijn volgens de topologie. Op de Multilayer switch dienen SVIs gebruikt te worden om tussen VLANs te routeren. Check/debug met ```sho ip route```, ```sho spanning-tree```, ```sho ip int brief```, ```sho vlan```, ```sho int trunk```.
   - [x]  Trunks configureren
2. Test met statische IP-adressen op de hosts of alle VLAN’s gepingt kunnen worden.
   - [r] De ping werkt 
3. Stel op de DHCP server de drie adres-pools in voor de VLANS 10, 20 en 30. Denk aan de juiste ranges die uitgegeven mogen worden. Denk ook aan “ip helper-address ” op de SVIs, waar is deze voor?
   > Met `ip helper-address`  worden DHCP-verzoeken in een VLAN doorgestuurd naar een DHCP-server in een ander netwerk. Dit zorgt ervoor dat clients in verschillende VLAN’s IP-adressen kunnen krijgen van dezelfde DHCP-server.
4. Check dat alle hosts een IP-adres gekregen hebben via DHCP in deze drie VLANs.
   - [p] Alle hosts hebben een IP-adres  
5. Zorg er met een ACL voor dat alleen VLAN 10 PC3 niet kan pingen. Kan er een standaard ACL gebruikt worden of moet er een extended ACL gebruikt worden?
   > Dit kan met een standaard ACL want je kan de source IP-adres blokkeren (Het IP-adres van de pc)
6. Zorg er met een ACL voor dat alleen hosts op VLAN 30 kunnen printen (ping is voldoende). Kan er een standaard ACL gebruikt worden of moet er een extended ACL gebruikt worden?
   > Een extended ACL, want dan kan je filteren op source en destination adressen.
   