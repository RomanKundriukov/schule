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