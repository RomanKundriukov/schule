- Große: 32 Bits
- Blöcke: 4
- Beispiel: 192.168.10.10
- min 0000 0000 -> 0
- max 1111 1111 -> 1

## Subnetzmaske
	Die Subnetzmaske ist eine Tahl, die angibt welche Teilmenge eine IP-Addresse für das Subnetz und welche für die Hosts in einem Netzwerk verwendet wird.
	Linke seite muss als 1 sein und rechte als 0, d.h. 1110 < geht nicht oder 0001 < geht auch nicht

	IPv4-Address 192.168.1.10

	Bits:  1100 0000 . 1010 1000 . 0000 0001 . 0000 1010
	Maske: 1111 1111 . 1111 1111 . 1111 1111 . 0000 0000

	Netzteil: 1100 0000 . 1010 1000 . 0000 0001 . 
	Hostteil: . 0000 0000

## IPv4 Header

![[../Img/ipv4header.png]]

---

## Unicast

1. 1.0.0.0 -> 126.255.255.255
2. 128.0.0.0 -> 191.255.255.255
3. 192.0.0.0 -> 223.255.255.255

## Localhost

1. 127.0.0.1

## Multicast

1. 224.0.0.0 -> 239.255.255.255
2. 224.0.0.5 -> OSPF - Routing Protokol

## Broadcast

1. 255.255.255.255

## Experimental 

1. 240.0.0.0 -> 255.255.255.254

## Private IP-Adressen

1. 10.0.0.0 -> 10.255.255.255
2. 172.16.0.0 -> 172.31.255.255
3. 192.168.0.0 -> 192.168.255.255