# r3coscrum

Methodik und Nachweise zum Projekt **R3cOSINT**. Das Produkt selbst liegt in
[r3cosint](https://github.com/valITino/r3cosint).

Hier steht, *wie* gearbeitet wird und *warum* so entschieden wurde. Die
Arbeitsmittel selbst — Backlog, Glossar, Stakeholderliste, Definition of Ready
und Done — liegen bewusst im Produkt-Repository. Begründung im Projektauftrag,
Abschnitt 1.3.

## Hinweis vom 2026-10-26: eingefaltet in r3cosint (Prozess-Schnitt PS-4)

Dieses Repository wird nicht mehr fortgeschrieben. Die Methodiktexte unter
`methodik/` und die Übergabevermerke in `UEBERGABE.md` liegen byte-gleich im
Produkt-Repository r3cosint unter docs/methodik/ (Quellen mit Quell-Commit und
SHA-256 je Datei in docs/methodik/QUELLEN.md; eingeführt mit dem Commit
`b24f7813ddf1567bbc7c7f94d3ffad6ebb68189f` von r3cosint). Der vollständige Verlauf dieses Repositories
liegt in r3cosint als Zweig archiv/r3coscrum (Spitze
`6bb7834c546baadf402ebd428ab94f079471ca42`, 93 Commits); eine Commit-Prüfsumme
dieses Repositories löst dort unter https://github.com/valITino/r3cosint/commit/<Prüfsumme>
auf. Der Arbeitsablauf eingang.yml ist mit diesem Stand entfernt; `nachweise/`
wird seit dem 2026-10-26 nicht mehr beschrieben (letzter Lauf: Stand
`fd9f40176999599be59401bbb33409ae6b9c2e08` von r3cosint). Archivierung und
Löschung nach der Übergangsfrist liegen beim Eigentümer (Weisung vom
2026-10-22, Vorlage docs/vorlagen/2026-10-22_prozess-schnitt.md in r3cosint,
Abschnitte 3 und 7).

## Aufbau

| Pfad | Inhalt | Wer schreibt |
|---|---|---|
| `methodik/` | Herleitung des RE-Prozesses nach IREB, Scrum-Aufbau, Entscheide | Mensch |
| `sprints/` | Sprint Reviews und Retrospektiven | Mensch |
| `nachweise/` | Verweise auf Artefakte im Produkt-Repository | **Automatik** |

## Regel für `nachweise/`

Dieses Verzeichnis wird von einem GitHub-Arbeitsablauf beschrieben, sobald im
Produkt-Repository ein Versionsschild gesetzt wird. **Nicht von Hand ändern** —
Änderungen gehen beim nächsten Lauf verloren.

Alles ausserhalb von `nachweise/` gehört den Autoren und wird von der Automatik
nie angefasst.

## Keine Kopien

Inhalte aus dem Produkt-Repository werden nicht kopiert, sondern verlinkt, mit
vollständiger Commit-Prüfsumme. Verweise auf `main` sind unzulässig, weil sie
sich mit jedem Commit ändern und damit als Nachweis untauglich sind.

Einzige Ausnahme: der eingefrorene Abzug unter `nachweise/abzug/` für die
Abgabe, damit die Arbeit ohne Zugriff auf das Produkt-Repository lesbar bleibt.

## Sprache

Deutsch, Schweizer Schreibweise. Kein Eszett, gerade Anführungszeichen.
