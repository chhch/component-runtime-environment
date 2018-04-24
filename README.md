# component-runtime-environment

## About

Development of a component runtime environment for a semester project at the university.

## Underlying Exercises

### Exercise 2
 
-   [X] FA1: Der Component Assembler muss die Laufzeitumgebung starten können.
-   [X] FA2: Der Component Assembler muss die Laufzeitumgebung stoppen können.
-   [X] FA3: Der Component Assembler muss neue Komponenten aus einem lokalen Verzeichnis des Rechners in die Laufzeitumgebung einsetzen (deployen) können.
-   [X] FA4: Der Component Assembler muss eingesetzte Komponenten in der Laufzeitumgebung ausführen können. Eine Start-Methode sollte dabei mit Hilfe einer Annotation im Rahmen eines Komponentenmodells definiert werden.
-   [X] FA5: Der Component Assembler soll mehrere Komponenten gleichzeitig (parallel) ausführen können.
-   [X] FA6: Der Component Assembler muss in der Lage sein, die Status der aktuell eingesetzten Komponenten über die Laufzeitumgebung abzurufen. Ein Status sollte pro Komponente folgendes beinhalten: Laufende Identifikationsnummer, Name, Zustand.
-   [X] FA7: Der Component Assembler muss Komponenten in der Laufzeitumgebung stoppen können. Auch hierzu sollte das Komponentenmodell eine „entsprechende“ Operation bereitstellen.
-   [X] FA8: Der Component Assembler muss Komponenten aus der Laufzeitumgebung löschen können.

Folgende strukturelle Eigenschaften sollte eine Komponente besitzen:

-   [X] Eine „deploybare“ Komponente entspricht einem .jar-File,
-   [X] Ein .jar-File kann wiederum eine beliebige Menge aus Klassen enthalten. In einem .jar-File muss mindestens eine Klasse enthalten sein.
-   [X] Eine Komponente ~~kann~~ muss ein Meta-File besitzen. / Muss nur ausführbare jars
-   [X] Klassen in einem .jar-File können in Packages angeordnet sein.

Weitere Anforderungen:

-   [X] Deployment von Komponenten (Muss)
-   [X] Lebenszyklus realisieren: start und stop von Komponenten (parallele Ausführung) (Muss)
-   [X] Status-Abfrage einer Komponente (Muss)
-   [X] Fehlerhandling bei Komponenten (Co)
-   [X] LZU muss die Abhängigkeiten auflösen und bereitstellen (Muss) / Test mit Log4J2
-   [X] Konfiguration von Komponenten (Muss) / Name, Id, Status, Annotationen
-   [X] Konflikte auflösen bei Abhängigkeiten (Muss) / Test mit Log4J2
-   [X] Löschen von Komponenten (Muss)
-   [X] Einhalten von Sicherheitsaspekten (Co)
-   [X] Starten einer LZU (Muss)
-   [X] Stoppen einer LZU (Muss)
-   [X] Unabhängigkeit von LZUs (W)
-   [X] Fehlerhandling einer LZU (Co)
-   [X] Verfügbarkeit garantieren von Komponenten (Muss)

### Exercise 3

-   [X] CR1: Die aktuelle Konfiguration einer Laufzeitumgebung (welche Komponenten wurden in welcher Reihenfolge eingesetzt) soll stets persistent auf einem externen Server abgespeichert werden, so dass bei einem Absturz der lokalen Laufzeitumgebung der Zustand (= die Konfiguration) der Laufzeitumgebung wiederhergestellt werden kann. Der Zustand einer Komponente braucht nicht gespeichert werden.
-   [X] CR2: Erweitern sie ihre Laufzeitumgebung um einen horizontalen Logging-Dienst, der von ihrer Laufzeitumgebung für alle kompatiblen Komponenten angeboten werden soll. Möchte eine Komponente diesen Dienst verwenden, so muss sie eine typ-konforme Variable in der Start-Klasse (wo @Start-Methode vorhanden) definieren und diese mit einer Annotation versehen (siehe Aufgabe).
-   [X] Die konkrete Implementierung sollte dann auf einer Console folgendes ausgeben: `++++ Runtime-Log: Meldung aus Component: Prozess gestartet ([TimeStamp])`
-   [X] Eine Auslagerung der relevanten Konfigurationsdaten auf einen externen Server ist nicht notwendig, das Abspeichern kann in einem lokalen File oder unter Verwendung eines lokalen Datenbanksystems prototypisch erfolgen.

### Exercise 5

-   [X] Demonstrieren sie die Machbarkeit anhand einer prototypischen Umsetzung innerhalb ihrer Laufzeitumgebung. Ziel: ihre ausgewiesenen Komponenten (nicht alle Klassen!) sollen sich gegenseitig über Zustandswechseln flexibel informieren können. (Bei der Umsetzung mit DI und Observer-Modell an <https://jcp.org/en/jsr/detail?id=299> orientieren.)

### Exercise 6

-   [X] Erweitern sie ihre Laufzeitumgebung um eine Funktionalität zur flexiblen Komposition von eingesetzten Komponenten. Orientieren sie sich dabei um die Ideen rund um das Pattern „Dependency Injection“ (Kapitel 4).
-   [X] Führen sie ein Scope-Management in ihre Laufzeitumgebung ein, so dass Referenzen zu konkreten Komponenten abhängig vom Lebenszyklus einer Komponente injiziert werden (siehe Aufgabe).
-   [X] Entwickeln sie ein Web-basiertes Frontend für ihre Laufzeitumgebung, mit der sie wesentliche Befehle ausführen können. Dieses Web-Frontend sollte dabei auf den eingeführten Technologien der Vorlesungen (vgl. Kapitel 5) aufbauen.