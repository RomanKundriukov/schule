
Das OSI-Modell dient als Designgrundlage / Standardisierung für die Kommunikationsprotokolle und -Prozesse in Netzwerken. Er interteilt die gesamte Netzwerk- Kommunikation in sieben aufeinander aufbauende Schichten (Layers). Jede dieser Schichten hat bestimmte und Klare aufgaben.

|     | Deutsch                                        | English            |
| --- | ---------------------------------------------- | ------------------ |
| L7  | Anwendungsschicht                              | Application Layer  |
| L6  | Darstellungsschicht                            | Presentation Layer |
| L5  | Sitzungsschicht                                | Session Layer      |
| L4  | Transportschicht                               | Transport Layer    |
| L3  | Vermittlungsschicht                            | Network Layer      |
| L2  | Sicherungsschicht                              | Data Link Layer    |
| L1  | Physicalische Schicht / Bitübertragungsschicht | Physical Layer     |

![[../Img/Capas-modelo-OSI.png]]

## OSI-Modell Header

![[../Img/osi-model-headers.png]]

## L1: Bitübertragungsschicht 

### Geräte:

- hub - leitet die Daten weiter
	- Unicast: nur an eine bestimmte Person / Gerät
	- Multicast: an eine Gruppe aber nicht an alle
	- Broadcast: an alle (Hub)
- Repeater - Verstärker

### Wie sendet man die Daten:
	- Simplex: in eine Ricgtung
	- Duplex: gleichzeitig in beide Richtungen
	- Halb-Duplex: abwehsend in beide Richtungen

## L2: Sicherungsschicht

### MAC-Addresse:
	steht für Media Access-Control.

- Große: 48 Bit
- Hexadecimal
- MAC-Addresse = Physicalische Addresse

## L3: Addressierung

- IPv4
- IPv6

IPv4: 192.168.10.10

- Große 32 bit
- min 0000 0000 -> 0
- max 1111 1111 -> 1

## L4: Transportschicht

### L4 Addressierung (Ports)

- TCP 
	- Transmission
	- Control Protocol

- UDP
	- User Datagramprotokol