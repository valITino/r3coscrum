# Konfiguration des RE-Prozesses nach IREB

Dieses Dokument leitet her, wie das Requirements Engineering für R3cOSINT
konfiguriert ist. Grundlage sind der Projektauftrag im Produkt-Repository,
Abschnitte 6.1 und 6.2 [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1]
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.2], sowie der IREB CPRE
Foundation Level, Lehrplan v3.3.0.

## Ausgangspunkt: zwei Rahmenwerke, bewusst getrennt

Die Planung folgt zwei Rahmenwerken, die sich ergänzen statt konkurrieren:

- **IREB CPRE Foundation Level v3.3.0** für das Requirements Engineering.
  Es beantwortet: Was soll das System leisten, wie gut, und woran erkennt
  man das.
- **Scrum Guide 2020** für den Entwicklungsprozess. Er beantwortet: In
  welcher Reihenfolge, in welchem Takt, mit welchen Ereignissen.

Die Trennung ist kein Formalismus. Ein Product Backlog ist eine
Dokumentationsstruktur für Anforderungen, kein Ersatz für Requirements
Engineering: Wer nur Scrum macht, hat eine Reihenfolge, aber keine
geprüften Anforderungen. Umgekehrt liefert RE ohne Prozessrahmen keine
Lieferfähigkeit. [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1]

## Die drei Facetten und ihre Einordnung für R3cOSINT

Nach IREB gibt es keinen allgemeingültigen RE-Prozess. Er wird anhand von
drei Facetten mit je zwei Polen konfiguriert. Die Einordnung für R3cOSINT
ist im Projektauftrag festgelegt
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.2]:

| Facette | Pole | Einordnung R3cOSINT | Begründung |
|---|---|---|---|
| **Zeit** | linear / iterativ | **iterativ** | Entwicklung nach Scrum; ein Teil der Anforderungen entsteht erst am laufenden Prototyp |
| **Zweck** | präskriptiv / explorativ | **explorativ, mit präskriptivem Teil** | Die fachlichen Anforderungen werden erarbeitet; die rechtlichen und datenschutzrechtlichen Vorgaben sind vorab verbindlich und nicht verhandelbar |
| **Ziel** | kundenspezifisch / marktorientiert | **kundenspezifisch** | Auftraggeber ist das eigene Dezernat; die Stakeholder sind namentlich bekannt und erreichbar |

## Ergebnis: partizipativer Prozess mit präskriptivem Teilbereich

Aus der Kombination iterativ, explorativ und kundenspezifisch ergibt sich
ein **partizipativer RE-Prozess** — mit einem klar abgegrenzten
**präskriptiven Teilbereich** für Recht und Datenschutz. Die massgebenden
Vorgaben dieses Teilbereichs stehen im Projektauftrag, Abschnitt 4.4
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.4].

## Warum diese Mischung gewählt wurde

Die Mischung ist bewusst so und keine Unschärfe. Der Massstab dafür steht
im Projektauftrag: Ein Anwendungsfall im Graphen darf sich über mehrere
Sprints entwickeln — eine Aufbewahrungsfrist nicht.

- Der **explorative Teil** passt zum Projekt, weil zu Beginn kein
  Produktionscode und kein festgelegter Tech-Stack existiert und die
  fachlichen Anforderungen am Prototyp und im Dialog mit den bekannten
  Stakeholdern erarbeitet werden. Der interaktive Prototyp ist dabei ein
  Validierungsmittel im Sinne von IREB
  [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.7].
- Der **präskriptive Teilbereich** ist nötig, weil R3cOSINT für den echten
  Einsatz bei der Kantonspolizei Bern gebaut wird. Rechtliche und
  datenschutzrechtliche Vorgaben werden nicht erarbeitet, sondern gelten
  vorab. Im Backlog werden beide Teile deshalb unterschiedlich behandelt:
  Der präskriptive Teil ist nicht verhandelbar und wird **nicht neu
  priorisiert, sondern nur terminiert**
  [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.2]
  [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.4].
- Die **kundenspezifische** Ausrichtung erlaubt direkte Beteiligung: Die
  Stakeholder sind erreichbar, Klärungen laufen über den Auftraggeber
  statt über Marktannahmen.

## Zuständigkeiten

Der RE-Anteil liegt bei der Rolle Requirements Engineer, der Prozessanteil
beim Scrum Master, die Ordnung des Backlogs beim Product Owner. Nach IREB
nimmt der Product Owner häufig zugleich die Rolle des Requirements
Engineers ein; hier bleiben die beiden getrennt, damit nicht dieselbe
Instanz Anforderungen erhebt und priorisiert
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1].

## Vorgehen: die fünf Konfigurationsschritte

Der Requirements Engineer arbeitet die fünf Konfigurationsschritte nach
IREB der Reihe nach ab und dokumentiert jeden
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.2]:

1. Einflussfaktoren analysieren (Entwicklungskontext, Verfügbarkeit der
   Stakeholder, Kritikalität, Randbedingungen, Zeit und Budget,
   Volatilität der Anforderungen).
2. Facettenkriterien beurteilen — die Tabelle oben ist die Vorgabe aus dem
   Projektauftrag; sie ist zu **belegen, nicht zu übernehmen**.
3. Prozess konfigurieren.
4. Arbeitsprodukte bestimmen (siehe `arbeitsprodukte.md`).
5. Praktiken auswählen (Ermittlungs-, Validierungs- und
   Priorisierungstechniken).

## Offene Punkte

- [OFFEN] Die Abarbeitung der fünf Konfigurationsschritte steht aus. Sie
  gehört zu Schritt 3 der Lieferreihenfolge
  [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2], der noch nicht
  begonnen ist. Insbesondere ist die Facettenbeurteilung (Schritt 2) noch
  mit einer eigenen Analyse zu belegen; dieses Dokument gibt bis dahin nur
  die Vorgabe aus dem Projektauftrag wieder.
- [OFFEN] Die Auswahl der Praktiken (Schritt 5) ist im Projektauftrag
  nicht festgelegt.

## Platzhalter in diesem Dokument

Die Automatik ersetzt diese Platzhalter durch feste Verweise mit
vollständiger Commit-Prüfsumme:

- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.2]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.4]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.7]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.4]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2]
