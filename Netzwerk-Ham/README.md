## Navigations
- [Commands](Commands.md)
## IP
<table>
    <thead>
        <tr>
            <th>IP</th>
            <th>Subnetzmaske</th>
        </tr>
    </thead>
    <tbody> 
    <tr>
        <td>
            <p>4 Byte</p>
        </td>
        <td>
            <p>8 Byte</p>
        </td>
    </tr>
    <tr>
        <td>
            <p>32 Bits</p>
        </td>
        <td>
            <p>48 Bits</p>
        </td>
    </tr>
    </tbody>
</table>

## OSI Modell

![OSI Modell](/Netzwerk-Ham//images/OSIModell.png)

## Protokolle
- ICMP -> ping Befehl
- OSPF -> routing Befehl (224.0.0.5)

## IPv4-Adressierung

<table>
<tr>
<th> </th>
<th>Adresse</th>
</tr>
<tr>
<td>Unicast</td>
<td>1.0.0.0 -> 126.255.255.255</td>
</tr>
<tr>
<td> </td>
<td>127.0.0.1 (kann man sich pingen)</td>
</tr>
<tr>
<td> </td>
<td>128.0.0.0 -> 191.255.255.255</td>
</tr>
<tr>
<td> </td>
<td>192.0.0.0 -> 223.255.255.255</td>
</tr>
<tr>
<td>Multicast</td>
<td>224.0.0.0 -> 239.255.255.255</td>
</tr>
<tr>
<td>Broadcast</td>
<td>255.255.255.255</td>
</tr>
<tr>
<td>Experimentelle Zwecke reserviert</td>
<td>240.0.0.0 -> 255.255.255.254</td>
</tr>
</table>

## Public und Private Ip-Adresse

- Private IP-Adresse

    1. 10.0.0.0 -> 10.255.255.255
    2. 172.16.0.0 -> 172.31.255.255
    3. 192.168.0.0 -> 192.168.255.2550

- Public IP-Adress
    - Ip-Adress von Router, aber mit verschiedene Porten. 
    - Network Address Translation (NAT)

## Subnetzmaske
- Die Subnetzmaske teilt die IP - Adressen in Netzanteil & Hostanteil auf.

    - Hostanteil startet ab 0 in Subnetzmaske

    - Alle Geräte in einem Lan haben den gleichen Netzanteil

<table>
<tr>
<th>Binär</th>
<td>Dezimal</td>
</tr>
<tr>
<td>0000 0000</td>
<td>0</td>
</tr>
<tr>
<td>1000 0000</td>
<td>128</td>
</tr>
<tr>
<td>1100 0000</td>
<td>192</td>
</tr>
<tr>
<td>1110 0000</td>
<td>224</td>
</tr>
<tr>
<td>1111 0000</td>
<td>240</td>
</tr>
<tr>
<td>1111 1000</td>
<td>248</td>
</tr>
<tr>
<td>1111 1100</td>
<td>252</td>
</tr>
<tr>
<td>1111 1110</td>
<td>254</td>
</tr>
<tr>
<td>1111 1111</td>
<td>255</td>
</tr>
</table>

## Wlan - Standorts
L2 - Data Link Layer besteht aus 2 Sublayers
- LLC IEEE 802.2
    - IEEE -> Data Flow
    - 802.2 -> Protokollerkennung 
        - IPv4
        - IPv6
        - ARP
- MAC IEEE 802.3
    - Adressierung
    - Fehlererkennung

WPAN IEEE 802.15 -> Bluetooth, RFID, etc

<table>
<tr>
<th>Aufgabe</th>
<th>Sublayer</th>
</tr>
<tr>
<td>Fehlererkennung</td>
<td>MAC</td>
</tr>
<tr>
<td>Adressierung</td>
<td>MAC</td>
</tr>
<tr>
<td>Data Flow</td>
<td>LLC</td>
</tr>
<tr>
<td>Protokollierung</td>
<td>LLC</td>
</tr>
<tr>
<td>Zugriffskontrolle</td>
<td>MAC</td>
</tr>
</table>

## Ethernet - Frame
 Ein Ithernet ist eine strukturierte Datenübertragungseinheit, die verschiedene Felder enthält.

 Minimale und maximale Frame-Größe:

    Mindestgröße: 64 Bytes, Maximalgröße: 1518 Bytes.
    Frames unter 64 Bytes nennt man "Runt-Frames", und Frames über 1500 Bytes "Jumbo-Frames".

Preamble und Start Frame Delimiter (SFD):

    Besteht aus 8 Bytes: 7 Bytes Preamble und 1 Byte SFD.
    Synchronisation zwischen Sender und Empfänger.

Ziel-MAC-Adresse (Destination MAC Address):

    Identifiziert den Empfänger des Frames (unicast, multicast oder broadcast).

Quell-MAC-Adresse (Source MAC Address):

    Gibt die MAC-Adresse der sendenden Netzwerkkarte (NIC) an.

Typ-Feld (Type):

    2 Bytes groß, gibt das Protokoll der höheren Schicht an (z. B. 0x0800 für IPv4, 0x86DD für IPv6).

Datenfeld (Data Field):

    Enthält die Nutzdaten, typischerweise 46 bis 1500 Bytes groß.
    Falls kleiner, wird Padding hinzugefügt, um die Mindestgröße zu erreichen.

Frame Check Sequence (FCS):

    4 Bytes groß, dient der Fehlererkennung mittels zyklischer Redundanzprüfung (CRC).

Diese Struktur stellt sicher, dass Ethernet-Frames effizient und fehlerfrei übertragen werden.

## MAC - Adresse
- 6 bite -> 48 bit
- besteht aus 12 Hexadezimal Ziffern

- Unicast: 
    - Das Paket wird an ein einziges Ziel gesendet (one to one)
- Broadcast: 
    - Das Paket wird an ein ganzes Netzwerk gesendet (einer an alle)
- Multicast:
    - Das Paket wird an eine Reihe (Gruppe) von Hosts gesendet, die sich in verschiedenen Netzen befinden können (one to many)

AA:BB:C3:F8:AB:10
- AA:BB:C3 -> Herstellerkennung
- F8:AB:10 -> Seriennummer (Geräterkennung)

Brodcast-Adresse
- FF:FF:FF:FF:FF:FF oder 11:11:11:11:11:11

Reservierte Multicast-Adresse
- 01:00:5E -> erste 3 byte
- IPv4-Multicast-Adressen liegen im Bereich 224.0.0.0 bis 239.255.255.255.
- für die Berechnung nehmen wir letzte 3 Byte von gültige Multicast Ip-Adresse
- in erstem Bite des letztes 3 Bytes muss immer 0 sein

## Switch-Verfahren

1. Store-and-Forward-Switching (Speichern und Weiterleiten):

   - Der Switch empfängt den gesamten Frame, führt eine Fehlerprüfung (CRC) durch und speichert ihn.
   - Nur fehlerfreie Frames werden weitergeleitet, basierend auf der Ziel-MAC-Adresse.
   - Vorteil: Höhere Zuverlässigkeit, da fehlerhafte Frames nicht weitergeleitet werden.
   - Nachteil: Höhere Latenz durch vollständige Speicherung des Frames.

2. Cut-Through-Switching (Sofortiges Durchschalten):

   - Der Switch beginnt mit der Weiterleitung, sobald die Ziel-MAC-Adresse gelesen wurde, auch wenn der Frame noch nicht vollständig empfangen ist.
   - Vorteil: Geringere Latenz.
   - Nachteil: Fehlerhafte Frames können weitergeleitet werden.

3. Fast-Forward-Switching:

   - Bietet die geringste Latenz.
   - Der Frame wird sofort nach dem Lesen der Ziel-MAC-Adresse weitergeleitet.
   - Nachteil: Fehlerhafte Frames können übertragen werden.

4. Fragment-Free-Switching:

   - Speichert die ersten 64 Bytes des Frames, bevor er weitergeleitet wird.
   - Kompromiss zwischen Store-and-Forward- und Fast-Forward-Switching.
   - Vorteil: Verhindert die Weiterleitung von Frames mit Kollisionen (da diese meist in den ersten 64 Bytes erkennbar sind).
   - Nachteil: Höhere Latenz als Fast-Forward-Switching, aber geringere Fehlerquote.

<table>
<tr>
<th> </th>
<th>Store and Forward</th>
<th>Cut-Through -> Fast-Forward</th>
<th>Cut-Through -> Fragment Free</th>
</tr>
<tr>
<td>Fehlererkennung CRC()Prüfsumme</td>
<td>ja</td>
<td>nein</td>
<td>ja (Erste 64 Bit)</td>
</tr>
<tr>
<td>Fehlerhafte Frames weiterleiten</td>
<td>nein</td>
<td>ja</td>
<td>nach 64 Bit</td>
</tr>
<tr>
<td>Latenz (Verzogerungszeit)</td>
<td>hoch</td>
<td>niedrig</td>
<td>mittel</td>
</tr>
<tr>
<td>Datenintegrität</td>
<td>hoch</td>
<td>niedrig</td>
<td>mittel</td>
</tr>
</table>

## IPv4-Header-Felder

1. Version:
    - 4-Bit-Wert, der die IP-Version angibt (bei IPv4 ist der Wert „0100“).

2. Internet Header Length (IHL):
    - Gibt die Länge des IPv4-Headers in 32-Bit-Worten an.

3. Differentiated Services (DS):
    - Früher als Type of Service (ToS) bezeichnet.
    - 8-Bit-Feld zur Angabe der Priorität und Qualität des Dienstes (z. B. DSCP und ECN).

4. Total Length:
    - Gesamtlänge des Pakets (Header + Daten) in Bytes.

5. Identification:
    - Eindeutige Identifikation des Pakets, um Fragmentierung zu ermöglichen.

6. Flags:
    - Steuerung der Fragmentierung (z. B. „Don't Fragment“ und „More Fragments“).

7. Fragment Offset:
    - Gibt die Position des Fragments im ursprünglichen Paket an.

8. Time to Live (TTL):
    - 8-Bit-Feld, das die Lebensdauer eines Pakets in Hops begrenzt.
    - Wird bei jedem Router um 1 verringert; erreicht der Wert 0, wird das Paket verworfen.

9. Protocol:
    - Gibt das Protokoll der höheren Schicht an (z. B. ICMP [1], TCP [6], UDP [17]).

10. Header Checksum:
    - Prüfsumme zur Fehlererkennung im Header.

11. Source IP Address:
    - 32-Bit-Adresse des Absenders (Unicast-Adresse).

12. Destination IP Address:
    - 32-Bit-Adresse des Empfängers (Unicast-, Multicast- oder Broadcast-Adresse).

#### Zusammenfassung:

    - Der IPv4-Header enthält wichtige Informationen zur Steuerung, Fragmentierung und Adressierung eines Pakets. Er ist 20 Bytes lang (ohne Optionen) und ermöglicht eine zuverlässige Weiterleitung von Paketen im Netzwerk.

## Auto-MDIX

1. Hintergrund:

    - Früher war die Art des benötigten Kabels abhängig von den verbundenen Geräten:
    - Crossover-Kabel: Für Switch-zu-Switch, Switch-zu-Router.
    - Straight-Through-Kabel: Für Switch-zu-Host oder Router-zu-Host.

2. Funktion von Auto-MDIX:

    - Erkennt automatisch, welcher Kabeltyp (Crossover oder Straight-Through) verwendet wird.
    - Konfiguriert die Schnittstelle des Ports entsprechend, sodass der Kabeltyp keine Rolle mehr spielt.
    - Erleichtert die Verbindung zwischen Geräten und eliminiert mögliche Fehler durch falsche Kabelwahl.

3. Standardstatus:

    - Auto-MDIX ist standardmäßig auf den meisten Switches aktiviert.
    - Kann jedoch deaktiviert sein und muss in solchen Fällen manuell aktiviert werden.

4. Aktivierung von Auto-MDIX:

    - Befehlssatz zur Aktivierung:
    ```js
    switch> enable
    switch# configure terminal
    switch(config)# interface fa0/1
    switch(config-if)# mdix auto
    switch(config-if)# end

    ```
switch> enable
switch# configure terminal
switch(config)# interface fa0/1
switch(config-if)# mdix auto
switch(config-if)# end
#### Zusammenfassung

    - Mit Auto-MDIX können Sie Geräte flexibel mit beliebigen Ethernet-Kabeln verbinden, ohne sich um den Kabeltyp kümmern zu müssen. Es vereinfacht die Netzwerkinfrastruktur erheblich.