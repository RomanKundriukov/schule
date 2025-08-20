VLANs sind virtuelle lokale Netze die in IEEE 802.1q standardisiert sind und auf der Schicht 2 des OSI-Schichtenmodells arbeiten. Typischerweise arbeitet man in einem Ethernet-basierten Netzwerk mit VLAN- bzw. Multi-LAN-Technik.  
Der Standard IEEE 802.1q ist für die VLAN-Technik bekannt, beinhaltet aber auch die Möglichkeit zur Priorisierung von Datenverkehr.

- Trennung der Datenströme bzw. Segmentierung durch virtuelle LANs (VLAN-ID)
- Priorisierung der Datenströme durch Class of Service (CoS)

Damit beide Verfahren funktionieren, müssen die Netzwerk-Komponenten auf der gesamten Übertragungsstrecke in der Lage sein, alle Datenpakete zu klassifizieren und zu priorisieren.

### Was ist mit „virtuelle LANs mit logischer Trennung“ gemeint?

Die Trennung der Datenströme auf Schicht 2 durch virtuelle LANs sorgt dafür, dass sich Computer unterschiedlicher Subnetze (auf IP-Ebene) nicht sehen können. Denn VLAN-fähige Switche **schalten Ethernet-Frames nur zwischen Ports, die zum selben VLAN gehören**.

- Beispiel Voice-VLAN: Ein Switch erkennt VoIP-Telefone anhand der MAC-Adresse und weist diesen Geräten eine für Telefonie reserviertes VLAN zu. Der Sprachdatenverkehr wird dadurch vom herkömmlichen Datenverkehr im selben lokalen Netzwerk abgeschottet.
- Beispiel Private-VLAN: Jeder Switch-Port ist ein eigenes VLAN. Auf diese Weise können die Clients im lokalen Netzwerk nicht direkt miteinander kommunizieren. Auf diese Weise kann der Datenverkehr durch Fremde nicht ausgespäht werden (ARP Spoofing). Die einzelnen Endgeräte bekommen nur Zugriff aufs Internet. Sinnvoll für Gäste in Hotels und Unternehmen.

### Grundlagen der Netzwerk-Segmentierung

- PLAN: Mehrere Switche für unterschiedliche Netze, die physikalisch voneinander getrennt sind, was teuer, aufwendig und fehleranfällig ist.
- Port-Konfiguration: Ein Zwischenschritt ist, zusammengehörige Switch-Ports zu konfigurieren.
- Mandanten-fähig: Einzelne Switch-Ports lassen sich Nutzergruppen zuweisen.
- VLAN: Jedes VLAN verhält sich wie ein eigener Switch. Die Geräte in den zugeordneten VLANs können miteinander, aber nicht direkt mit Geräten in anderen VLANs kommunizieren.

### Segmentierung durch VLAN-Tagging mit VLAN-ID

Virtuelle LANs werden mit Markierungen bzw. Tags der Ethernet-Frames realisiert. Dazu werden Tags definiert. Wobei es sich hierbei nur um eine Nummer handelt. Die Tags werden von den Switchen im Netzwerk ausgewertet.

Es gibt zwei Möglichkeiten, Pakete mit VLAN-Tags zu versehen.

1. Der Switch versieht jedes eingehende Ethernet-Frame mit oder ohne Abhängigkeit der MAC-Adresse mit einem Tag, was Switch-seitig konfiguriert sein muss.
2. Die einzelnen Hosts versehen ausgehende Datenpakete mit Tags. Dazu muss die LAN-Konfiguration jedes Gerätes entsprechend angepasst werden, damit die korrekte Kennung in den Frame-Header geschrieben wird. Vorteil: Ein Switch kann Pakete aus unterschiedlichen VLANs über denselben Port verarbeiten.

Prinzipiell sind 4.096 (2 hoch 12 Bit) virtuelle LANs möglich (von 0 bis 4.095). Allerdings sind die IDs 0 und 4.095 reserviert. Die ID 1 wird typischerweise als Admin-VLAN verwendet, damit alle Netzwerk-Komponenten zentral steuerbar sind.  
In der Praxis ist es so, dass die Anzahl der konfigurierbaren VLANs oft begrenzt ist. Typisch sind 24 oder 256.

VLANs werden mit Switche realisiert, die in gewisser Weise die Vorteile von Switching und Routing vereinen. Es gilt die Regel: Verbleibt der Netzwerkverkehr innerhalb eines VLANs, wird geswitcht, andernfalls wird in ein anderes VLAN geroutet. Wobei Switching schneller ist als Routing.

## Beispiel-Architektur eines lokalen Netzwerkes mit VLANs

![[../Img/VLAN_Concept.svg.png]]

### Anwendung von VLANs

VLANs können dann sinnvoll eingesetzt werden, wenn man zwei oder mehrere voneinander physikalisch getrennte Netze haben möchte, aber keine zusätzliche Hardware installieren will.

- Trennung von Zugängen zum lokalen Netzwerk mit Zugriff aufs lokale Netzwerk und nur mit Internet-Zugang.
- Trennung von Test- und Produktivumgebungen.
- Normalen Datenverkehr von Anwendungen und Backup trennen.
- Minimierung des Datenverkehrs innerhalb des lokalen Netzwerks. Beispielsweise Begrenzung von Broadcast durch ARP, DHCP, MAC-Flooding, usw. (Hinweis: Broadcasts lassen sich auch durch Subnetting begrenzen.)