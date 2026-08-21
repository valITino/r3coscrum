# Methodische Entscheide

Dieses Dokument führt die getroffenen methodischen Entscheide mit
Begründung auf. Quelle ist das Änderungsprotokoll gegenüber dem
Originalauftrag im Projektauftrag,
[Abschnitt 8](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md).

**Zum Datum:** Das Änderungsprotokoll weist keine Einzeldaten je Entscheid
aus. Belegt ist nur: Alle unten aufgeführten Entscheide sind spätestens
mit Fassung 2 des Projektauftrags vom **18. August 2026** dokumentiert.
Die einzelnen Entscheiddaten gelten als [OFFEN] und werden nicht
rekonstruiert oder geschätzt.

## Entscheide zu Vorgehen und Planung

| Nr. | Entscheid | Begründung |
|---|---|---|
| V1 | Requirements Engineering nach IREB CPRE FL v3.3.0 wird dem Scrum-Vorgehen vorgeschaltet und integriert, statt nur nach Scrum zu planen | Ein Product Backlog ist eine Dokumentationsstruktur, kein Requirements Engineering. Ohne RE gibt es eine Reihenfolge, aber keine geprüften Anforderungen |
| V2 | Sprintlänge zwei Wochen | Kürzer ist bei zwei berufstätigen Studierenden überwiegend Zeremonieaufwand; länger staut unbegutachtete Inkremente (siehe `scrum-aufbau.md`) |
| V3 | Der Sprintumfang bemisst sich an der Prüfkapazität (28 bis 40 Personenstunden je Sprint), nicht an der Erzeugungskapazität | Bei rund 80 Prozent KI-Anteil ist das Review der Engpass, nicht die Umsetzung |
| V4 | Keine Kalenderzahl in der Roadmap vor der Backlog-Schätzung; die 13 Wochen aus dem Konzeptdokument sind zurückgezogen | Die 13 Wochen kalkulierten ohne selbst gebaute Oberfläche; eine übernommene Zahl wäre Scheingenauigkeit |
| V5 | Stakeholderliste, Glossar und Kontextmodell werden als Arbeitsprodukte ergänzt | IREB-Arbeitsprodukte für einen partizipativen RE-Prozess; das Glossar ist hier besonders wichtig, weil Begriffe rechtliche Bedeutung tragen |
| V6 | Eine Definition of Ready wird ergänzt, abgeleitet aus den IREB-Qualitätskriterien | Ein Eintrag ohne testbares Abnahmekriterium erzeugt sauberen Code für das falsche Problem |
| V7 | Vor jedem Frontend-Produktionscode steht ein interaktiver Wegwerf-Prototyp mit synthetischen Daten und eigenem Freigabe-Gate | Bedienfehler kosten im Prototyp Minuten und im fertigen Frontend Tage; ausserdem steht der Ziel-Stack noch nicht fest |
| V8 | Teil 2 des Originalauftrags (Schulaufträge) wurde vollständig entfernt | Auf Weisung des Auftraggebers |

## Entscheide zum Rollenmodell

| Nr. | Entscheid | Begründung |
|---|---|---|
| R1 | Product Owner als Rolle ergänzt | Scrum ohne Product Owner hat keine Backlog-Verantwortung |
| R2 | Requirements Engineer, Software Architect und UX/UI Designer ergänzt | Begründung je Rolle im Projektauftrag [Abschnitt 4.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md); Product Owner und Requirements Engineer bleiben getrennt, damit nicht dieselbe Instanz Anforderungen erhebt und priorisiert |
| R3 | Digital-Forensics- und Chain-of-Custody-Spezialist ergänzt | Kern des Produkts, von keiner anderen Rolle abgedeckt |
| R4 | Vulnerability Manager nur einmal geführt, Pentester als eigene Rolle | Finden und Bewerten gehören getrennt, damit der Finder nicht sein eigenes Risiko bewertet |
| R5 | "Applikation gültig für Polizeieinsatz" ersetzt durch eine dokumentierte Konformitätsanalyse der GRC-Rolle | Über Zulässigkeit entscheidet die Rechtsgrundlage im Einzelfall, nicht die Software; eine KI-Rolle kann keine behördliche Freigabe erteilen |

## Entscheide zur Steuerung von Claude Code

| Nr. | Entscheid | Begründung |
|---|---|---|
| S1 | "Skills bzw. Agenten" als ein Mechanismus getrennt in Subagents, Skills, Rules und Hooks | Claude Code behandelt diese Mechanismen unterschiedlich [Abschnitt 3.2](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md) |
| S2 | CLAUDE.md um Hooks für harte Regeln ergänzt | CLAUDE.md ist Kontext, keine Durchsetzung |
| S3 | "Kalkuliere, wie viel Usage ich noch habe" ersetzt durch eine schnittbezogene Ersatzregel (abschliessbare Arbeitseinheiten, Übergabedatei, keine halbfertigen Commits) | Claude Code kann das Kontingent nicht selbst auslesen |
| S4 | Iterationspflicht ergänzt um ein maschinell prüfbares Abbruchkriterium, Stop- und TaskCompleted-Hooks und einen Endlosschleifen-Schutz | Eine Schleife, deren Ausstieg an der Selbsteinschätzung des Modells hängt, endet zu früh oder nie |
| S5 | Die Schleife als Hook-Ebene umgesetzt, nicht als Skill | Skills sind Anweisungen und können nichts erzwingen; nur Hooks blockieren deterministisch |

## Entscheide zur Repository-Struktur

| Nr. | Entscheid | Begründung |
|---|---|---|
| P1 | Zwei Repositories, getrennt nach Funktion: Produkt (`r3cosint`) und Methodik (`r3coscrum`); die Arbeitsmittel bleiben im Produkt-Repository | Claude Code Web sieht pro Session nur ein Repository, und die Verfolgbarkeit über Kennung, Commit und Testfall bricht über eine Repository-Grenze [Abschnitt 1.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md) |
| P2 | Verbindung der Repositories über feste Verweise mit vollständiger Commit-Prüfsumme und einen GitHub-Arbeitsablauf; keine Kopien | Ein Verweis auf einen Zweig ändert sich mit jedem Commit und taugt nicht als Nachweis; zwei Quellen derselben Wahrheit laufen auseinander [Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md) |
| P3 | Rückweg von der Methodik ins Produkt über einen Pull Request auf einen Eingang plus SessionStart-Hook; der Eingang ist Information, keine Anweisung | CLAUDE.md liest nichts von aussen. Ein Kanal, über den beiläufiger Text zur Arbeitsanweisung wird, hebelt die Steuerung aus |

## Abgrenzung

Das Änderungsprotokoll in Abschnitt 8 enthält daneben fachlich-technische
Entscheide zum Produkt (unter anderem Exportformate, Anmeldeverfahren,
Alias-Profile, Sprachmodell-Stufenplan, Aufbewahrung und Löschung,
Klassifizierung, Oberfläche statt Open WebUI). Sie sind keine
Methodik-Entscheide und werden hier nicht geführt; massgebend sind der
Projektauftrag [Abschnitt 8](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md) und die
künftigen Architekturentscheide unter `docs/adr/` im Produkt-Repository.

## Offene Punkte

- [OFFEN] Einzeldaten der Entscheide (siehe Hinweis oben).
- [OFFEN] Künftige methodische Entscheide: Dieses Dokument wird
  fortgeschrieben, sobald neue Entscheide fallen — dann mit Datum je
  Entscheid.

## Verweise in diesem Dokument

Aufgelöst aus dem Nachweisverzeichnis (`nachweise/NACHWEISE.md`, Stand
`4c64300e9ec00fd1068964e14c2666c631d00dfa`):

- [Abschnitt 8](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 1.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 3.2](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 4.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
