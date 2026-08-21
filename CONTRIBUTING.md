# Richtlinien für Mitwirkende

Dieses Repository ist der Methodik- und Nachweisteil des Projekts R3cOSINT
(Aufteilung im [Projektauftrag, Abschnitt 1.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)).
Hier entsteht kein Produktionscode: Gearbeitet wird an Texten; einzige
Ausnahme sind die Arbeitsabläufe unter `.github/workflows/`.

## Zweige und Pull Requests

- Kein direkter Push auf `main`. Jede Änderung läuft über einen Pull
  Request; externe Mitwirkende arbeiten aus einem Fork.
- Eine Einheit, ein Pull Request: Jeder Pull Request behandelt ein
  abgegrenztes Anliegen.
- Kein Force Push und keine Historienänderung auf gemeinsamen Zweigen.
  Veröffentlichte Historie wird nicht umgeschrieben.
- Der Merge erfolgt ausschliesslich durch den Repository-Eigentümer
  (valITino). Die Zuständigkeit für alle Pfade ist in `.github/CODEOWNERS`
  hinterlegt.

## Ausnahme: der Ordner `nachweise/`

Einzige Ausnahme vom Pull-Request-Weg: Den Ordner `nachweise/` beschreibt
ausschliesslich die Automatik unter `.github/workflows/`, und zwar direkt.
Er wird nie von Hand geändert — Handänderungen gehen beim nächsten Lauf
verloren.

## Sprache und Verweise

- Deutsch, Schweizer Schreibweise. Kein Eszett — immer "ss". Gerade
  Anführungszeichen (" und '), keine typografischen.
- Verweise stets mit vollständiger Commit-Prüfsumme (40 Zeichen). Verweise
  auf `blob/main` sind unzulässig, weil sie sich mit jedem Commit ändern.
- Inhalte aus dem Produkt-Repository
  ([r3cosint](https://github.com/valITino/r3cosint)) werden nie kopiert,
  sondern verlinkt.

## Keine echten Daten

Das Repository ist öffentlich. Keine echten Fall- oder Personendaten —
nicht in Texten, nicht in Beispielen, nicht in Commit-Nachrichten.
