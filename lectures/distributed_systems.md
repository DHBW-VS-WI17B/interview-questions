### Was sind verteilte Systeme?

- Verbund von verschiedenen Rechnern über verschiedene Protokolle

### Was sind Ziele verteilter Systeme?

- Verschiedene Systeme verbinden
- Informationen austauschen
- Ungenutzte Ressourcen nutzen
- Lasten verteilen
- Ausfallsicherheit
- Skalierbarkeit

### Wann spricht man von transparenten verteilten Systemen?

- Wenn die App gegenüber dem Nutzer wie ein einziges System wirkt.

### Was ist das ISO OSI Modell?

- Layer 1: Physikalische Schicht
- Layer 2: Sicherungsschicht (Übertragungsfehlerkorrektur)
- Layer 3: Netzwerkschicht (Routing mit z.B. IPv4)
- Layer 4: Transportschicht (Aufteilung der Daten in Pakete z.B. TCP / UDP)
- Layer 5: Sitzungsschicht (kaum benutzt)
- Layer 6: Darstellungsschicht (kaum benutzt)
- Layer 7: Anwendungsschicht (z.B. HTTP, SSH, FTP, SMTP)

### Was ist ACID?

Eigenschaften einer Datenbank-Transaktion

- Atomar: Wird ganz oder gar nicht ausgeführt
- Konsistent: Nach der Transaktion keine inkonsistente Zustände
- Isoliert: Parallele Transaktionen beeinflussen sich nicht.
- Dauerhaft: Endergebnis wird gespeichert

### Wie kann grundsätzlich kommuniziert werden?

- synchron: Request/Response, RPC, eine HTML-Seite laden
- asynchron: Callback, Polling, Email, Sockets
- nachrichtenorientiert: PubSub, MQTT-Sensor

### Nenne Softwarearchitekturen

- Schichtmodell (3-Tier: Präsentation, Anwendung, Datenspeicher)
- Objektbasiert (Objekte reden miteinander über Methodenaufrufe)
- Ereignisbasiert: Event Loop arbeitet Nachrichten ab z.B. node.js
- Architektur mit gemeinsamer DB
- Peer-to-Peer

### Was ist ein Remote Procedure Call (RPC)?

- "Methodenaufruf über das Netz"

### Nenne Client-Arten

- Thin-Client (UI wird zwischen Client und Server aufgeteilt)
- Klassischer Client in der 3-Tier Architecture (UI ausschließlich clientseitig)
- SPA & REST
- Rich Client: (UI und Anwendungslogik auf dem Client)
- PWA

### Was macht eine Service Oriented Architecture aus?

- Services eines Unternehmens in viele, kleine, möglichst unabhängige Dienste aufzuteilen. Kleinere Services sind einfacher zu warten, können schneller und flexibler ersetzt werden und können eventuell auch Daten für andere Services bereitstellen

### Was sind Microservices?

- Anwendung in viele kleine unabhängige Dienste/Prozesse/Module zerlegt werden, die miteinander kommunizieren (über REST).
- Das Prinzip ist ähnlich wie bei SOA, nur geht es hier nur um eine Anwendung nicht um ein Informationssystem, das ein Geschäftsprozess abbildet.

### Wie kann man Cloud-Computing aufteilen?

- public: AWS / Azure / GCP
- private: Eigene Cloud -> z.B. eigene Firewall
- hybrid: Public + Private

### Erkläre das MVC-Pattern

- Model: DB-Zugriff, Datenmodell
- View: Präsentationsschicht
- Controller: Eingabe und Verarbeitung von Daten

### Was ist REST?

Representational State Transfer (CRUD HTTP etc.)

### Was ist die Same Origin Policy (SOP)?

- JS darf keine Scripts von anderem Host ausführen
- Kann mit CORS-Einstellungen gefixt werden

### SaaS, PaaS, IaaS?

- IaaS: VM mieten
- PaaS: Azure Function mieten
- SaaS: Salesforce mieten

### Was ist ein Container?

- In einem Containerkann eine Anwendung mit ihren gesamten Bibliotheken, Dateien und Konfigurationsdaten gepackt werden und auf einem Rechner deponiert und ausgeführt werden.
- Container teilen sich ein Betriebssystem, laufen aber als gegenseitig isolierte Prozesse, sind dadurch unabhängig und können auf jedem Hostsystem ausgeführt werden.

### Was ist Serverless Computing?

- Azure Functions, AWS Lambda
- "Server läuft nur, wenn er gebraucht wird."

### Was ist eine Progressive Web App (PWA)?

- App, die aus HTML/CSS/JS besteht und wieeine responsive Webseite aussieht.
- Installierbar wie jede andere App
- Service Worker spricht ggf. mit remote Servern
- Beispiel: https://photopea.com

### Was ist Not only SQL (NoSQL)?

- Nicht-relationale, auf Skalierbarkeit und Hochverfügbarkeit optimierte Datenbanken.
- Eventual Consistency: Transkationen nicht isoliert und konsistent (last write wins)
- Kategorien:
  - Dokumentenorientiert (key-document): CouchDB, MongoDB
  - Key-Value: Amazon Dynamo, Redis, Riak
  - Spaltenorientiert (Schneller Zugriff auf Spaltensummen): Hbase
  - Graphen-DB (Baum/Netzwerkstrukturen): Giraph, Neo4J

### Was ist das CAP-Theorem?

- Theorem: Nie sind alle drei Eigenschaften voll erfüllt
  - Consistency: Alle Nutzer sehen immer die gleichen Daten
  - Availability: Alle Nutzer können immer zugreifen
  - Partition Tolerance: DB kann auf mehere Nodes verteilt werden und einer kann ausfallen

### Wie funktioniert eine Blockchain?

- Dezentral
- Transaktionen in Blöcken
- Blöcke sind über Hashes verbunden
- Längste gewinnt

### Nenne Konsensmechanismen

- Mining = Proof of Work: Auswahl des Teilnehmers, der den letzten Block beglaubigt, findet durch Berechnung eines Rätsels statt. Die Rechenleistung ist entscheidend.
- Proof of Stake: Hier entscheidet das Vermögen in Bitcoins eines Teilnehmers.
- Practical Byzantine Fault Tolerance (PBFT): Hier entscheidet eine Mindestanzahl von Teilnehmern, die sich auf die Gültigkeit einer Transaktion einigen.
- Proof of Burn: Miner muss einen Einsatz in Bitcoins leisten ("verbrennen"), um Blocks bestätigen zu dürfen. 

### Wie funktioniert Cross Site Scripting (XSS)?

- Code über Form o.Ä. einschleusen
- Opfer führt den Code ausversehen aus

### Was ist Cross Site Request Forgery (CSRF)?

- Angreifer manipuliert eine HTTP Request vom Opfer
- TLS oder JWT fixen das z.B.

### Was ist eine SQL-Injection

- SQL-Query einschleusen

### Nenne Hash-Funktionen und Einsatzgebiete für Hash-Funktionen

- SHA256, SHA512
- Downloadprüfsummen, Passwörter speichern, Email-Signatur

### Wie feststellen das Private Key und Public Key zusammen gehören?

- Beides einer Certification Authority (CA) vorlegen und von deren privat Key signieren lassen.
- Sich treffen und die Keys vergleichen
