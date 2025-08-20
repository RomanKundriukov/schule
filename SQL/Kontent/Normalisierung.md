
## Die Normalisierung in SQL folgt einer Reihe von Regeln, die als Normalformen (NF) bezeichnet werden. Jede Form beseitigt bestimmte Arten von Redundanzen und Abhängigkeitsproblemen. Die gängigsten Normalformen sind:

- Erste Normalform (1NF) – Beseitigt doppelte Spalten und stellt sicher, dass jede Spalte atomare (unteilbare) Werte enthält.

-  Zweite Normalform (2NF) – Beseitigt partielle Abhängigkeiten, indem sichergestellt wird, dass alle Nicht-Schlüsselattribute vom gesamten Primärschlüssel abhängen.

- Dritte Normalform (3NF) – Beseitigt transitive Abhängigkeiten, d. h. Nicht-Schlüsselattribute dürfen nicht von anderen Nicht-Schlüsselattributen abhängen

- Boyce-Codd-Normalform (BCNF) – Eine strengere Version von 3NF, die sicherstellt, dass jeder Determinant ein Kandidatenschlüssel ist.

- Vierte Normalform (4NF) und Fünfte Normalform (5NF) – Beseitigen Redundanzen weiter, indem sie mehrwertige Abhängigkeiten und Join-Abhängigkeiten behandeln.