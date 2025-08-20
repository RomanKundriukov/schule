
## SLAAC (Stateless Address Autoconfiguration)

>Stateless Address Autoconfiguration (SLAAC) ist ein Verfahren zur zustandslosen und automatischen Konfiguration von IPv6-Adressen an einem Netzwerk-Interface. Mit "stateless" bzw. "zustandslos" ist gemeint, dass die jeweilige IPv6-Adresse nicht zentral vergeben und gespeichert wird. Demnach erzeugt sich der Host seine IPv6-Adresse unter Zuhilfenahme zusätzlicher Informationen selbst. SLAAC ist die Weiterentwicklung von Verfahren für die klassische IP-Autokonfiguration unter IP4. Anders als bei IPv4 übernehmen IPv6-Router dabei eine aktive Rolle.

>Man unterscheidet grob gesehen zwischen globalen IPv6-Adressen (Global Scope) und link-lokalen IPv6-Adressen (Local Scope). Mit der Stateless Address Autoconfiguration kann sich ein IPv6-Host sowohl eine link-lokale, als auch eine globale IPv6-Adresse erzeugen.  Damit bietet IPv6 den gleichen Komfort wie beim Betrieb eines sehr einfach gehaltenen DHCP-Servers.

>Das Ziel von SLAAC ist, dass ein Host zumindest eine link-lokale IPv6-Adresse bekommt, mit der in jedem Fall eine Verbindung innerhalb des lokalen Netzwerks möglich ist. In einem weiteren Schritt würde sich ein Host per SLAAC ein globale IPv6-Adresse erzeugen, mit der er auch Verbindungen ins Internet aufbauen kann.


| **Merkmal**                   | **LLA**                                             | **ULA (Unique Local Address)** |
| :---------------------------- | --------------------------------------------------- | ------------------------------ |
| **Präfix**                    | fe80                                                | fc00/fd00                      |
| **Reichweite**                | Nur im lokalen Netz                                 | Das ganze lokale Netz          |
| **Automatisch generiert**     | Ja                                                  | Nein                           |
| **Kommunikation über Router** | Nein                                                | Ja (nur intern)                |
| **Internetfähig**             | Nein                                                | Nein                           |
| **Typische Nutzung**          | Kommunikation zwischen Geräte im selben Netzsegment | Intranet                       |
