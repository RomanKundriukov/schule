Der Standard IEEE 802.1 definiert Media Access Control (MAC). Hier wird unter anderem die physikalische Adresse für Netzwerk-Schnittstellen festgelegt. Und das unabhängig von der Übertragungstechnik. Die sogenannte MAC-Adressen gelten zum Beispiel für Ethernet (IEEE 802.3), Bluetooth (IEEE 802.15) und WLAN (IEEE 802.11)

### Darstellung einer MAC-Adresse

Die **48 Bit der MAC-Adresse** lässt sich als Bitfolge oder in kanonischer Form darstellen. Weil die Darstellung als Bitfolge zu lang ist, teilt man die 48 in 6 Oktette (jeweils 8 Bit) auf. Jedes Oktett wird dann als eine zweistellige hexadezimale Zahl dargestellt. Wichtig ist, vor der Umformung der dualen in die hexadezimale Darstellung wird das Oktett umgedreht (gespiegelt).  
Bei der hexadezimalen Darstellung werden die hexadezimalen Zeichenpaare durch Bindestriche getrennt. Üblich ist auch die Darstellung mit Doppelpunkten. Das kann zu Verwechslungen mit IPv6-Adressen führen.

**Beispiel für eine Umformung:** 00110101 -> 10101100 = [1010][1100] = AC (hex)

| |Bitfolge|Kanonische Form|
|:--|:--|:--|
|Beispiel 1|00110101 01111011 00010010 00000000 00000000 00000001|AC-DE-48-00-00-80|
|Beispiel 2|01001000 00101100 01101010 00011110 01011001 00111101|12-34-56-78-9A-BC|
### MAC-Multicast- und MAC-Broadcast-Adressen

Gelegentlich kommt es vor, dass ein Ethernet-Frame an mehrere Stationen (Multicast) oder alle Stationen (Broadcast) eines Netzwerks gesendet werden soll. Für diesen Zweck gibt es eine entsprechende Multicast- und Broadcast-Adressen. Sie existieren nur als Ziel-Adressen. Für spezielle Anwendungen gibt es standardisierte Multicast-Adressen. Für Broadcasts (Ethernet-Frames an alle Stationen) gibt es aber nur eine einzige Adresse. Sie lautet:

|                   | Bitmuster                                             | Kanonische Form   |
| :---------------- | :---------------------------------------------------- | :---------------- |
| Broadcast-Adresse | 11111111 11111111 11111111 11111111 11111111 11111111 | FF-FF-FF-FF-FF-FF |
| Multicast-Adresse | ==01:00:5E== -> reserviert für Multicast-Adresse      |                   |

Broadcasts können ein Netz sehr stark belasten, da in diesem Fall das ganze Netz für einen Augenblick mit einem einzigen Datenpaket belegt ist. Bei einem Broadcast-Sturm kann ein Netz sogar ganz zum Erliegen kommen. Nach Möglichkeit vermeidet man Broadcasts über Netzgrenzen hinweg.

## Mac-Adresse

AA:BB:C3:F8:AB:10
- AA:BB:C3 -> Herstellerkennung
- F8:AB:10 -> Seriennummer (Geräterkennung)

## Create Multicast MAC-Adresse aus IP-Adresse

239.192.0.1

1. Nehmen letzte 3 Byte 192.0.1

| 0d  | 192.0.1                           |
| :-- | :-------------------------------- |
| 0b  | 1100 0000 . 0000 0000 . 0000 0001 |

2.  **1 Bit ist immer 0!**
	==0==100 0000 . 0000 0000 . 0000 0001 -> 40:00:01

3. Multicast MAC-Adresse -> 01:00:5E:40:00:01
 