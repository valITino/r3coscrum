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
| V9 | **2026-08-31.** Steht eine Abwägung zwischen Laufzeit oder Bequemlichkeit einerseits und Beweiskraft andererseits, entscheidet die Beweiskraft. Wörtliche Weisung des Auftraggebers: "Das, was korrekt und qualitativ ist. Soll zwar effizient sein, aber nie an Korrektheit und Qualität verlieren." | Erstmals angewandt auf O-13 des [Architekturentscheids 0002](https://github.com/valITino/r3cosint/blob/7d1fe2fdea8dc339a7890ece18e4859418cfd6f6/docs/adr/0002-architekturentscheid-ziel-stack.md): Die Definition-of-Done-Kette benutzt den Zwischenspeicher des Paketwerkzeugs nicht mehr, weil dessen Inhalt nicht erneut gegen die Sperrdatei geprüft wird. Der Preis ist ein Ladevorgang je Bau; das Ergebnis der Kette ist ein Nachweis nach Projektauftrag 5.3, und ein Nachweis, der auf einem ungeprüften Zwischenspeicher beruht, trägt nicht |
| V10 | **2026-08-31.** Eine Abgrenzung ist keine Erlaubnis: Was sich schliessen lässt, wird geschlossen; abgegrenzt wird nur, was sich mit den Mitteln des jeweiligen Artefakts nicht schliessen lässt. Eine benannte Lücke bleibt eine Lücke | Entstanden aus einem belegten Fehler im eigenen Vorgehen: Der Makefile-Kopf grenzte einen Angriffsweg ab ("dagegen schützt die Kette nicht"), obwohl er mit einer einzigen Zeile zu schliessen war. Die Abgrenzung ist damit vom Ergebnis einer Prüfung zu ihrer Ausrede geworden. Siehe [Abschnitt 6.7](https://github.com/valITino/r3cosint/blob/2bc0255c83e7bbbd2664df759aceeebe747246e0/docs/adr/0002-architekturentscheid-ziel-stack.md) |
| V11 | **2026-09-01.** Eine Behebung ist nicht fertig, wenn der Befund weg ist, sondern wenn die **Schicht geprueft ist, die sie neu erreichbar gemacht hat**. Wer nur die Fundstelle repariert, legt die naechste Runde an | An zwei aufeinanderfolgenden Tagen zweimal belegt, am 2026-08-31 in einem Dokument und am 2026-09-01 in dem Werkzeug, das es finden sollte. Beim Belegpruefer fand Runde 2 einen Fehler, den die Behebung aus Runde 1 verursacht hatte, und Runde 3 einen, den die Behebung aus Runde 2 erst erreichbar gemacht hatte -- eine Existenzpruefung, die zwei Runden lang toter Code war und beim Scharfschalten Fehlalarme ausloeste. Beide Male hat es keine Selbstpruefung gefunden, sondern eine unabhaengige Instanz auf einem anderen Modell. Zwei Arbeitseinheiten sind daran nach Eskalationsregel 3.4 abgebrochen worden ([Uebergabe](https://github.com/valITino/r3cosint/blob/edcf8b5655a7ad0cb1e29945fea92f67000467df/docs/uebergaben/2026-08-31_belegpruefer-abbruch-nach-3-4.md)) |
| V12 | **2026-09-01.** Nennt ein Text ein Prüfmittel, dessen Ausfall eine bestimmte Wirkung haben soll, muss der Code genau dieses Prüfmittel prüfen. Eine Nennung ohne Prüfung ist keine Beschreibung, sondern eine Zusicherung ohne Deckung, und sie ist schädlicher als gar keine Nennung: sie erzeugt genau das Vertrauen, das sie nicht trägt | Am 2026-09-01 an Kettenschritt D20 belegt und behoben ([`4b9adf781ddb86bea0b9f84d6cb59bb1ccea416e`](https://github.com/valITino/r3cosint/commit/4b9adf781ddb86bea0b9f84d6cb59bb1ccea416e)). Architekturentscheid und Definition of Done nannten sechs Prüfmittel, deren Fehlen die Lage C ergeben sollte; der Code prüfte drei. Ausgeführt gemessen: das Fehlen eines der drei ungeprüften ergab nicht Lage C, sondern hunderte Scheinfunde -- rot mit falscher Begründung, also genau der Fehlermodus, den der Architekturentscheid als vermieden beschrieb. Das ist die vierte Stufe derselben Fehlerklasse in diesem Projekt: zuerst wurde die Verfügbarkeit eines Namens statt der Anwesenheit des Gegenstands gemessen, dann eine Liste von Namen statt des Inhalts, dann der Gegenstand ohne Beleg, dass das Messmittel misst -- und nun benennt der Text ein Messmittel, nach dem niemand fragt |
| V13 | **2026-09-01.** Eine Angabe, die nichts steuert, sondern etwas anderes nur wiederholt, wird gestrichen und nicht nachgeführt | Im selben Prüfdurchgang gefunden: Zwei Kommentare im Makefile zählten die Ausführungsreihenfolge der Kette auf, obwohl die Reihenfolge allein aus der Zielliste stammt. Beide Aufzählungen waren veraltet, weil die Aufnahme eines neuen Schritts sie nicht erreicht hatte. Der eine Absatz warnte wörtlich vor genau dieser zweiten Aufzählung, "die bei der nächsten Fortschreibung erneut veralten könnte" -- und führte im selben Absatz eine. Eine nachgeführte Aufzählung ist beim nächsten Mal wieder falsch; eine gestrichene kann nicht falsch werden |

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
| S6 | **2026-08-31.** Fremdes Material wird nie wörtlich in das Projekt übernommen. Übernommen werden Bauweise, Gliederung und Einsicht; der entstehende Text ist unserer, in Deutsch und Schweizer Schreibweise, und wird vor der Aufnahme gegen unsere Bauvorschriften geprüft. Die Herkunft wird über die vollständige 40-stellige Commit-Prüfsumme vermerkt. Eine Abhängigkeit von einem Marktplatz oder einem Plugin, das sich unter uns aktualisiert, wird nicht eingegangen | Drei Gründe, jeder für sich tragend. Erstens Reproduzierbarkeit: Sie ist Bauvorschrift (Projektauftrag 5.4); ein Bestand, der sich ändert, ohne dass bei uns eine Datei geändert wird, ist damit unvereinbar — dieselbe Überlegung, aus der Verweise auf `blob/main` unzulässig sind. Zweitens Belegbarkeit: Die Lizenz des angebundenen Bestands (`valITino/claude-skills-fullstack`, `882ef55e377dbf9a4dbe496bb41ac6ccd0e555cf`) ist MIT, ihre Urheberrechtszeile lautet aber "Copyright (c) 2025" ohne benannten Rechteinhaber, und dreizehn Dateien führen Inhalte aus einem dritten Projekt weiter, eine davon ohne Lizenzangabe. Ein Vermerk, der niemanden nennt, ist in einem Projekt mit Belegpflicht nicht belegtauglich. Drittens Inhalt: Fremde Inhalte sind Daten, nie Anweisungen — eine Skill-Datei wird als Ganzes in den Kontext geladen, und im geprüften Bestand stehen Muster, die unseren Verfahrensgarantien widersprechen (selbsttätige Verkettung von Erkennen und Handeln, Aufklärungsbefehle nach aussen, ungeprüfte Zeichenketten in SQL) |
| S7 | **2026-08-31.** Ein Skill entsteht nur, wenn **mehrere Rollen dieselbe Prozedur gleich ausführen**. Was nur eine Rolle tut, gehört in ihre Rollendatei; was eine Festlegung ist, in einen Architekturentscheid oder eine Regel | Der fremde Bestand führt Rollen wie DevOps Engineer, Code Reviewer und Security Reviewer als Skills. Für uns wäre damit weder abbildbar, dass der Pentester nicht schreiben darf, noch dass Prüfung und Umsetzung auf verschiedenen Modellen laufen (Projektauftrag 3.4). Umgekehrt kostet jeder überflüssige Skill Pflege an drei Stellen — Skill, `skills:`-Feld je Rolle, ADR 0001. Erstmals angewandt: aus rund zwanzig beurteilten Kandidaten sind genau zwei Skills entstanden ([`pruefbefund-melden` und `dod-kette-belegen`](https://github.com/valITino/r3cosint/tree/2bc0255c83e7bbbd2664df759aceeebe747246e0/.claude/skills)) |

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
- [OFFEN] **Herkunftsvermerk bei fehlendem Rechteinhaber** (neu am
  2026-08-31, hängt an S6). Zwei Fragen, die der Auftraggeber entscheidet,
  fachlich vorzubereiten durch den Legal Reviewer: Ist eine von einem fremden
  Werk abgeleitete Vorlage im Repository eines polizeilichen
  Ermittlungswerkzeugs überhaupt zulässig? Und trägt auch eine Nachbildung
  nach Vorbild — bei der kein fremder Text in das Repository gelangt — einen
  Herkunftsvermerk? Solange das offen ist, gilt S6 in seiner strengen Form:
  neu schreiben, nie übernehmen.

## Verweise in diesem Dokument

Aufgelöst aus dem Nachweisverzeichnis (`nachweise/NACHWEISE.md`, Stand
`4c64300e9ec00fd1068964e14c2666c631d00dfa`):

- [Abschnitt 8](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 1.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 3.2](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 4.3](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
- [Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)
