>Das Transmission Control Protocol, kurz TCP, ist Teil der Protokollfamilie TCP/IP. TCP ist ein verbindungsorientiertes Protokoll und soll maßgeblich Datenverluste verhindern, Dateien und Datenströme aufteilen und Datenpakete den Anwendungen zuordnen können.

>Rekonstruktion der Daten = suche richtige Wege, um die Daten zu senden und richtige Reinfolge, um die Daten zurück zu kriegen.

![[../Img/1697696952313.png]]

### Das Transmission Control Protocol (TCP) im TCP/IP-Protokollstapel

| **Schicht** | Dienste / Protokolle / Anwendungen |      |     |      |
| ----------- | ---------------------------------- | ---- | --- | ---- |
| Anwendung   | HTTP                               | IMAP | DNS | SNMP |
| Transport   | TCP                                |      | UDP |      |
| Internet    | IP (IPv4 / IPv6)                   |      |     |      |
| Netzzugang  | Ethernet, WLAN, ...                |      |     |      |
Für die Anwendungen ist TCP transparent. Die Anwendungen übergeben ihren Datenstrom an den TCP/IP-Stack und nehmen ihn von dort auch wieder entgegen. Mit der für die Übertragung nötige TCP-Paketstruktur sowie die Parameter der ausgehandelten Verbindung haben die Anwendungen nichts zu tun.

### Aufgaben und Funktionen von TCP

- Segmentierung (Data Segmenting): Dateien oder Datenstrom in Segmente teilen, Reihenfolge der Segmente wieder herstellen und zu Dateien oder einem Datenstrom zusammensetzen
- Verbindungsmanagement (Connection Establishment and Termination): Verbindungsaufbau und Verbindungsabbau
- Fehlerbehandlung (Error Detection): Bestätigung von Datenpaketen und Zeitüberwachung
- Flusssteuerung (Flow Control): Dynamische Auslastung der Übertragungsstrecke
- Anwendungsunterstützung (Application Support): Adressierung spezifischer Anwendungen und Verbindungen durch Port-Nummern
### Segmentierung (Data Segmenting)

Eine Funktion von TCP besteht darin, den von den Anwendungen kommenden Datenstrom in Datenpakete bzw. Segmente aufzuteilen (Segmentierung) und beim Empfang wieder zusammenzusetzen. Die Segmente werden mit einem Header versehen, in dem Steuer- und Kontroll-Informationen enthalten sind. Danach werden die Segmente an das Internet Protocol (IP) übergeben.  
Da beim IP-Routing die Datenpakete unterschiedliche Wege gehen können, entstehen unter Umständen zeitliche Verzögerungen, die dazu führen, dass die Datenpakete beim Empfänger in einer anderen Reihenfolge eingehen, als sie ursprünglich hatten. Deshalb werden die Segmente beim Empfänger auch wieder in die richtige Reihenfolge gebracht und erst dann an die adressierte Anwendung übergeben. Dazu werden die Segmente mit einer fortlaufenden Sequenznummer versehen (Sequenzierung).

### Verbindungsmanagement (Connection Establishment and Termination)

Als verbindungsorientiertes Protokoll ist TCP für den Verbindungsaufbau und Verbindungsabbau zwischen zwei Stationen einer Ende-zu-Ende-Kommunikation zuständig.  
Durch TCP stehen Sender und Empfänger ständig in Kontakt zueinander.

- [TCP-Kommunikation (Verbindungsaufbau/Verbindungsabbau)](https://www.elektronik-kompendium.de/sites/net/2009211.htm)

### Fehlerbehandlung (Error Detection)

Obwohl es sich eher um eine virtuelle Verbindung handelt, werden während der Datenübertragung ständig Kontrollmeldungen ausgetauscht. Der Empfänger bestätigt dem Sender jedes empfangene Datenpaket. Trifft keine Bestätigung beim Absender ein, wird das Paket noch mal verschickt.  
Da es bei Übertragungsproblemen zu doppelten Datenpaketen und Quittierungen kommen kann, werden alle TCP-Pakete und TCP-Meldungen mit einer fortlaufenden Sequenznummer gekennzeichnet. So sind Sender und Empfänger in der Lage, die Reihenfolge und Zuordnung der Datenpakete und Meldungen zu erkennen.

- [TCP-Kommunikation (Fehlerbehandlung)](https://www.elektronik-kompendium.de/sites/net/2009211.htm)

### Flusssteuerung (Flow Control)

Bei einer paketorientierten Übertragung ohne feste zeitliche Zuordnung und ohne Kenntnis des Übertragungswegs erhält das Transport-Protokoll vom Übertragungssystem keine Information über die verfügbare Bandbreite.  
Mit der Flusssteuerung werden beliebig langsame oder schnelle Übertragungsstrecken dynamisch auszulasten und auch auf unerwartete Engpässe und Verzögerungen reagiert.

- [TCP-Kommunikation (Flusssteuerung)](https://www.elektronik-kompendium.de/sites/net/2009211.htm)

### Anwendungsunterstützung (Application Support)

TCP- und UDP-Ports sind eine Software-Abstraktion, um Kommunikationsverbindungen voneinander unterscheiden zu können. Ähnlich wie IP-Adressen Rechner in Netzwerken adressieren, adressieren Ports spezifische Anwendungen oder Verbindungen, die auf einem Rechner laufen.

- [TCP- und UDP-Ports](https://www.elektronik-kompendium.de/sites/net/1812041.htm)
- [TCP- und UDP-Ports (Übersicht)](https://www.elektronik-kompendium.de/sites/net/2911021.htm)

### Der kleine Bruder: UDP - User Datagram Protocol

Neben dem verbindungsorientierten TCP gibt es auch das verbindungslose und unsichere UDP. Das User Datagram Protocol (UDP) ist ebenso auf der Schicht 4, der Transportschicht, des OSI-Schichtenmodells angeordnet. Es hat die selbe Aufgabe wie TCP, nur das ihm nahezu alle Kontrollfunktionen fehlen und dadurch schlanker daher kommt und einfacher zu verarbeiten ist.

- [Mehr Informationen über UDP](https://www.elektronik-kompendium.de/sites/net/0812281.htm)

### Aufbau des TCP-Headers

Jedem Datenpaket, das TCP verschickt, wird ein Header vorangestellt, der die folgenden Daten enthält:

- Sender-Port
- Empfänger-Port
- Paket-Reihenfolge (Nummer)
- Prüfsumme
- Quittierungsnummer
- Flags

Aufbau des TCP-Headers TCP-Pakete setzen sich aus dem Header-Bereich und dem Daten-Bereich zusammen. Im Header sind alle Informationen enthalten, die für eine gesicherte TCP-Verbindung wichtig sind. Der TCP-Header ist in mehrere 32-Bit-Blöcke aufgeteilt. Mindestens enthält der Header 5 solcher Blöcke. Somit hat ein TCP-Header eine Länge von mindestens 20 Byte.

### Bedeutung der Felder im TCP-Header

|Feldinhalt|Bit|Beschreibung|
|:--|:--|:--|
|Quell-Port  <br>(Source-Port)|16|Hier steht der Quell-Port, von der die Anwendung das TCP-Paket verschickt. Bei einer Stellenanzahl von 16 Bit beträgt der höchste Port 65.535.|
|Ziel-Port  <br>(Destination-Port)|16|Hier steht der Ziel-Port, über welchen das TCP-Paket der Anwendung zugestellt wird. Bei einer Stellenanzahl von 16 Bit beträgt der höchste Port 65.535.|
|Sequenz-Nummer|32|Bei jeder TCP-Verbindung werden Nummern zwischen den Kommunikationspartner ausgehandelt. Während der Verbindung werden diese Nummern verwendet um die TCP-Pakete eindeutig zu identifizieren.|
|Acknowledgement-Nummer|32|Alle Datenpakete werden bestätigt. Dazu dient das ACK-Flag und die Acknowledgement-Nummer, die sich aus der Sequenz-Nummer und der Anzahl von empfangenen Bytes errechnet. Damit kann der Sender feststellen, ob die Daten beim Empfänger vollständig angekommen sind.|
|Data Offset|4|Hier steht die Anzahl der 32-Bit-Blöcke des TCP-Headers. Die Mindestmenge beträgt 5.|
|Reserviert|6|Dieser Bereich ist auf 000000 gesetzt und für Erweiterungen des TCP-Headers gedacht.|
|Flags|6|Kennzeichnung bestimmter für die Kommunikation und Weiterverarbeitung der Daten wichtiger Zustände (URG, ACK, PSH, RST, SYN, FIN).|
|Window-Größe|16|Der Empfänger sendet dem Sender in diesem Feld die Anzahl an Daten, die der Sender senden darf. Dadurch wird das Überlaufen des Empfangspuffers beim Empfänger verhindert. Den Vorgang nennt man Windowing und dient der Datenflusssteuerung.|
|Check-Summe|16|Dieses Feld dient der Kontrolle von Header- und Datenbereich.|
|Urgent-Pointer|16|Zusammen mit der Sequenz-Nummer gibt dieser Wert die genaue Position der Daten im Datenstrom an. Der Wert ist nur gültig, wenn das URG-Flag gesetzt ist.|
|Optionen/Füllbits  <br>(Options/Padding),  <br>jeweils 32 Bit lang|   |Dieses Feld beinhaltet optionale Informationen. Um die 32-Bit-Grenze einzuhalten wird das Options-Feld mit Nullen aufgefüllt.|
### Schwächen von TCP

Eine Schwäche von TCP ist die Verzögerung durch den Verbindungsaufbau vor der eigentlichen Datenübertragung. Und nach dem Verbindungsaufbau mit TCP entstehen weitere Zeitverluste durch den Verbindungsaufbau mit den Protokollen TLS und HTTP. Da fragt man sich zu Recht, warum kann ein Verbindungsaufbau bzw. Handshake nicht für alle beteiligten Protokolle gelten.  
Beim Protokoll Quick UDP Internet Connections (QUIC) werden Wartezeiten, die durch viele einzelner TCP-Verbindungen entstehen, durch Verschachtelung mit darüberliegenden Protokollen eingespart und sogar die TLS-Verschlüsselung integriert.

- [QUIC - Quick UDP Internet Connections](https://www.elektronik-kompendium.de/sites/net/2210241.htm)