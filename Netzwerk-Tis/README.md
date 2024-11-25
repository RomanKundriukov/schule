# Grundbegriffe von Iot

#### IoT (Internet of Things):
- Bezeichnet die Vernetzung von physischen und virtuellen Gegenständen über das Internet, die miteinander kommunizieren und Daten austauschen können. Diese Gegenstände können Geräte, Sensoren, Maschinen oder Alltagsgegenstände wie Haushaltsgeräte sein. 

- Das Internet of Things bezeichnet ein Netzwerk von physischen Geräten, die über Sensoren, Software und andere Technologien miteinander verbunden sind, um Daten zu sammeln und auszutauschen. Beispiel: Smarte Haushaltsgeräte wie eine vernetzte Kaffeemaschine.

#### Subscribe (Abonieren):
- In IoT-Systemen bezeichnet sich "Subscribe" auf den Prozess, bei dem ein Gerät oder eine Anwendung sich bei einem Server (z.B. MQTT-Broker) registriert, um bestimmte Themen (Topics) zu abonieren und Benachrichtigungen zu erhalten, wenn neue Daten veröffentlich werden.

#### Topics(Themen):
- Ein Topic ist eine hierarchische Struktur, die verwendet wird, um Datenströme in einem IoT-System zu organisieren. Es wird häufig in Publish-Subscribe-Architekturen (z. B. MQTT) verwendet. Beispiel: "Haus/Küche/Temperatur".

#### Publish (Veröffentlichen):
- Dies beschreibt, wenn ein Gerät oder Sensor Daten (z. B. Temperatur, Feuchtigkeit) an einen Server oder Broker sendet, die von anderen Geräten abgerufen werden können.

#### Gateway:
- Ein Gateway ist ein Gerät oder Software, das Daten von IoT-Geräten sammelt, filtert und an ein Netzwerk oder die Cloud weiterleitet. Es verbindet verschiedene Protokolle und dient als Brücke zwischen IoT-Geräten und Cloud-Systemen.

#### Unterschied zwischen Client und Broker:
- Client: Ein Client ist ein Gerät oder eine Anwendung, die mit einem Broker kommuniziert, um Daten zu senden (Publish) oder zu empfangen (Subscribe).

- Broker: Der Broker fungiert als zentraler Server in einer Publish-Subscribe-Architektur (wie MQTT). Er leitet Nachrichten von Publishern an die entsprechenden Abonnenten weiter.

Beispiel: Ein Temperatursensor (Client) sendet die Temperaturdaten an den MQTT-Broker. Ein Smartphone (Client) abonniert das Thema "Temperatur" und erhält die Daten vom Broker.

#### Bedeutung von Cloud-Diensten:
- Cloud-Dienste sind essenziell für IoT, da sie:

    Daten von IoT-Geräten speichern, analysieren und visualisieren können.
    Remote-Zugriff auf Geräte ermöglichen.
    Skalierbarkeit bieten, um große Datenmengen zu verwalten.

Beispiel: Ein Cloud-Dienst wie AWS IoT Core sammelt Daten von IoT-Sensoren und stellt sie über Dashboards oder APIs zur Verfügung.