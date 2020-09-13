### Was ist KI?

- Gegenstand der KI ist die Untersuchung intelligenten Verhaltens und dessen Implementierung auf Computern.

### Wann ist ein System intelligent?

- Ein System heißt intelligent, wenn es selbstständig und effizient Probleme lösen kann.
- Der Grad der Intelligenz hängt vom Grad der Selbstständigkeit, dem Grad der Komplexität des Problems und dem Grad der Effizienz des Problemlösungsverfahrens ab.

### Welche Arten von Machine Learning gibt es?

- Supervised Learning (̈uberwachtes Lernen): Lernen erfolgt durch Verwendung von Trainingsdaten, die in Eingabe- und Ausgabewerten aufgeteilt sind. Nach dem Training sollen aus neuen Eingabewerten auf unbekannte Ausgabewerte geschlossen werden können.
- Unsupervised Learning (unüberwachtes Lernen): Lernen erfolgt mit Trainingsdaten ohne bekannte Ausgabewerten bzw. Strukturierung (Klassifizierung).
- Reinforcement Learning (verstärkendes Lernen): Das Lernen erfolgt aus einer Reihe von Verstärkungen in Form von Belohnungen oder Bestrafungen. Das Ziel ist, ein System zu entwickeln, das seine Leistungen durch Interaktionen mit seiner Umgebung verbessert (z.B. Starcraft-Bot).

### Was ist der Unterschied zwischen einer schwachen und einer starken KI?

- Schwach: Kann einen Anwendungsfall gut.
- Stark: Kann den Menschen ersetzen.

### Wie kann man eine KI auf Stärke testen?

- Turing-Test: Wand zwischen KI und Tester

### Anwendungsbereiche für KI?

- Mustererkennung, Spracherkennung, Bilder verstehen, Expertensystem (Diagnosen), Roboter, Spiele

### Was ist eine Aussage?

- Kleinstes sprachliches Gebilde, dass klar entweder wahr oder falsch sein kann!

### Wie funktioniert die Implikation?

- Wenn es regnet (A), dann ist die Wiese nass (B).
- Prämisse falsch -> Implikation wahr

### Was ist die Konjunktive Normalform?

- KNF: Klauseln, die mit `UND` verbunden sind.
- Eine Klausel sind Literale, die mit `ODER` verbunden sind.

### Wie kommt man zur KNF?

1. Äquivalenzen killen
2. Implikationen killen
3. Negation an die Literale binden
4. Doppelte Negationen auflösen
5. Ausmultiplizieren

### Was ist die semantische Folgerung?

- wenn alle Formeln vor `|=` wahr sind, dann ist alles nach `|=` auch wahr.

### Was sind modus ponens und modus tollens?

- modus ponens: `A -> B, A |= B`
- modus tollens: `A -> B, -B |= -A`

### Wie funktioniert Resolution?

- Man macht eine KNF aus der semantischen Folgerungen (nimmt das negierte Zeug in dem Gleichzeichen mit rein)
- Man bildet Mengen aus den Klauseln
- Jetzt kürze man immer ein Literal raus
- Wenn die leere Menge am Ende rauskommt, dann stimmt die semantische Folgerung

### Was ist ein Prädikat?

- M(x): x ist ein mensch | M => Prädikat
- s: Simon | s => Objekt

### Was ist der Allquantor?

- ∀ -> für alle

### Was ist der Existenzquantor?

- ∃ -> es existiert
- Fun fact: `∃x ≡ ¬∀x¬`

### Wie funktioniert die Resolution bei der Prädikatenlogik?

- Quantoren nach links ziehen und dann ignorieren.
- Dann gleich wie bei der normalen Resolution.

### Was ist eine Hornklausel?

- Eine Klausel mit maximal einem positiven Literal

### Wie ist ein künstliches Neuron aufgebaut?

- Eingabewerte: $o_n$
- Gewichte: $w_n$
- Netzeingabe: $net = \sum_j o_j * n_j$
- Aktivität: $a = f_{act}(net)$
- Ausgabe: $o = a$

### Welche Aktivierungsfunktionen gibt es so?

- Schwellwertfunkion $f_0$
- Logistische Funktion $f_{log}(net) = \frac{1}{1 + e^{-c * net}}$

### Was ist ein neuronales Netz?

- Eine Menge von Neuronen, die durch gerichtete und gewichtete Verbindungen miteinander verknüpft sind.
- Eingabe-Neuronen: zu diesem Neuron gibt es keine gerichtete Verbindung hin
- Ausgabe-Neuronen: von diesen Neuronen gibt es keine gerichtete Verbindung weg

### Welche Spezialfälle gibt es in der Architektur eines neuronalen Netzes?

- Short connection (eine Schicht wird übersprungen)
- Rückkopplung (von einer Ausgabe zu einer inneren Schicht)

### Was ist eine Perzeptron?

- Ein einstufiges vorwärtsgerichtetes neuronales Netz, das keine inneren Schichten hat.

### Wie kann man ein Perzeptron trainieren?

- o = Ausgabe bzw. mit Index Eingabe
- t = erwartetes Ergebnis
- Fehler = t - o
- Korrektur = Lernrate (λ) * Fehler * Eingabewert
- Neues Gewicht = Altes Gewicht + Korrektur
- Für die grafische Ermittlung: $o_2 = \frac{\theta - o_1 w_1}{w_2}$

### Was ist Backpropagation?

- Lernverfahren für mehrstufige Perzeptrons.
- Braucht man, weil es keine Soll-Ausgabewerte für die verdeckten Schichten gibt.

### Was ist die Idee hinter einem Convolutional Neural Network?

- Man bearbeitet die Eingabe, bevor man was ins Netz gibt.

### Was sind die Schritte beim Convolutional Neural Network?

1. Convolution: Filter (Kernel) über das Bild laufen lassen um mehrere Feature Maps zu erstellen.
2. ReLu-Aktivierungsfunktion: (Negative Werte = Null, positive Werte = Gerade)
3. Pooling: Aus einem Großen Bild ein kleines machen (z.B. immer nur max Wert nehmen)
4. Klassifizierung: Durch ein mehrstufiges Perzeptron.

### Wie kann man das Flussüberquerungsrätsel lösen?

- Zustandsraum (alle validen Zustände) definieren
- Übergänge einzeichnen
- Weg finden

### Wie kann man das Tic Tac Toe Problem lösen?

- Zustandsbaum bilden.
- Davon ausgehen, dass immer das beste gewählt wird.
