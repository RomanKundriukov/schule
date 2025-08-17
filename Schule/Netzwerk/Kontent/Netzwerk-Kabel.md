
### Kabelarten

- **Koaxialkabel**: heute kaum genutzt, früher für Bus-/Ring-Netze. Aufbau: Innenleiter + Abschirmung. Vorteil: weniger Störungen. Einsatz: TV, Radio, selten Netzwerke.
    
- **Twisted-Pair-Kabel**: verdrillte Adernpaare, Standard in LANs. Vorteile: weniger Störungen, PoE möglich. Varianten: UTP, FTP, S/FTP etc.
    
- **Lichtwellenleiter (LWL/Glasfaser)**: Übertragung mit Licht, sehr hohe Bandbreite und Reichweite, unempfindlich gegen Störungen. Nachteile: teurer, aufwendige Montage, Signalumwandlung nötig.
    

### Patch- vs. Verlegekabel

| |Patchkabel (flexibel)|Verlegekabel (starr)|
|---|---|---|
|Anwendungsbereich|Serverschrank, Geräte|Kabelkanal, Wände|
|Länge|kurz|lang|
|Bauweise|dünn, flexibel|robust, starr|
|Steckertyp|RJ-45 Steckverbinder|RJ-45 Stecker|

### Schirmung

- **U** = ungeschirmt
- **F** = Folie
- **S** = Geflecht
- **SF** = Folie + Geflecht

| Typ   | Gesamtschirmung | Adernschirmung |
| ----- | --------------- | -------------- |
| U/UTP | keine           | keine          |
| F/UTP | Folie           | keine          |
| S/FTP | Geflecht        | Folie          |

### Passive Komponenten

- Anschlussdosen
- Patchfelder (Patch-Panels)
- Patchkabel

### Glasfaser vs. Kupfer

- **Glasfaser**: mehr Bandbreite, weniger Dämpfung, ideal für große Distanzen/Rechenzentren.
- **Kupfer (Twisted Pair)**: günstiger, einfacher, PoE-Versorgung möglich, für Büro/Etagen völlig ausreichend.

### Installation

- Kabel sorgfältig behandeln, nicht quetschen, Biegeradien einhalten.
- Twisted-Pair-Adern beim Auflegen nicht zu weit öffnen.
- Netzwerkkabel getrennt von Stromleitungen verlegen, Erdung/Potentialausgleich beachten.

## Glassfaser

|                 | Kupferleitung (TP-Kabel)                        | Glassfaser                                      |
| --------------- | ----------------------------------------------- | ----------------------------------------------- |
| Geschwindigkeit | bis 10 Gbit/s                                   | bis 40 Gbit/s                                   |
| Zuverlässigkeit | Anfällig für elektromagnetische Störungen       | sehr Zuveflässig                                |
| Reichweite      | 100 m                                           | bis zu 40 km                                    |
| Kosten          | günstiger in der Installation für kurze Strecke | Teuer in der installation, aber Kostengünstig   |
| Sicherheit      | Relativ leicht abzuhören                        | sehr schewr abzuhören, bietet höhere Sicherheit |

![[Aufbau_Koaxkabel.png]]

### Vorteile der Lichtwellenleiter gegenüber Kupferkabel

- Lichtwellenleiter können beliebig mit anderen Versorgungsleitungen parallel verlegt werden. Es wirken keine elektromagnetischen Störeinflüsse.
- Wegen der optischen Übertragung existieren keine Störstrahlungen oder Masseprobleme.
- Entfernungsbedingte Verluste durch Induktivitäten, Kapazitäten und Widerständen treten nicht auf.
- Nahezu Frequenz-unabhängige Leitungsdämpfung der Signale.
- Übertragungsraten sind durch mehrere Trägerwellen mit unterschiedlichen Wellenlängen (Farbspektrum) fast unbegrenzt erhöhbar.
- Es gibt keine Probleme mit dem Potenzialausgleich bei unterschiedlichen Erdungspotenzialen an den Kabelenden der Etagenverteiler.

### Nachteile der Glasfaser

- Lichtwellenleiter sind teurer als Kupferkabel.
- Die Kosten für den Aufwand bei der Montage sind höher.
- Lichtimpulse lassen sich nicht vernünftig verarbeiten und auch nicht speichern.
### Fachbegriffe

Der **Brechungsindex** ist der Faktor, um den die Lichtgeschwindigkeit in optischen Medien kleiner ist, als im Vakuum.

**Moden** sind die verschiedenen Wege, denen die Photonen des Lichts innerhalb oder entlang der Faser folgen können. Single- oder Monomode-Fasern haben nur eine, Multimode-Fasern können viele Moden unterstützen.

Der **Spleiß** ist die dauerhafte Verbindung zwischen zwei Fasern. Um eine Verbindung zwischen zwei Fasern herzustellen, müssen die beiden Enden verschmolzen (Schmelzspleiß) oder verklebt (Klebespleiß) werden.

Das Einfügen eines optischen Bauelements erzeugt eine Dämpfung des Signals. Das ist mit **Einfügedämpfung** gemeint.

**Dispersion** beschreibt den Effekt, dass der eingespeiste Lichtimpuls über den Ausbreitungsweg zeitlich ausgeweitet wird. Der Lichtimpuls wird breiter. Dadurch kann es zu Überlappungen mit den vorangegangenen und nachfolgenden Impulsen kommen. Bei hohen Geschwindigkeiten kann es zu Übertragungsfehlern kommen.  
Damit der Lichtimpuls möglichst lange impulsartig bleibt, werden für die Impulserzeugung Laserdioden und keine herkömmlichen Leuchtdioden verwendet.

### Mode und Moden

Der Begriff "Mode" in Bezug auf Glasfaserkabel bezieht sich auf die Anzahl der möglichen Lichtpfade oder Signalwege, die durch die Glasfaser verlaufen können. Singlemode-Fasern erlauben nur einen Lichtpfad, während Multimode-Fasern mehrere Lichtpfade unterstützen. Singlemode-Fasern wird für große Entfernungen verwendet, während Multimode-Fasern für kürzere Strecken in Rechenzentren oder Unternehmensnetzwerken geeignet ist.

Bei Multimode-Fasern ist die räumliche Verteilung des Lichts orthogonal (vergleichbar mit „linear unabhängig“ bei Vektoren). Man muss sich das so vorstellen, dass man mehrere Lichtsignale gleichzeitig mit unterschiedlichen Winkeln in die Faser einspeist. Abhängig vom Winkel wird das Signal häufiger an den Wänden reflektiert und legt eine längere Strecke zurück. Das ist mit den Moden gemeint. Die unterschiedlichen Moden können (theoretisch) voneinander wieder getrennt werden. Allerdings sind die Moden in den klassischen Multimode-Fasern ein unerwünschter Nebeneffekt. Es erfolgt kein Multiplexing. Es wird sogar darauf geachtet, keine Laufzeitunterschiede zu bekommen.

Man verwendet Multimode-Fasern normalerweise nur wegen der geringeren Kosten im Vergleich zu Singlemode-Fasern. Das wiederum geht zu Lasten einer reduzierten Leitungslänge wegen der deutlich höheren Dämpfung von Multimode-Fasern.