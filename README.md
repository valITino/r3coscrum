# r3coscrum

Methodik und Nachweise zum Projekt **R3cOSINT**. Das Produkt selbst liegt in
[r3cosint](https://github.com/valITino/r3cosint).

Hier steht, *wie* gearbeitet wird und *warum* so entschieden wurde. Die
Arbeitsmittel selbst — Backlog, Glossar, Stakeholderliste, Definition of Ready
und Done — liegen bewusst im Produkt-Repository. Begründung im Projektauftrag,
Abschnitt 1.3.

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
