# Anforderungen

## Allgemein

- Jedesmal, wenn man ein Commit auslöst, schaut der Helper in das Repo und gibt Hinweise. 
- Bekommt als Input:
  - Zugriff auf Repo selbst (kann alle Klassen auslesen)
  - ggfs. Meta-Informationen, welche Klassen von Studies angelegt / verändert werden
  - Zugriff auf XML-File mit Test-Ergebnissen (z.B. sind da Stacktraces drin)
- Darstellung der Hilfe sollte auf der Test-Page des Studierenden sein

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
- Zeit seit letzter Hilfe
- Ausgaben der Tests (im XML File)
- Tabellentests
  - Liste der "zuviel-Worte" in Spalte ...
  - Liste der fehlenden Worte" in Spalte ...
  - Namen und Typ der Zeilen und Spalten


## ST1

- M0 - Coding Basics
  - Ergibt eher weniger Sinn. 
- M1 - Glossar & Fachliches Datenmodell  
  - Tabellentests zum Glossar
    - müssen sowieso überarbeitet werden
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
