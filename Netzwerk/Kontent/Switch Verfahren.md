Switches verwenden ihre MAC-Adresstabellen, um zu bestimmen, welchen Port zum Weiterleiten von Frames verwenden wird.

## Bei Cisco-Switches gibt es zwei Methoden zur Weiterleitung von Frames:

- **Store-and-Forward-Switching** (Speichern und Weiterleiten): Diese Methode empfängt den
gesamten Frame und berechnet die CRC (Prüfsumme). Die Prüfsumme stelt fest, ob der
empfangene Frame einen Fehler aufweist. Wenn die CRC gültig ist, sucht der Switch die
Zieladresse heraus, die den ausgehenden Port bestimmt. Anschließend wird der Frame über den richtigen Port weitergeleitet. Ein großer Vorteil des Store-and-Forward-Switching besteht darin, dass festgestellt wird, ob ein Frame Fehier aufweist, bevor er weitergeleitet wird. Das Verwerfen von fehlerhaften Frames verringert den Bandbreitenverbrauch durch beschädigte Daten

- **Cut-Through-Switching** (Sofortiges Durchschalten): Beim dieser Methode reagiert der Switch
auf die Daten, sobald sie empfangen werden, selbst wenn die Übertragung noch nicht
vollständig ist. Der Switch puffert nur so viel des Frames, dass er die Ziel-MAC-Adresse lesen kann, um zu bestimmen, an welchen Port die Daten weitergeleitet werden sollen. Die Ziel-MAC-Adresse befindet sich in den ersten 6 Bytes des Frames, direkt nach dem Präambel. Der Switch sucht die Ziel-MAC-Adresse in seiner Switching-Tabelle, bestimmt den ausgehenden
Schnittstellenport und leitet den Frame über den zugewiesenen Switch-Port an sein Ziel weiter.
Der Switch führt dabei keine Fehlerprüfung des Frames durch.

### Es gibt zwei Varianten des Cut-Through-Switchings:

- **Fast-Forward-Switching:** Das Fast-Forward-Switching bietet das niedrigste Latenzniveau.Beim Fast-Forward-Switching wird ein Paket sofort weitergeleitet, nachdem die Zieladresse gelesen wurde. Da das Fast-Forward-Switching mit der Weiterleitung beginnt, bevor das gesamte Paket empfangen wurde, kann es vorkommen, dass fehlerhafte Pakete weitergeleitet werden. Fast-Forward-Switching ist die typische Methode des Cut-Through-Switchings.

- **Fragment-Free-Switching:** Beim Fragment-Free-Switching speichert der Switch die ersten 64Bytes des Frames, bevor er ihn weiterleitet. Fragment-Free-Switching kann als Kompromisszwischen Store-and-Forward-Switching und Fast-Forward-Switching betrachtet werden. Der Grund, warum Fragment-Free-Switching nur die ersten 64 Bytes des Frames speichert, liegt darin, dass die meisten Netzwerkfehler und Kollisionen während der ersten 64 Bytes auftreten. Fragment-Free-Switching versucht, das Fast-Forward-Switching zu verbessern, indem eine kleine Fehlerprüfung an den ersten 64 Bytes des Frames durchgeführt wird, um sicherzustellen, dass keine Kollision stattgefunden hat, bevor der Frame weitergeleitet wird. Fragment-Free-Switching ist ein Kompromiss'zwischen der hohen Latenz und hohen Integrität des Store-andForward-Switchings und der niedrigen Latenz und verringerten Integrität des Fast-Forward Switchings.

|                                     | **Stored and Forward** | **Cut-Through Fast-Forward** | **Cut-Through Fragment Free** |
| :---------------------------------- | ---------------------- | ---------------------------- | ----------------------------- |
| **Fehlererkennung CRC**             | JA                     | Nein                         | Ja (erste 64 Bit)             |
| **Fehlerhafte Frames weiterleiten** | Nein                   | Ja                           | Nach 64 Bit                   |
| **Latenz (Verzögerungszeit)**       | Hoch                   | Niedrig                      | Mittel                        |
| **Datenintegrität**                 | Hoch                   | Niedrig                      | Mittel                        |