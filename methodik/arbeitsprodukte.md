# Arbeitsprodukte des Requirements Engineering

Dieses Dokument hält fest, welche RE-Arbeitsprodukte für R3cOSINT geführt
werden, wozu, von wem und mit welcher Lebensdauer. Grundlage ist der
Projektauftrag im Produkt-Repository, Abschnitt 6.3
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.3]. Die Arbeitsprodukte
selbst liegen im Produkt-Repository und werden von hier aus nur verwiesen,
nie kopiert — Begründung der Aufteilung in Abschnitt 1.3
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-1.3].

## Herleitung

Für einen partizipativen RE-Prozess (siehe `re-prozess.md`) sieht IREB als
Arbeitsprodukte ein Product Backlog mit User Stories und Prototypen vor.
Beides ist im Projekt vorgesehen. Ergänzt werden drei Arbeitsprodukte, die
im ursprünglichen Auftrag fehlten: Stakeholderliste, Glossar und
Kontextmodell [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.3].

## Übersicht

| Arbeitsprodukt | Wozu | Verantwortlich | Lebensdauer | Stand im Produkt-Repository |
|---|---|---|---|---|
| **Stakeholderliste** | Festhalten, wer betroffen ist und mitredet: je Stakeholder mindestens Name, Funktion und Rolle, Kontakt, Verfügbarkeit, Relevanz, Fachgebiet, Ziele und Interessen | Requirements Engineer | sich weiterentwickelnd | noch nicht angelegt |
| **Glossar** | Verbindliche Definitionen aller Fachbegriffe; Verwendung für alle Arbeitsprodukte und Oberflächentexte verpflichtend | Requirements Engineer, ein benannter Verantwortlicher | langlebig | noch nicht angelegt |
| **Kontextmodell** | Systemgrenze, Kontextgrenze, Scope, externe Akteure und Schnittstellen | Software Architect | sich weiterentwickelnd | noch nicht angelegt |
| **Product Backlog** | Geordnete Anforderungen mit Anforderungsart, Priorisierung und Abnahmekriterien | Product Owner | sich weiterentwickelnd | noch nicht angelegt |
| **Interaktiver Prototyp** | Anforderungen am laufenden Bild ermitteln und validieren; Freigabe-Gate vor jedem Frontend-Produktionscode | UX/UI-Designer (fachlich), Requirements Engineer (methodisch) | kurzlebig, Wegwerf | vorhanden: [PERMALINK: prototype/OSINT_Plattform_Demo.html], wird ergänzt, nicht ersetzt |
| **Projektauftrag** | Baseline der vereinbarten Anforderungen | Protocol Master | langlebig, änderungskontrolliert | vorhanden: [PERMALINK: docs/00_Projektauftrag.md] |

## Einzelheiten je Arbeitsprodukt

**Stakeholderliste.** Absehbar sind mindestens: Ermittler des Dezernats
als Endbenutzer, Dezernatsleitung, Informatik der Kantonspolizei Bern,
kantonaler Datenschutzbeauftragter, Staatsanwaltschaft als Empfängerin der
Exporte, der Studienkollege, die betreuende Dozentur der FFHS. Die Liste
wird vom Requirements Engineer vervollständigt
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.3].

**Glossar.** Für dieses Projekt überdurchschnittlich wichtig, weil
Begriffe teils rechtliche Bedeutung tragen: Der Unterschied zwischen
verdeckter Fahndung und verdeckter Ermittlung ist kein sprachlicher,
sondern entscheidet über Zulässigkeit. Zu definieren sind unter anderem
Fall, Entität, Alias-Profil, Schutzstufe, Ermittlung, Recherche, Export,
Beweismittel. Synonyme werden gekennzeichnet, Homonyme vermieden
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.3].

**Product Backlog.** Jeder Eintrag wird einer der drei Anforderungsarten
nach IREB zugeordnet (funktionale Anforderung, Qualitätsanforderung,
Randbedingung), Qualitätsanforderungen messbar mit ISO/IEC 25010 als
Checkliste, Priorisierung ergänzt um das Kano-Modell. Randbedingungen aus
dem präskriptiven Teil werden nicht priorisiert, sie sind gesetzt
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.4]. Ein Eintrag darf
erst in einen Sprint, wenn er die Definition of Ready erfüllt (siehe
`scrum-aufbau.md`).

**Interaktiver Prototyp.** Methodisch ein exploratives Arbeitsprodukt zur
Validierung von Anforderungen im Sinne von IREB — das ist der Grund, warum
er vor dem Frontend steht, nicht nur ein praktischer
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.7]. Er ist als
Wegwerf-Prototyp festgelegt: Der Code wird nach der Freigabe nicht
weiterverwendet; weitergegeben werden Bildschirmfluss, Komponenteninventar,
Design-Tokens, Oberflächentexte, Review-Entscheide und der synthetische
Datenbestand [PERMALINK: docs/00_Projektauftrag.md#abschnitt-5.6].

**Projektauftrag.** Erste Baseline der Anforderungen. Jede spätere
freigegebene Fassung wird als neue Baseline gekennzeichnet, mit
Versionsnummer und fortgeführtem Änderungsprotokoll
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.6].

## Verweise statt Kopien

Alle Nachweise aus diesem Repository auf Arbeitsprodukte im
Produkt-Repository verwenden feste Verweise mit vollständiger
Commit-Prüfsumme. Das Produkt-Repository führt dafür unter
`docs/NACHWEISE.md` ein erzeugtes Nachweisverzeichnis, das bei jedem
Meilenstein neu erzeugt wird [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.6].

## Offene Punkte

- [OFFEN] Die Ablagepfade von Stakeholderliste, Glossar, Kontextmodell,
  Product Backlog sowie Definition of Ready und Done sind im
  Projektauftrag nicht festgelegt. Sie entstehen mit Schritt 3 der
  Lieferreihenfolge [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2];
  die Verweise hier werden dann nachgeführt.
- [OFFEN] Der benannte Verantwortliche für das Glossar ist noch nicht
  bestimmt.
- [OFFEN] Das Nachweisverzeichnis `docs/NACHWEISE.md` im
  Produkt-Repository ist noch nicht angelegt.

## Platzhalter in diesem Dokument

Die Automatik ersetzt diese Platzhalter durch feste Verweise mit
vollständiger Commit-Prüfsumme:

- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.3]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.4]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.6]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.7]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-5.6]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-1.3]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2]
- [PERMALINK: docs/00_Projektauftrag.md]
- [PERMALINK: prototype/OSINT_Plattform_Demo.html]
