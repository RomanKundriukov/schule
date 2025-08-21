
# Incident Management KPIs

>**Incident-Management** bezeichnet einen strukturierten Prozess innerhalb des **IT Service Managements (ITSM)**, dessen Ziel es ist, **unerwartete Störungen oder Leistungseinbußen (Incidents)** möglichst schnell zu beheben und den normalen Betrieb wiederherzustellen.

| Kennzahl               | Zweck / Fokus                                            |
| ---------------------- | -------------------------------------------------------- |
| **MTTR (Respond)**     | Reaktionsgeschwindigkeit (Alert → Start der Bearbeitung) |
| **MTTR (Repair)**      | Reparaturdauer (Behebung bis Wiederherstellung)          |
| **MTBF**               | Systemzuverlässigkeit (Betriebszeit zwischen Ausfällen)  |
| **MTBI**               | Zeitdauer zwischen Incidents                             |
| **Incident Frequency** | Volumen der Incidents pro Zeitraum                       |
| **Verfügbarkeit**      | Anteil der Up-Time gegenüber Gesamtzeit                  |
| **Anteil SL1-gelöst**  | Effizienz der Erstbearbeitung durch First Level Support  |

---

---

## 1. Mean Time To Respond (MTTR—Response)

**Definition**: Durchschnittliche Zeitspanne vom Eingang der Incident-Benachrichtigung (z. B. Alert) bis zum Beginn der Bearbeitung. Manchmal auch als **Mean Time to Acknowledge (MTTA)** bezeichnet.  
**Bedeutung**: Misst die Reaktionsgeschwindigkeit eines Teams. Ein geringer Wert zeigt effiziente Alert- und Eskalationsprozesse.  

## 2. Mean Time to Repair (MTTR—Repair)

**Definition**: Durchschnittliche Dauer von Beginn der Reparatur bis zur Wiederherstellung des Systems (Funktionsfähigkeit). Sie umfasst Diagnose und Behebung.  
**Unterschiede**:

- **Mean Time to Recover (MTRS)** / **Mean Time to Restore (MTTR)** umfasst zusätzlich Verzögerungen wie Teilebeschaffung oder administrative Pausen. [LogicMonitor+1](https://www.logicmonitor.com/blog/whats-the-difference-between-mttr-mttd-mttf-and-mtbf?utm_source=chatgpt.com)  

## 3 Mean Time Between Failures (MTBF)

**Definition**: Durchschnittliche Betriebsdauer zwischen zwei aufeinanderfolgenden (reparablen) Ausfällen eines Systems.  
**Ziel**: Je höher der MTBF, desto zuverlässiger das System.

## 4. Mean Time Between Incidents (MTBI)

**Definition**: Ähnlich wie MTBF, aber bezogen auf **Incidents** (z. B. IT-Störungen), nicht nur hardware-bezogene Fehler.

## 5. Incidenthäufigkeit (Incident Frequency)

**Definition**: Anzahl der Incidents in einem definierten Zeitraum (z. B. pro Monat).  
**Relevanz**: Zeigt das generelle Volumen an Vorfällen und kann Trends oder Problembereiche aufdecken.  
_(Kann je nach Kontext auch pro User, pro System oder pro Zeitspanne gemessen werden.)_

## 6. Verfügbarkeit (Availability/Uptime)

**Definition**: Verhältnis der Zeit, in der ein System funktionsfähig ist, zur Gesamtzeit. Lässt geplante Wartungen außen vor und betrachtet nur ungeplante Ausfälle.

## 7. Anteil der vor First Level Support (FLS) gelösten Incidents

**Definition**: Anteil aller Incidents, die bereits beim **First-Level-Support** (z. B. Helpdesk) gelöst werden, ohne Eskalation an höhere Supportebenen.  
**Relevanz**: Hoher Anteil bedeutet effiziente Erstbearbeitung und entlastet teure Supportstufen.