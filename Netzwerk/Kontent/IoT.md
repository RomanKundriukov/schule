
- IoT steht für das =="Internet der Dinge" (Internet of Things)==. Es bezeichnet ein Netzwerk physischer Objekte, die mit Sensoren, Software und anderen Technologien ausgestattet sind und über das Internet miteinander kommunizieren können, um Daten auszutauschen und Aufgaben zu automatisieren

### 1. **MQTT (Message Queuing Telemetry Transport)**

Ein leichtgewichtiges Netzwerkprotokoll im **Publish‑Subscribe‑Modell**, ideal für IoT‑Anwendungen mit begrenzten Ressourcen und instabilen Netzwerken. Es basiert typischerweise auf TCP/IP und wurde entwickelt für Machine‑to‑Machine-Kommunikation.

### 2. **Client**

Beliebige Geräte oder Anwendungen (z. B. Sensoren, Aktoren, Web-Apps), die MQTT verwenden. Sie können Nachrichten **veröffentlichen (publish)** oder sich für bestimmte Themen **anmelden (subscribe)** – oder beides. Kommunikation erfolgt immer über den Broker.

### 3. **Broker (MQTT-Broker)**

Ein Server, der:

- Nachrichten von Publishern entgegennimmt,
- sie nach Themen sortiert,
- und an abonnierende Clients weiterleitet.

Er ist zentraler Vermittler, sorgt für Zustellung auch bei instabiler Verbindung und verwaltet Sitzungen (z. B. persistent sessions).

### 4. **Publish**

Wenn ein Client Daten sendet:

- Die Nachricht enthält ein **Topic** (Themenpfad) und einen **Payload** (Dateninhalt).
- Der Broker verteilt sie an Clients, die das betreffende Topic abonniert haben.

### 5. **Subscribe**

Ein Client beantragt:

- über den Broker Nachrichten für bestimmte **Topics** (Themen) zu erhalten.
- Man verwendet dabei Topic-Namen oder Filter (Wildcards wie `+`, `#`), um flexibel mehrere Themen abzudecken.

### 6. **Topics**

Hierarchisch strukturierte Strings (z. B. `sensor/temperature/room1`), nach denen Nachrichten geroutet werden. Topic-Namen sind flexibel und müssen nicht vorab angelegt werden.

### 7. **Payload**

Der tatsächliche Inhalt der Nachricht (z. B. Temperaturwert, JSON-Daten). MQTT ist **datenagnostisch** – es ist egal, ob Text, JSON, Binärdaten oder Bilder übertragen werden.

### 8. **Gateway / IoT-Gateway**

Spezielle IoT-Komponente, die z. B.:

- Protokolle konvertiert (z. B. lokale Sensor‑Protokolle → MQTT),
- Daten sammelt,
- und an den MQTT-Broker weiterleitet oder umgekehrt.

(Obwohl in deiner Liste erwähnt, wurde dieser Begriff nicht explizit in den Quellen definiert — ich habe ihn kontextuell ergänzt.)

### 9. **Sensoren & Aktoren**

- **Sensoren**: Generieren Daten (z. B. Temperatur, Licht).
- **Aktoren**: Führen Aktionen aus (z. B. Relais öffnen, Licht steuern).

Beide können Clients in einem MQTT-Netzwerk sein:

- Sensoren → **publishen** Messwerte. 
- Aktoren → **subscriben** Befehle (bzw. handeln entsprechend).
