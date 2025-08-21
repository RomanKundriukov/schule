# 1 und 2 Level Support

![[../Img/202508211000-1.png]]

---

# SLAs

## Was steht im Vertrag

1. Zielsetzung
2. Vertragsgegenstand
3. Leistungen des Auftragsnehmers
4. Vertragsdauer und Kündigung
5. Art und Umfang der Leistungen
6. Weisungsfreiheit
7. Auftragserfüllung
8. Vergütung
9. Service-Level (Bronze/Silber/Gold) - Kennwerte für die bereitzustellende Leistung
10. Haftung
11. Sonstige Bestimmungen
12. Erfüllungsort / Gerichtsstand

---

# Beispielweiße

- Bronze SLA
	- `Verfügbarkeit` pro Jahr : 99.0%
	- `Servicebereitschaft`: Mo. - Fr. 8:00 - 18:00 Uhr. Außerhalb dieser Zeiten kann eine Störungsmeldung eingehen. Entstörungsprozess beginnt sobald der nächste Werktag erreicht wird
	- `Reaktionszeit`: auf Störungen: innerhalb von 24 Stunden
	- `Entstördauer`: innerhalb von 5 Tagen
	- Der Auftraggeber stellt sicher, dass die Störungsmeldung durch entsprechend entscheidungsbefugtes und qualifizierte Personal erfolgt.
	- Bei dringenden Problemen erfolgt ein Expresszuschlag von +50% auf den regulären Stundensatz und die Lösung beträgt grundsätzlich innerhalb von 4 Stunden

### Jährliche maximal zulässige Ausfallzeiten

|                        | **Ausfallzeiten in Minuten**                      |
| :--------------------- | ------------------------------------------------- |
| **Bronze Level 1 99%** | 365 x 24 x 60 / 100 x 1 = 5256 min = 87,6 Stunden |

|                    | **Reaktionszeit (max)**<br>**Entstördauer (max)**                                 | **Wie viele Vorfälle dieser Art darf es jährlich geben?** |
| :----------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **Bronze Level 1** | *24 Stunden* 1440 min<br>                          +<br>*5 Tage*         7200 min | 8640 min -> 5256 / 8640 = 0.6                             |

