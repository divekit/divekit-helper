# Anforderungen

## Allgemein

- Jedesmal, wenn man ein Commit auslöst, schaut der Helper in das Repo und gibt Hinweise. 
- Bekommt als Input:
  - Zugriff auf Repo selbst (kann alle Klassen auslesen)
  - ggfs. Meta-Informationen, welche Klassen von Studies angelegt / verändert werden
  - Zugriff auf XML-File mit Test-Ergebnissen (z.B. sind da Stacktraces drin)
- Darstellung der Hilfe sollte auf der Test-Page des Studierenden sein
- Regeln werden als Teil des Origin-Repos hinterlegt

## Todos

- Beispiel-XMLs zur Verfügung stellen

## Optionen

- 1. Option: Textuell
`If OWNCLASS appears in stacktrace, give message MESSAGE ...`
- 2. Option: Java API
`if ( divekitHelper().contains().ownClass() ... ) `

## Bausteine, die man braucht

- Liste eigener Klassen
- Anzahl der Commits (abgebildet in Level für die Hilfe)
- Commit-Frequenz (# Commits / Zeitspanne)
  - müsste man eigentlich pro Aufgabe machen 
- Zeit seit letzter Hilfe
- Ausgaben der Tests (im XML File)
- Tabellentests (nicht Teil des Helper-Projekts - aber Anforderungen an Schnittstellen sollten definiert werden) 
  - Liste der "zuviel-Worte" in Spalte ...
  - Liste der fehlenden Worte" in Spalte ...
  - Namen und Typ der Zeilen und Spalten
- Diagramme
  - Liste der erwarteten / erwarteten / fehlenden Klassen
  - Liste der erwarteten / fehlenden Assoziationen
  - "Illegale" UMLet-Elemente
- Annotationen der Klassen (kann man mit Java Reflection auslesen)
  - @Entity, @ElementCollection, ...  

## ST1

- M0 - Coding Basics
  - Ergibt eher weniger Sinn. 
- M1 - Glossar & Fachliches Datenmodell  
  - Tabellentests zum Glossar
    - **müssen sowieso überarbeitet werden**, nicht Teil des Helpers
      - oder-Ausdrücke
      - Schreibweisen - CamelCase vs. Schreibweise wie im Aufgaben-Text
      - alle Fehler sollten auf einmal ausgegeben werden
      - Hinweis auf Wort, was nicht hingehört
      - Hinweis auf fehlendes Wort
      - Tabellenspalten / Zeilen haben Namen, diese für Mengen / Listen an Begriffen
      - Tabellentest gibt die Tabelle direkt mit Hinweisen rot/grün zurück
    - zusätzlich sollte der Helper folgende Hinweise geben
      - Systembestandteil als Geschäftsobjekt ansehen
        - Regel wäre dann "wenn Tabellenspalten-Sets ein Mismatch haben, gib Hinweis '_TS1_ ist in _TS2_, bitte prüfen'
  - Fachliche Datenmodell
    - Jetzt schon ausgegeben wird: im Diagramm fehlt eine Klasse / eine Relation
    - Hinweis, wenn Mismatch Glossar - Diagramm
    - Hinweis auf ganz bestimmte falsche Assoziationen
- M2 - Use Cases
  - Use Case Diagramm
    - **sowieso sollte das (teil-)automatisiert werden**, nicht Teil des Helper-Projekts
      - Name des UC: es sollte möglich, verschiedene Optionen anzugeben (buy a .... buying a ...) 
  - Use Case Template
    - Automatisieren: Teile des Headers durch Helper abdecken
      - Helper: Verwechslung der Aktoren, Teile des Headers durch Helper abdecken
    - Nachbedingung im Ausnahmeszenario vergessen
- M3 - CRUD-Matrix plus Verhaltensmodellierung
  - Tabelle alle Zustände, alle Übergänge
  - Zustandsdiagramm
    - muss automatisiert werden
- M4 - LDM
  - siehe FDM
- M5 - JPA / DDD Basic Building Blocks
  - Annotationen durchschauen
    - Annotationen fehlen
    - bidirektionale Beziehung (kein Testfehler!)
    - falsche Annotation (@Embeddable)
    - Repo fehlt
    - Repo für VO
    - Repo mit falschem Entity-Typ / ID-Typ
    - VO equals fehlt
    - VO nicht immutable
    - irgendwo im Stacktrace taucht eigene Klasse auf 
  
  
