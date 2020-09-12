### Was ist der Unterschied zwischen Stack und Heap? 

Lokale Variablen werden auf dem Stack, globale Variablen und Objekte werden auf dem Heap gespeichert. 

### Was ist der Unterschied bei der Prozesssynchronisation zwischen `Wechselseitiger Ausschluss bei kritischen Aktivitäten` (1) und `Sauberer Ablauf bei Abhängigkeiten?` (2) 

1. Prozess B wartet auf das Ende von Prozess A um die Ressource/n nutzen zu können.
2. Prozess B wartet auf das Ergebnis von Prozess A, damit er beginnen kann. 

### Wie groß ist der `logische Adressraum` bei einem 32-Bit-Rechner? 

4GB virtueller Speicher, die jeder Prozess erhält. 

### Was sind Race Conditions? 

Race Conditions sind Probleme, die bei gleichzeitiger Nutzung von Speicher durch verschiedene Prozesse oder Threads auftreten können. 

### Was ist die Von-Neumann-Architektur? 

- Die Von-Neumann-Architektur ist ein Referenzmodell für Computer, wonach ein gemeinsamer Speicher sowohl Computerprogrammbefehle, als auch Daten hält.
- Komponenten: Recheneinheit, Steuerwerk, BUS, Arbeitsspeicher, I/O

### Welches Problem wird durch UEFI bzw. durch BIOS gelöst?

- Das BIOS löst das Problem des sogenannten Bootstrappings, also das Dilemma, dass Software zum Starten Software benötigt.
- Bootstrapping: Software befindet sich normalerweise auf einem Datenträger, dessen Speicher beim Start erstmal in den Hauptspeicher des Rechners eingelesen werden muss. Dazu benötigt die CPU aber wiederum Software.
- Lösung für Bootstrapping: Das Ladeprogramm befindet sich bei modernen 64-bit Systemen als Teil des UEFI in einem Flash-Speicher, dessen Inhalt auch ohne Stromversorgung erhalten bleibt. 

### Was ist die Aufgabe der Systemschnittstelle? 

Sie trennt Benutzermodus und Kernmodus. 

### Was sind Vordergrundprozesse? 

Sie sind Prozesse, die mit (menschlichen) Benutzern interagieren. 

### Nennen Sie 3 Betriebssysteme. 

Windows, Ubuntu, MacOS 

### Was ist der Unterschied zwischen dem Benutzermodus und dem Kernmodus eines Betriebssystems?

Mit dem Benutzermodus kann man auf unkritische Anwendungen zugreifen, ohne dass der Benutzer `große` Benutzerrechte besitzt. Im Kernmodus greift man auf die Hardware zu und kann z.B. Programme starten bzw. stoppen.  

### Aus welchem Grund wird Arbeitsspeicher eingesetzt? 

Arbeitsspeicher ist bedeutend schneller als eine normale HDD, und kann dadurch Daten schneller zur Verfügung stellen. 

### Was sind die Kennzeichen einer Open Source Software? 

Eine Open Source Software zeichnet sich dadurch aus, dass ihr Quelltext öffentlich und von Dritten eingesehen, geändert und genutzt werden kann. Darüber hinaus ist Open Source Software meist kostenlos nutzbar. Ein Beispiel für ein Open Source Betriebssystem ist Linux. 

### Nach welchem Prinzip sortiert die Addressraumverwaltung die lokalen Variablen? 

Nach dem `LIFO`-Prinzip (Last-In-First-Out).

### Was ist ein Spinlock?

Loop bis das Lock verfügbar ist

```
// Eintrittsprotokoll
 solange (Sperrvariable besitzt Wert 'gesperrt') {
    tue nichts;
 }
 setze Sperrvariable auf 'gesperrt'

 // Kritischer Abschnitt
 modifiziere Ressource

 // Austrittsprotokoll
 setze Sperrvariable auf 'frei'
```

### Nennen Sie die Vor- und Nachteile von Spinlock. 

- Wechselseitiger Ausschluss funktioniert
- Keine Race-Conditions trotz gemeinsamer Variable
- Ablauf der beiden Prozesse A und B sind nur im striktem Wechsel möglich 
- Beim Warten in der While-Schleife wird unnötig CPU-Zeit verbraucht 

### Was ist ein Semaphor?

Meist wird die Ganzzahl (Zähler) beim Start des Semaphors mit dem Zahlenwert der maximal verfügbaren Ressourcen initialisiert bzw. der maximalen Zahl der Prozesse, die gleichzeitig die Ressource nutzen können. Ein Prozess, der auf die Ressource zugreifen will, muss vorher die Operation „Reservieren/Probieren“ aufrufen, und danach, wenn er die Ressource nicht mehr benötigt, die Operation „Freigeben“. Bei jeder Reservierung wird der Zähler um 1 heruntergezählt, bei Freigabe wird er wieder um 1 erhöht. Der Zähler darf nicht unter 0 fallen: Wenn eine Reservierung bei Zählerstand 0 erfolgt, wartet der reservierende Prozess, bis ein anderer Prozess Ressourcen freigegeben hat. Es gibt auch Implementierungen, die ins Negative zählen. Damit kann angezeigt werden, wie viele Prozesse auf eine Freigabe warten. 

### Was ist der Unterschied zwischen einem Dienst, und einem Prozess? 

Ein Dienst ist ein Hintergrundprogramm ohne Bildschirmausgabe, dass beim Booten automatisch gestartet wird. Der Prozess hingegen kann aktiv vom Benutzer gestartet und verwaltet werden. 

### Adressraumverwaltung: Was ist die Aufgabe des `Stacks` und wie funktioniert es?

- lokale Variablen aus Unterprogrammen / Rücksprungadresse für die Rückkehr ins vorherige Unterprogramm / Hauptprogramm werden gespeichert. 
- der Stack funktioniert nach dem `LIFO` Prinzip 

### Was ermöglicht die Betriebssystemeigenschaft `Multiuser`? 

Sie ermöglicht das simultane Arbeiten mehrerer Benutzer am gleichen System. 

### Was ist der Unterschied zwischen dem Typ-1 und Typ-2 Hypervisor? 

- Typ 1-Hypervisor: Eine Art Basis-Betriebssystem, dessen Aufgabe es ist, virtuelle Maschinen zu betreiben.
- Typ 2-Hypervisor: Betreibt virtuelle Maschinen und läuft selber auf einem vollwertigem Gast-Betriebsystem. 

### Was ist Scheduling?

Ein permanenter OS Prozess entscheidet welcher Prozess als nächster rechnen darf.

### Welche Scheduling-Kategorien gibt es? 

1. Nicht unterbrechende (nonpreemptive): Scheduler lässt einen Prozess so lange laufen bis er blockiert wird oder er die CPU freiwillig freigibt.
2. Unterbrechende (preemptive): Scheduler wählt Prozess aus und lässt ihn nur eine festgesetzte Zeit laufen

### Nenne Scheduling-Algorithmen

- first come first served
- shortest job first
- round robin (jeder darf mal, einer nach dem anderen)
- priority

### Was versteht man unter der Abkürzung GNU? 

GNU: Gnu is Not Unix Vom MIT Studenten Richard Stallman wurde die Free Software Foundation initiiert. Damit verbunden ist die GNU General Public License (GPL), eine weit verbreitete, freie Softwarelizenz. 

### Was sind Aufgaben eines Betriebssystems? 

Verwaltung der Zugriffs- und Benutzerrechte, Input-, Output-Steuerung, Anwenderprogramme installieren u. starten, Schnittstelle zur Hardware grafische Darstellung 

### Welcher Scheduling-Algorithmus besitzt die durchschnittlich beste Laufzeit? 

Shortest Job First 

### Welche 3 Zugriffsrechte für Dateien und Verzeichnisse gibt es für Unix? 

1. Leseerlaubnis (r)
2. Schreibererlaubnis (w)
3. Ausführererlaubnis (x)

### Wie funktioniert eine grafische Benutzeroberfläche?

- Betriebssystem stellt eine Programmbibliothek zur Verfügung
- Button wird betätigt, der von Windows gezeichnet wird
- Ein Ereignis wird produziert
- Nachricht wird in eine Warteschlange eingereiht (Message Queue)
- Nachrichten werden nacheinander abgearbeitet (Message Loop)
- Passendes Programm wird zur Nachricht ausgeführt (Event-Handler) 

### Worauf basiert Android?

Android basiert auf einem Linux Kernel und einer veränderten Java Virtual Machine. 

### Was ist der Stack Pointer? 

Der Stack Pointer zeigt auf die unterste oder letzte Adresse, die gerade im Stack verwendet wird. 

### Was sind die Nachteile des `Swapping` und wie können diese beseitigt werden? 

- Aus -und Einlagern kostet viel Zeit -> Relokationsproblem: Das Programm wird an beliebigen Speicherstellen gestartet bzw. der Prozess neu geladen. Die Speicheradresse einer Variablen kann damit beim Übersetzen des Codes nicht festgelegt werden bzw. ändert sich wieder beim neuen Laden.
- Speicherschutzproblem: Die Programme arbeiten mit absoluten Adressen. Deshalb kann man kein Programm davon abhalten, Befehle zu erzeugen, die jedes beliebige Wort im Speicher lesen oder überschreiben. 

### Welche Prozesszustände gibt es und welche Funktion haben sie? 

- Rechnend: der Prozess wird ausgeführt
- Rechenbereit: der Prozess kann ausgeführt werden und wartet, bis er aufgerufen wird
- Blockiert: der Prozess kann nicht ausgeführt werden, da er auf ein eintretendes Ereigniss wartet(z.B. auf die Festplatte oder auf eine Eingabe des Benutzers) 

### Was versteht man unter `Multithreading`? 

Multithreading bezeichnet das gleichzeitige Abarbeiten mehrerer Threads innerhalb eines einzelnen Prozesses. 

### Unterschied Prozess / Dienst?

- Dienst(services/daemons): Hintergrund-Programm ohne Bildschirmausgabe, das beim Booten automatisch gestartet werden kann und auch läuft, wenn kein Benutzer angemeldet ist.
- Prozess = einmalig

### Wie funktioniert der virtuelle Speicher beim 32bit Rechner?

- Jeder Prozess bekommt 4GB RAM
- Speicher wird in Einheiten a 4kB eingeteilt (Pages)
- MMU (Memory Management Unit) teilt den Pages ihre Pageframes (Realer Speicher und auf die Festplatte ausgelagerter Speicher) zu
- Pageframe nicht vorhanden → page fault

### Wie funktioniert RAID Level 0?

- Festplatten werden in Stripes unterteilt
- Die Stripes werden nach Round-Robin auf den echten Platten verteilt.

### Wie funktioniert RAID Level 1?

- Spiegeln

### RAID Level 5

- Jede Disk hat Parity um die anderen Disks wiederherzustellen
- Eine Disk kann ausfallen
- Kapazität = (n-1) * Diskkapazität
- https://de.wikipedia.org/wiki/RAID#/media/Datei:RAID_5.svg

### Was ist ein Journaling-Dateisystem?

Ein Journaling-Dateisystem ist ein Dateisystem, das alle Änderungen vor dem eigentlichen Schreiben in einem dafür reservierten Speicherbereich, dem Journal, aufzeichnet. Damit ist es zu jedem Zeitpunkt möglich, einen konsistenten Zustand der Daten zu rekonstruieren, auch wenn ein Schreibvorgang an beliebiger Stelle abgebrochen wurde. 

### Wie funktioniert das Dateisystem FAT (File Allocation Table)?

- Tabelle aller Blöcke + Dateien wird auf der Platte abgelegt (verkettete Liste pro Datei)
- Verzeichniseintrag = erster Block einer Datei jeweils
- Problem: Die FAT sollte im RAM sein. Doof.

### Wie funktioniert das Unix-Dateisystem?

- Jede Datei bekommt ihren Index-Node (Datenstruktur mit Blockadressen) zugeordnet
- I-Node nur im RAM, wenn Datei offen
- I-Node Größe begrenzt.
- Beispiele:
  - Verzeichnis = besondere Datei + I-Node
  - Hardlink = zweiter Dateiname mit dem selben I-Node
  - Softlink = Datei mit Pfadangabe zur anderen Datei
