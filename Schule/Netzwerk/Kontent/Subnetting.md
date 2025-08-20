# Subnetting (Subnetmask / Subnetzmaske)

Die Aufteilung eines zusammenhängenden Adressraums von IP-Adressen in mehrere kleinere Adressräume nennt man Subnetting.  
Ein Subnet, Subnetz bzw. Teilnetz ist ein physikalisches Segment eines Netzwerks, in dem IP-Adressen mit der gleichen Netzwerkadresse benutzt werden. Diese Teilnetze können über Routern miteinander verbunden werden und bilden dann ein großes zusammenhängendes Netzwerk.

## Wozu dient Subnetting?

1. **Reduzierung der Routing-Komplexität**  
    Ohne Subnetting müssten alle Router in einem Netzwerk wissen, zu welchem Host jede IP-Adresse gehört oder alle Datenpakete weiterleiten – was die Netzlast erhöht und ineffizient ist[Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0907201.htm?utm_source=chatgpt.com).
    
2. **Effiziente Netzverwaltung**  
    Durch die sinnvolle Vergabe von IP-Adressen entlang der physischen Netzstruktur (z. B. nach Gebäuden oder Abteilungen) wird die Netzlast reduziert. Router müssen nur die Netzwerkadresse statt einzelner Hosts kennen, um Datenpakete korrekt zu routen[Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0907201.htm?utm_source=chatgpt.com).

## Vorteile von Subnetting im Überblick

- **Verbessertes Routing** – Subnetting verringert die Anzahl der zu speichernden Routen, da Router nur noch Netzwerke und nicht einzelne Hosts verwalten müssen.

- **Reduzierte Netzlast** – Durch gezieltes Routing müssen weniger Datenpakete unnötig weitergeleitet werden.

- **Struktur & Skalierbarkeit** – Subnetting erlaubt eine logische Aufteilung nach Standort oder Organisationseinheit und ist dadurch hoch skalierbar.

|Aspekt|Beschreibung|
|---|---|
|**Definition**|Aufteilung eines IP-Adressraums in kleinere logische Subnetze|
|**Zielsetzung**|Effizientere Vergabe und Verwaltung von IP-Adressen|
|**Nutzen**|– Weniger Routing-Informationen nötig– Reduzierte Netzlast– Klare Struktur und Skalierbarkeit|
## Beispiel wie man teilt 1 Netzwerk auf 2 auf

**Netzwerk** 192.168.10.0/24

**Subnetzmaske**
1111 1111 . 1111 1111 . 1111 1111 . 0000 0000

**Hostanteil**
0000 0000 -> 8 Bit

**Host pro Subnetz**
1. `2^8` = 256
2. 256 - 2 (Reservierte Netz-Adresse und Broadcast-Adresse) = 254

**Nehmen 1 Bit** weil wir teilen unser Netzwerk auf 2 kleinere Netzwerke

**Neue Netzwerke** (letzte 7 Bit sind **neue Hostanteil**)

1. 1100 0000 . 1010 1000 . 0000 1010 . `0`000 0000
	192.168.10.0 / 25
	**Broadcast-Adresse:** 1100 0000 . 1010 1000 . 0000 1010 . `0`==111 1111== -> 192.168.10.127/25
	**Adress-Bereich:** 192.168.10.1/25 - 192.168.10.126/25

2. 1100 0000 . 1010 1000 . 0000 1010 . `1`000 0000
	192.168.10.128 / 25
	**Broadcast-Adresse:** 1100 0000 . 1010 1000 . 0000 1010 . `1`==111 1111== -> 192.168.10.255/25
	**Adress-Bereich:** 192.168.10.129/25 - 192.168.10.254/25

## Noch Beispielweise

### Gegeben

| **IP-Adresse**                 | 192.168.200.139      |
| :----------------------------- | -------------------- |
| **Ursprüngliche Subnetzmaske** | 255.255.255.0 / 24   |
| **Neue Subnetzmaske**          | 255.255.255.224 / 27 |

### Gesucht

| **Anzahl der Subnetz-Bits**          | 27 - 24 = 3 Bits für neue |
| :----------------------------------- | ------------------------- |
| **Anzahl der erstellten Subnetze**   | 2^3 = 8                   |
| **Anzahl der Host-Bits pro Subnetz** | 32 - max<br>32-27 = 5     |
| **Anzahl der Hosts pro Subnetz**     | 2^5 = 32 - 2 = 30         |
### IP_Adresse: 192.168.200.139

| **Netzwerkadresse des Subnetz**               | 192.168.200.128 |
| :-------------------------------------------- | --------------- |
| **IPv4-Adresse des ersten Hosts im Subnetz**  | 192.168.200.129 |
| **IPv4-Adresse des letzten Hosts im Subnetz** | 192.168.200.158 |
| **IPv4-Broadcast-Adresse im Subnetz**         | 192.168.200.159 |

---
## FLSM (Fixed-Length Subnet Mask)
	erzeugt Subnetze gleicher Größe und gleicher Anzahl von Host-Kennungen.

## VLSM (Variable-Length Subnet Mask)
	Subnetze unterschiedlicher Größe mit einer variablen Anzahl von Hosts schafft.
