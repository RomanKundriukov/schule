## Einordnung der Netzwerkprotokolle

Der Artikel unterteilt Netzwerkprotokolle nach ihrem **Funktionstyp**:

1. **Kommunikationsprotokolle** – ermöglichen den Datenaustausch zwischen Geräten.

2. **Managementprotokolle** – überwachen und steuern den Netzwerkbetrieb.
   
3. **Sicherheitsprotokolle** – schützen Datenübertragungen durch Authentifizierung und Verschlüsselung.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
   

Er bedient sich sowohl des **theoretischen OSI-Modells (7 Schichten)** als auch des gebräuchlicheren **TCP/IP-Modells (4 Schichten)**.

---

## Wichtige Protokolle nach Schichten (im TCP/IP-Modell)

### Anwendungsschicht

- **DNS** – Übersetzt Domainnamen in IP-Adressen und umgekehrt (z. B. A-/AAAA-, CNAME-, MX-, PTR-Einträge).[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    
- **DHCP** – Vergibt automatisch IP-Adressen, Subnetzmaske, Gateway, DNS-Server usw., inklusive Ablauf (Lease) und erneuter Anforderung.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    
- **FTP** – Client-Server-Transfer von Dateien über separate Befehls- und Datenkanäle; alte, aber noch genutzte Methode.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **HTTP / HTTPS** – Basis des Webs: Anforderung und Übertragung von Webseiten; HTTPS schützt per Verschlüsselung via TLS.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **SMTP** – Protokoll zum Versenden von Mails. Für den Empfang nutzt es POP3 oder IMAP.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **SNMP** – Ermöglicht Netzwerkadministration über Manager-Agent-Modell und MIB-Datenbanken.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    
- **SSH** – Sichere Fernzugriffe über verschlüsselte Tunnel, Authentifizierung, Tunneling & Portweiterleitung.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    
- **Telnet** – Frühes Remote-Login-Protokoll ohne Verschlüsselung – heute wegen mangelnder Sicherheit weitgehend obsolet.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    

### Transportschicht

- **TCP** – Verbindungsorientierter Dienst: Zustellung, Sequenzierung, Fehlerprüfung, Neuübertragung.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **UDP** – Verbindungsloser Transport mit niedriger Latenz, ohne Garantie für Reihenfolge oder Lieferung (z. B. für VoIP).[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    

### Internetschicht (Netzwerkschicht)

- **IP** – Vermittelt Datenpakete wie Briefe: mit Absender- und Zieladresse über Router (Gateways) transportiert.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **ARP** – Wandelt IPv4/IPv6-Adressen in MAC-Adressen um und nutzt Caching im LAN.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    
- **ICMP** – Für Netzwerkdiagnose & Fehlermeldungen (z. B. Ping, Traceroute, „Destination Unreachable“).[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise)
    

### Verbindungsschicht (Link Layer)

- **Ethernet** – Standard für kabelgebundene Verbindung, Rahmenbildung, MAC-Adressen.
    
- **WLAN (802.11)** – Standard für drahtlose Verbindung.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    

### Routing-Protokolle (spezialisiert)

- **BGP** – Wichtigster Pfadsteuerungsdienst für das Internet zwischen autonomen Systemen.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
    
- **OSPF** – Datenpakete basierend auf Shortest Path First algorithmisch effizient routen; bessere Skalierbarkeit als RIP.[Computer Weekly](https://www.computerweekly.com/de/feature/12-gaengige-Netzwerkprotokolle-und-ihre-Funktionsweise?utm_source=chatgpt.com)
---
## Übersichtstabelle – Protokolle im Überblick

| Schicht / Kategorie    | Protokolle & Funktion                                             |
| ---------------------- | ----------------------------------------------------------------- |
| **Anwendungsschicht**  | DNS, DHCP, FTP, HTTP/HTTPS, SMTP (+ POP3/IMAP), SNMP, SSH, Telnet |
| **Transportschicht**   | TCP (zuverlässig), UDP (schnell, unzuverlässig)                   |
| **Internetschicht**    | IP (Packet Forwarding), ARP (IP↔MAC), ICMP (Fehler, Diagnose)     |
| **Verbindungsschicht** | Ethernet, WLAN (802.11)                                           |
| **Routing-Protokolle** | BGP (Internet-Routing), OSPF (Intra-Netz Routing)                 |

---

## Überblick zum Address Resolution Protocol (ARP)

**Funktion & Einsatzzweck**

- ARP arbeitet primär in der **OSI‑Schicht 2 (Sicherungsschicht)**, teilweise auch an der Grenze zur Schicht 3, besonders bei der Übersetzung von IP‑Adressen in MAC‑Adressen [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- In einem lokalen Netzwerk werden zur Zustellung von IP‑Paketen **Hardware‑Adressen benötigt**; diese Aufgabe übernimmt ARP.


**Funktionsweise & Ablauf**

1. Ein Host prüft anhand der Subnetzmaske, ob sich die Ziel-IP im lokalen Subnetz befindet.

2. Befindet sich das Ziel im gleichen Subnetz, wird zunächst der **ARP‑Cache** gecheckt. Ist die MAC‑Adresse bekannt, wird direkt gesendet; ist sie unbekannt, wird ein **ARP‑Request** per Broadcast („FF‑FF‑FF‑FF‑FF‑FF“) gesendet [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

3. Der Host mit passender IP-Adresse antwortet mit einem **ARP‑Reply**, woraufhin der Absender die MAC‑Adresse im Cache speichert [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

**Für andere Subnetze / Router**

- Liegt die IP-Adresse außerhalb des lokalen Subnetzes, wird das Paket an das **Standard‑Gateway** (Router) geschickt – dessen MAC-Adresse muss ebenfalls per ARP ermittelt werden, falls sie nicht bekannt ist [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Der Router leitet das Paket entweder ins nächste lokale Subnetz weiter oder nutzt seine Routing‑Tabelle bzw. eigenes Gateway, wenn das Ziel noch weiter entfernt liegt [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Der Vorgang wiederholt sich, bis das Paket das Netzwerk verlässt, sein Ziel erreicht oder die TTL auf 0 fällt [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).


**ARP-Cache – Speicherung & Verwaltung**

- Im ARP‑Cache werden MAC‑Adressen gespeichert, um wiederholte ARP‑Broadcasts zu vermeiden [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Einträge können **statisch** (manuell) oder **dynamisch** (automatisch durch ARP‑Anfragen) angelegt werden [Elektronik-Kompendium](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Dynamische Einträge haben Zeitstempel und werden nach einer gewissen Zeit (z. B. ~2 Minuten) gelöscht, sofern sie nicht erneut genutzt werden; bei Cache‑Überlauf werden ältere Einträge entfernt [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Ein Neustart oder Herunterfahren löscht den Cache, einschließlich statischer Einträge [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).


**Fehlerquellen & Sicherheit**

- ARP funktioniert in der Regel störungsfrei, solange **keine falschen statischen Einträge** gesetzt oder **Hardware‑Adressen manipuliert** werden (z. B. durch ARP‑Spoofing) [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

- Solche böswilligen Eingriffe bleiben dem Nutzer meist verborgen [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901061.htm?utm_source=chatgpt.com).

---

## Was ist Trace Route?

_Trace Route_ – unter Unix bzw. Linux als `traceroute`, unter Windows als `tracert` – ist ein Kommandozeilen-Tool zur Verfolgung des Wegs von Datenpaketen in einem IP-Netzwerk, ähnlich wie der Befehl „Ping“. Es zeigt jedoch zusätzlich, **durch welche Stationen (Hops)** die Datenpakete laufen und liefert detailliertere Informationen zur Netzwerkverbindung [Telekom hilft Community+6Elektronik-Kompendium+6Elektronik-Kompendium+6](https://www.elektronik-kompendium.de/sites/net/0901041.htm?utm_source=chatgpt.com).

## Ablauf & Funktionsweise

- Das Tool sendet mehrere **ICMP-Pakete** (vergleichbar mit Ping), aber mit steigendem **TTL-Wert** (Time to Live).

- Der erste Ping erhält TTL = 1, erreicht also nur den ersten Router. Dieser sendet daraufhin eine **„ICMP Time Exceeded“-Meldung (Typ 11)** zurück [gutefrage+5Elektronik-Kompendium+5Elektronik-Kompendium+5](https://www.elektronik-kompendium.de/sites/net/0901041.htm?utm_source=chatgpt.com).

- Anschließend wird ein Paket mit TTL = 2 gesendet – das erreicht den nächsten Hop – und so weiter, bis das Ziel erreicht ist.

- Das Ergebnis wird Hop für Hop auf dem Bildschirm angezeigt [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901041.htm?utm_source=chatgpt.com)[Elektronik-Kompendium](https://www.elektronik-kompendium.de/sites/net/0901041.htm?utm_source=chatgpt.com).
## Nutzen & Anwendungsgebiete

1. **Pfadprüfung**: Überprüfen, ob die Datenpakete den erwarteten Weg nehmen – Umwege können auf Routerausfälle oder Routingfehler hinweisen.

2. **Performance-Analyse**: Latenz pro Zwischenstation messen – so lassen sich potenzielle Engpässe erkennen.

3. **Fehlerdiagnose**: Bei Paketverlust kann festgestellt werden, an welcher Station die Pakete hängenbleiben.

4. **Routing-Schleifen identifizieren**: Wenn eine Station mehrfach erscheint, kann das auf Routing-Schleifen hindeuten [gutefrage+4Elektronik-Kompendium+4Elektronik-Kompendium+4](https://www.elektronik-kompendium.de/sites/net/0901041.htm?utm_source=chatgpt.com).

## Warum die Zeiten manchmal nicht steigen

Die drei Zeitwerte je Hop repräsentieren drei separate Pings. Sie sind keine kumulierten Zeiten. Daher kann – abhängig von Last oder Pfadänderungen – ein weiter entfernter Hop manchmal schneller antworten als ein früherer [ComputerBase](https://www.computerbase.de/forum/threads/erklaerung-traceroute.990386/?utm_source=chatgpt.com).

| Thema                     | Beschreibung                                                              |
| ------------------------- | ------------------------------------------------------------------------- |
| **Tool & Betriebssystem** | `traceroute` (Unix/Linux), `tracert` (Windows)                            |
| **Funktionsweise**        | Sendet ICMP-Pakete mit steigendem TTL, sammelt „Time Exceeded“-Antworten  |
| **Beispiel-Ausgabe**      | Zeigt Hop-Nummer, drei Latenzwerte und IP-Adresse jeder Station           |
| **Verwendungszweck**      | Pfadkontrolle, Latenzanalyse, Fehlerrecherche, Routing-Schleifen erkennen |
| **Antwortzeiten**         | Drei individuelle Messungen je Hop – nicht kumulativ                      |

---

## Was ist ICMP?

- **ICMP** (Internet Control Message Protocol) ist Teil des Internet Protokolls (IP), fungiert jedoch als eigenständiges Nachrichtenprotokoll zur Übermittlung von Statusinformationen und Fehlermeldungen im Netzwerk. Es dient dazu, IP, TCP und UDP über Probleme bei Datenpaketen zu informieren und so die Übertragungsqualität zu verbessern [Elektronik-Kompendium+2Elektronik-Kompendium+2](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).

- Sollte eine ICMP-Nachricht verloren gehen, wird darüber kein Fehler gemeldet – der Paketverlust bleibt somit unbeachtet [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).

## Aufbau des ICMP-Headers (IPv4)

- ICMP besitzt keinen eigenen Header. Stattdessen wird der Standard-IP-Header angepasst:
    
    - **Type-of-Service**-Feld im IP-Header wird auf **0000** gesetzt.
        
    - Das **Protokoll**-Feld erhält den Wert **1**, der ICMP zugeordnet ist [Elektronik-Kompendium+2Elektronik-Kompendium+2](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).
        
- Der Datenbereich des IP-Headers wird umgewidmet für den ICMP-Teil:
    
    - **ICMP-Typ** (Art der Nachricht)
        
    - **ICMP-Code** (Zusatzinformation zur Nachricht)
        
    - **ICMP-Checksumme**
        
    - **ICMP-Datenbereich**, der den ursprünglichen IP-Header plus die ersten 64 Bit der Daten des Pakets enthält, das die ICMP-Nachricht ausgelöst hat [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).

## Einsatzbereiche von ICMP

- ICMP ist besonders bei Netzwerkfehlern relevant: Es wird zwischen Hosts und aktiven Netzwerkkomponenten (z. B. Routern) verwendet, um Störungen bei IP-Paketen zu melden [Elektronik-Kompendium+2Elektronik-Kompendium+2](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).
    
- Tools wie **Ping** und **Traceroute/Tracert**, die jedem Betriebssystem mit TCP/IP zur Verfügung stehen, basieren maßgeblich auf ICMP und sind essenziell für die Netzwerkdiagnose [Elektronik-Kompendium+1](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).
    
- Darüber hinaus ermöglichen Netzwerkanalysewerkzeuge eine detaillierte Überwachung des ICMP-Verkehrs – hilfreich für tiefgehende Fehlersuche und Leistungsanalysen [Elektronik-Kompendium](https://www.elektronik-kompendium.de/sites/net/0901011.htm?utm_source=chatgpt.com).

|Thema|Details|
|---|---|
|**Protokolltyp**|Teil des IP, eigenständiges Nachrichtenprotokoll für Status- und Fehlermeldungen|
|**Fehlermanagement**|Meldet Probleme zwischen Hosts und Routern zur Verbesserung der Netzwerkübertragung|
|**Verlust von Meldung**|Geht ICMP verloren, führt das nicht zu weiteren Fehlermeldungen|
|**Header-Struktur**|Kein eigener Header, nutzt IP-Header mit Modifikation von Type-of-Service und Protokoll|
|**Nachrichtenfelder**|ICMP-Typ, Code, Checksumme, + IP-Header und erste 64 Bit Paketdaten|
|**Bekannte Tools**|Ping, Traceroute/Tracert (Netzwerkanalyse und Fehlerdiagnose)|
|**Monitoring**|ICMP-Verkehr kann mit Netzwerkmonitoren detailliert überwacht werden|