## Wenn ein neuen PC war im Netz verbunden:

1. `RS` (Router Solicitation) `Multicast`
	PC fragt nach einem Router (`fe80::2`)
2. `RA` (Router Advertisement)
	Der Router antwortet und sendet Präfix, MTU etc...
3. `GUI` = Präfix + MAC-Adresse

### Beispielweiße

1. `IPv6-Adresse`: fe80::12
2. `MAC_Adresse`:  20:1A:2B:3C:4D:5E
3. `Präfix`: 2001:db8:abcd::/64

>Erstellen eine `GUI-Adresse`

4. `MAC_Adresse`:  20:1A:2B:3C:4D:5E = 48 Bit
5. 16 Bit für `GUI` fehlt.
6. Nehmen `FFFE` -> Reserviert. 16 Bit
7. in ersten Block des MAC-Adresse ändern 7 Bit. 1 = 0 / 0 = 1
	`war`: 20:1A:2B:3C:4D:5E
		0010 00`0`0
	`neue`: 22:1A:2B:3C:4D:5E
		0010 00`1`0
8. Fügen reservierte teil `FFFE` in der Mitte hinzu.
	221A : 2B`FF` : `FE`3C : 4D5E
9. Fassen `Präfix von Router` und `neue Teil` zusammen
	2001 : DB8 : ABCD : 221A : 2BFF : FE3C : 4D5E -> `GUI-Adresse`

## Emitteln die MAC-Adresse aus IPv6-Adresse (Neighbor Discovery)

1. `NS`(Neighbor Solicitation) Multicast
	PC fragt nach der MAC-Adresse von einem anderen PC
2. `NA` (Neighbor Advertisement)
	Ziel-PC sendet sein MAC-Adresse

> Berechnen **Solicited-Node Multicast-Adresse**. Das Braucht man bei der `NS`

3. Extrahieren **letzte 24 Bit** aus `GUI`
	2001 : DB8 : ABCD : 221A : 2BFF : FE`3C : 4D5E`
4. Fassen **Solicited-Node Multicast-Adresse** zusammen
	ff02::1:FF3C:4D5E