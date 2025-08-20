

Eine IPv6-Adresse ist eine Netzwerk-Adresse, die einen Host eindeutig innerhalb eines IPv6-Netzwerks logisch adressiert. Die Adresse wird auf IP- bzw. Vermittlungsebene (des OSI-Schichtenmodells) benötigt, um Datenpakete verschicken und zustellen zu können. Im Gegensatz zu anderen Adressen hat ein IPv6-Host mehrere IPv6-Adressen, die unterschiedliche Gültigkeitsbereiche haben.  
Konkret bedeutet das, dass wenn von IPv6-Adressen die Rede ist, dass nicht immer klar ist, welchen Gültigkeitsbereich diese IPv6-Adressen aufweisen. Grob unterscheidet man zwischen verbindungslokalen und globalen IPv6-Adressen. Die verbindungslokale IPv6-Adresse ist nur im lokalen Netzwerk gültig und wird nicht geroutet. Die globale IPv6-Adresse ist über das lokale Netzwerk hinaus im Internet gültig.

Eine IPv6-Adresse hat eine Länge von 128 Bit. Diese Adresslänge erlaubt eine unvorstellbare Menge von 2128 oder 3,4 x 1038 IPv6-Adressen. Das sind 340.282.366.900.000.000.000.000.000.000.000.000.000 IPv6-Adressen, also rund 340 Sextillionen Adressen. Bei IPv4 spricht man von rund 4,3 Milliarden Adressen.  
Der Adressraum von IPv6 reicht aus, um umgerechnet jeden Quadratmillimeter der Erdoberfläche inklusive der Ozeane mit rund 600 Billiarden Adressen zu pflastern. Im Vergleich zu IPv4 geht man bei der Vergabe und Zuteilung von IPv6-Adressen deshalb sehr großzügig um.

Arten von IPv6-Adressen

- Unicast: Adressen für ein einzelnes Interface.
- Anycast: Adressen für mehrere Interfaces, wobei nur eines davon das Paket empfängt.
- Multicast: Adressen für mehrere Interfaces, die alle das selbe Paket empfangen.
- Broadcast: Existieren nicht und wird mit Multicast-Adressen realisiert.

### Segmentierung

Einer der Gründe für den Wechsel von IPv4 auf IPv6 ist der größere Adressbereich von IPv6. Doch warum gleich 128 Bit Adressbreite? Der Grund ist der, dass die IP-Adressen lang genug sein sollten, um den gesamten Adressraum großzügig segmentieren bzw. aufteilen zu können. Es sollen möglichst alle Netzwerk-Topologien berücksichtigt werden können. Gleichzeitig soll das Routing vereinfacht werden.

Damit Router effizient arbeiten können, müssen Adressen hierarchisch strukturiert vergeben werden. Damit alle Ebenen der Hierarchie abgebildet werden können, muss die IP-Adresse lang genug sein. Wünschenswert wäre es, wenn dann auch noch genug Raum für zukünftige Entwicklungen übrig bleibt. Deshalb akzeptiert man bei der Segmentierung von IPv6-Adressen auch einen relativ großen Verschnitt.

### IPv6-Adresse im Detail

![[../Img/ipv6-adressen.png]]

Eine IPv6-Adresse besteht aus 128 Bit. Wegen der unhandlichen Länge werden die 128 Bit in 8 mal 16 Bit unterteilt. Je 4 Bit werden als eine hexadezimale Zahl dargestellt. Je 4 Hexzahlen werden gruppiert und durch einen Doppelpunkt (":") getrennt. Um die Schreibweise zu vereinfachen lässt man führende Nullen in den Blöcken weg. Eine oder mehr Gruppen von 4 Nullen kann man einmalig durch zwei Doppelpunkte ("::") ersetzen.

Eine IPv6-Adresse besteht aus zwei Teilen. Dem Network Prefix (Präfix oder Netz-ID) und dem Interface Identifier (Suffix, IID oder EUI).  
Der Network Prefix kennzeichnet das Netz, Subnetz bzw. Adressbereich. Der Interface Identifier kennzeichnet einen Host in diesem Netz. Er wird aus der 48-Bit-MAC-Adresse des Interfaces gebildet und dabei in eine 64-Bit-Adresse umgewandelt. Es handelt sich dabei um das Modified-EUI-64-Format.  
Auf diese Weise ist das Interface unabhängig vom Network Prefix eindeutig identifizierbar.

## Verkürzungsform

1. In IPv6-Adresse kann man alle erste 0 im Block verkürzen
2. Man kann alle 0 Blöcke mit `::` verkürzen, aber nur 1 mal pro IPv6-Adresse

**Voll-Form:** 2001:0db8:0000:0000:0000:0000:0000:0001
**Kurz-Form:** 2001:db8::1

### Interface

**Link-Local-Adresse (LLA)** beginnt immer mit `fe80` z.B. fe80::1
**Global Unicast Adresse (GUA)** beginnt von `2001` bis `3FFF` z.B. 2001:db8:acad:1::1/64


> Jede IPv6 Gerät **muss** mindestens ein LLA-Adresse haben. **Kann** GUA-Adresse haben


## Header

> Größe = 40 Byte (320 Bit)


![[../Img/ipv6-header.png]]

>Um die Verarbeitung der IPv6-Pakete zu vereinfachen wurde die Länge des IPv6-Headers auf 40 Byte fest definiert. Optionale Informationen werden in die Extension-Headers verlagert. Der feste Teil des IPv6-Headers enthält unter anderem die IPv6-Adresse von Sender und Empfänger. Das IPv4-Feld Time-to-live (TTL) ist das Hop Limit. Auf die Prüfsummenberechnung und Fragmentierung wird verzichtet, was den IPv6-Routern das Leben erleichtert.

### Bedeutung der Felder im IPv6-Header

|Feldinhalt|Bit|Beschreibung|
|:--|:--|:--|
|Version|4|Hier ist die Version des IP-Protokolls abgelegt, nach der das IP-Paket erstellt wurde.|
|Traffic Class|8|Der Wert des Feldes definiert die Priorität des Paketes.|
|Flow Label|20|Das Flow Label kennzeichnet Pakete für ein viel schnelleres Routing. Das MPLS macht dieses Verfahren allerdings überflüssig.|
|Payload Length|16|Hier steht die im IP-Paket transportierten Daten in Byte. Bisher musste der Wert aus dem Feld Paketlänge abzüglich dem Feld IHL ermittelt werden.|
|Next Header|8|Hier ist das übergeordnete Transportprotokoll angegeben. Bei IPv4 hieß das Feld einfach Protokoll.|
|Hop Limit|8|Dieses Feld enthält die Anzahl der verbleibenden weiterleitenden Stationen, bevor das IP-Paket verfällt. Es entspricht dem TTL-Feld von IPv4. Jede Station, die ein IP-Paket weiterleitet, muss von diesem Wert 1 abziehen.|
|Source-Address|128|An dieser Stelle steht die IP-Adresse der Station, die das Paket abgeschickt hat (Quell-IP-Adresse).|
|Destination-Address|128|An dieser Stelle steht die IP-Adresse der Station, für die das Paket bestimmt ist (Ziel-IP-Adresse).|
|IPv6-Header-Erweiterungen  <br>jeweils 64 Bit  <br>(8 Byte)|   |Im IPv6-Header können optional Informationen im separaten Header dem IP-Kopf angehängt werden. Bis auf wenige Ausnahmen werden diese Header-Erweiterungen von IP-Routern nicht beachtet.|

## Reservierte-Adresse

1. `fe80` --> LLA
2. `2001` bis `3FFF` --> GUA
3. `ff02::2` --> alle Router im Netz
4. `ff02::1` --> alle Geräten im Netz
5. `ff02::1:FF` --> `Präfix` für Berechnung der `Solicited-Node Multicast-Adresse`
6. `fc00` / `fd00` --> ULA (Unique Local Address)