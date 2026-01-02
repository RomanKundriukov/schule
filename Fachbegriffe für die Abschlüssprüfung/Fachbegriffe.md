## Aggregation (schwache Teil-Ganzes-Beziehung)

- **Bedeutung:** _A hat B_, aber **B kann auch ohne A existieren**.
- **Lebensdauer:** Teilobjekt **lebt unabhängig** vom „Ganzen“.
- **UML-Symbol:** **leere Raute** am „Ganzen“.
- **Beispiel:** _Vertrag — Fahrzeug_: Ein Fahrzeug kann unabhängig existieren und könnte auch einem anderen Vertrag zugeordnet werden. Genau so wird es oft erklärt: „Fahrzeug kann als selbständiges Objekt existieren.“

---

## Komposition (starke Teil-Ganzes-Beziehung)

- **Bedeutung:** _A besteht aus B_, **B gehört exklusiv zu A**.
- **Lebensdauer:** Wird **A gelöscht**, werden die **B-Teile mit gelöscht** (sie existieren nicht sinnvoll alleine).
- **UML-Symbol:** **gefüllte (schwarze) Raute** am „Ganzen“.
- **Beispiel:** _Haus — Zimmer_ oder _Bestellung — Bestellposition_: Ohne Haus/Bestellung machen Zimmer/Positionen allein oft keinen Sinn.

**Merksatz:** _„Ich bin der Besitzer – ohne mich existierst du nicht.“_

---
## Kurzvergleich

- **Aggregation:** Teil **kann** allein leben ✅
- **Komposition:** Teil **kann nicht** allein leben ❌ (Lebensdauer hängt am Ganzen)

---
## Polymorphie 

- **Polymorphism** bedeutet in der OOP: **Gleiche Schnittstelle/gleicher Typ – unterschiedliches Verhalten.**

## Die Kernaussage (prüfungsreif)

- Du kannst ein Objekt über einen **Basistyp** (Interface/abstrakte Klasse/Oberklasse) referenzieren.
- Welche Methode tatsächlich ausgeführt wird, entscheidet das **konkrete Objekt zur Laufzeit** (Dynamic Dispatch).

### Mini-Beispiel (Java/C#-Denke)

- Basistyp: `Fahrzeug`
- Untertypen: `Auto`, `Motorrad`
- Beide haben `fahre()`, aber jede Klasse implementiert es anders.
- Du kannst in einer Liste `List<Fahrzeug>` sowohl `Auto` als auch `Motorrad` speichern und `fahre()` aufrufen → jedes fährt „auf seine Art“.