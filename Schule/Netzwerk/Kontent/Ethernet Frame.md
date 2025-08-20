
Ein Ethernet-Frame ist eine strukturierte Datenübertragungseinheit, die verschiedene Felder
enthält. Jedes dieser Felder hat eine spezifische Funktion. Hier ist eine Beschreibung der
verschiedenen Felder und wichtigen Konzepte:

## **1.  Minimale und maximale Frame-Größe:**

Die minimale Größe eines Ethernet-Frames beträgt 64 Bytes, während die maximale Größe 1518
Bytes beträgt. 
Diese Größenangaben schließen alle Bytes von der Ziel-MAC-Adresse bis zum Frame-Check-
Sequenz-Feld (FCS) ein.

- Frames, die kleiner als 64 Bytes sind, nennt man Kollisionsfragmente oder Runt-Frames. Diese
werden automatisch von den Empfangsgeräten verworfen,

- Frames, die mehr als 1500 Bytes an Daten enthalten, nennt man Jumbo-Frames oder Baby.
Giant-Frames.

## **2. Preamble und Start Frame Delimiter (SFD):**

Diese Felder bestehen aus insgesamt 8 Bytes (7 Bytes für die Preambel und 1 Byte für den SFD)Sie werden zur Synchronisation zwischen Sender und Empfänger verwendet. Die ersten 8 Bytes des Frames signalisieren dem Empfänger, dass ein neuer Frame ankommt. Die Preambel ist nicht in der Frame-Größe enthalten.

## **3. Ziel-MAC-Adresse (Destination MAC Address):**

Dieses 6-Byte-Feld identifiziert den vorgesehenen Empfänger des Frames. Der Wert in diesem
Feld wird mit der MAC-Adresse des Empfangsgeräts verglichen. Wenn die Adressen
übereinstimmen, wird der Frame akzeptiert. Es kann sich um eine Unicast-, Multicast- oder
Broadcast-Adresse handeln.

## **4. Quell-MAC-Adresse (Source MAC Address):**

Dieses 6-Byte-Feld gibt an, von welcher Netzwerkkarte (NIC) der Frame gesendet wurde.

## **5. Typ (Type):**

Dieses 2-Byte-Feld gibt das Protokoll der höheren Schicht an, das im Ethernet-Frame gekapselt
ist. Beispielsweise steht der Wert 0x800 für IPv4, 0x86DD für IPv6 und 0x806 für ARP.

## **6. Datenfeld (Data Field):**

Dieses Feld enthält die eigentlichen Nutzdaten, die von der höheren Schicht stammen, wie etwa
ein IPv4-Paket. Es kann zwischen 46 und 1500 Bytes groß sein. Wenn das Paket kleiner ist,
werden zusätzliche Bits (Padding) eingefügt, um die Mindestgröße des Frames zu erreichen.

## **7. Frame Check Sequence (FCS):**

Das FCS-Feld ist 4 Bytes groß und dient der Fehlererkennung. Es verwendet eine Prüfsumme, die
mithilfe eines zyklischen Redundanzchecks (CRC) berechnet wird. Der Sender fügt das CRC-
Ergebnis in das FCS-Feld ein. Der Empfänger berechnet ebenfalls eine Prüfsumme und vergleicht
diese mit dem empfangenen Wert. Stimmen die Ergebnisse überein, ist der Frame fehlerfrei.
Andernfalls wird der Frame verworfen.

## **Zusammenfassung**

Ein Ethernet-Frame hat eine feste Struktur, die sicherstellt, dass Daten sicher und fehlerfrei
zwischen Netzwerkgeräten übertragen werden. Die Struktur beginnt mit Synchronisationsfeldern
und enthält Adressfelder, ein Datenfeld sowie eine Fehlerprüfungssequenz.