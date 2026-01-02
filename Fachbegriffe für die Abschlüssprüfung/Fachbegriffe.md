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

---

Haupttypen von Verschlüsselungsverfahren

- **Symmetrische Verschlüsselung:**
    - **Prinzip:** Sender und Empfänger teilen sich denselben geheimen Schlüssel.
    - **Vorteil:** Sehr schnell und effizient für große Datenmengen.
    - **Nachteil:** Sicherer Schlüsselaustausch ist kritisch.
    - **Beispiele:** AES (Advanced Encryption Standard).
- **Asymmetrische Verschlüsselung:**
    - **Prinzip:** Nutzt ein Schlüsselpaar: einen öffentlichen Schlüssel (zum Verschlüsseln) und einen privaten Schlüssel (zum Entschlüsseln).
    - **Vorteil:** Kein direkter Schlüsselaustausch nötig, da nur der öffentliche Schlüssel bekannt sein muss.
    - **Nachteil:** Langsamer als symmetrische Verfahren.
    - **Beispiele:** RSA (Rivest–Shamir–Adleman).
- **Hybride Verschlüsselung:**
    - **Prinzip:** Kombiniert beide Ansätze, z. B. wird der symmetrische Sitzungsschlüssel asymmetrisch ausgetauscht und dann für die eigentliche Datenverschlüsselung verwendet (wie bei TLS/SSL).

---

## Angabe / Elemente von Zertifikat

Ein Zertifikat enthält typischerweise Angaben zum Inhaber (Person, Organisation, Domain), zum Aussteller (Zertifizierungsstelle), zum Zweck (z.B. sichere Verbindung, bestandene Prüfung) sowie wichtige Metadaten wie Seriennummer, Gültigkeitsdauer und Ausstellungsdatum, ergänzt durch eine digitale Signatur zur Sicherstellung der Echtheit und Integrität.

Wesentliche Elemente

- **Subjekt (Inhaber):** Wer oder was zertifiziert wird (z.B. Name, Organisation, Web-Domain).
- **Aussteller (Zertifizierungsstelle):** Die vertrauenswürdige Stelle, die das Zertifikat ausstellt und signiert (Name, ggf. Organisation).
- **Öffentlicher Schlüssel:** Dient zur Verschlüsselung und Authentifizierung (bei digitalen Zertifikaten).
- **Seriennummer:** Eindeutige Kennung des Zertifikats.
- **Gültigkeitsdauer:** Zeitraum, in dem das Zertifikat gültig ist (Gültig ab/bis).
- **Ausstellungsdatum:** Wann das Zertifikat erstellt wurde.
- **Digitale Signatur:** Die Signatur der Zertifizierungsstelle, die die Echtheit garantiert. 

Zusätzliche Angaben (je nach Zertifikatstyp)

- **Für Schulungen/Leistungen:** Thema, Umfang, Dauer, Lernziele, Prüfgrundlagen.
- **Für Websites (SSL/TLS):** Domainname, Organisation, Ort, Organisationseinheit (OU).
- **Für physische Urkunden:** Bild/Thema, Titel, Begründung der Auszeichnung, Unterschrift/Siegel.

---

