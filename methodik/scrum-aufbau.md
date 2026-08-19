# Scrum-Aufbau

Dieses Dokument hält fest, wie Scrum für R3cOSINT aufgesetzt ist und warum.
Grundlage sind der Projektauftrag im Produkt-Repository, Abschnitt 6.8
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8], und der Scrum Guide
2020.

## Sprintlänge: zwei Wochen

Der Auftraggeber hat die Wahl delegiert; festgelegt sind **zwei Wochen**.
Begründung: Der Scrum Guide lässt einen Monat oder weniger zu. Bei einem
Team aus zwei berufstätigen Studierenden fällt der Zeremonieaufwand
kürzerer Sprints prozentual zu stark ins Gewicht. Ein Monat ist zu lang,
weil der Engpass nicht die Umsetzung ist, sondern das menschliche Review —
dann stauen sich zu viele unbegutachtete Inkremente. Zwei Wochen bieten
pro Sprint mehrere Abende und ein Wochenende für Reviews
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8].

## Ereignisse und Timeboxes

Die Ereignisse folgen dem Scrum Guide 2020, die Timeboxes sind anteilig
auf die Sprintlänge von zwei Wochen umgerechnet:

| Ereignis | Timebox |
|---|---|
| Sprint Planning | höchstens 4 Stunden |
| Daily Scrum | 15 Minuten |
| Sprint Review | höchstens 2 Stunden |
| Sprint-Retrospektive | höchstens 1,5 Stunden |

Die Ergebnisse von Sprint Reviews und Retrospektiven werden in diesem
Repository unter `sprints/` festgehalten.

## Verantwortlichkeiten

Scrum kennt drei Verantwortlichkeiten: Product Owner, Scrum Master,
Developers. Der ursprüngliche Auftrag nannte nur den Scrum Master; Product
Owner und weitere Rollen wurden ergänzt
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.3].

| Verantwortlichkeit | Aufgabe | Besonderheit in diesem Projekt |
|---|---|---|
| **Product Owner** | Ordnet das Product Backlog und entscheidet über Priorität | Bleibt vom Requirements Engineer getrennt, damit nicht dieselbe Instanz Anforderungen erhebt und priorisiert [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1] |
| **Scrum Master** | Prozess, Ereignisse, Hindernisbeseitigung | Arbeitsgrundlage Scrum Guide 2020; Schreibrechte nur auf Planungsartefakte [PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.2] |
| **Developers** | Umsetzung der Sprint-Backlog-Einträge | Die Umsetzung übernimmt zu rund 80 Prozent Claude Code über das Rollenmodell; der menschliche Anteil von rund 20 Prozent liegt bei Review, Freigabe und Feinschliff durch Auftraggeber und Studienkollege [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8] |

**Commitments:** Product Goal für das Product Backlog, Sprint Goal für das
Sprint Backlog, Definition of Done für das Inkrement.

## Definition of Ready gegenüber Definition of Done

Die beiden sind strikt zu unterscheiden: **Ready gilt für den Eingang in
den Sprint, Done für den Ausgang**
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8].

**Definition of Ready** — abgeleitet aus den IREB-Qualitätskriterien für
Anforderungen. Ein Backlog-Eintrag darf erst in einen Sprint gezogen
werden, wenn er je Eintrag adäquat, notwendig, eindeutig, in sich
vollständig, ohne Zusatzerklärung verständlich und prüfbar ist — es
existiert ein Abnahmekriterium, das sich als Test formulieren lässt. Für
das Backlog als Ganzes gelten Konsistenz, Redundanzfreiheit,
Vollständigkeit, Änderbarkeit, Verfolgbarkeit und Konformität zu den
rechtlichen Vorgaben. Die Definition of Ready ist der Ort, an dem der
menschliche Anteil am meisten bewirkt: Ein schlecht formulierter Eintrag
erzeugt sauberen Code für das falsche Problem
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.5].

**Definition of Done** — verbindlich für alle Rollen und formuliert als
**ausführbare Befehlskette**: Für jede Aufgabe ist festgelegt, welche
Befehle mit Rückgabewert 0 enden müssen, damit sie als erledigt gilt.
Damit hat die Iterationspflicht ein maschinell prüfbares Abbruchkriterium
statt einer Selbsteinschätzung des Modells. Was nicht als Test formuliert
werden kann, gilt nicht als erledigt, sondern als offen und geht an den
Auftraggeber zurück [PERMALINK: docs/00_Projektauftrag.md#abschnitt-3.4].
Einzige ausdrückliche Ausnahme ist der interaktive Prototyp, dessen
Freigabe ein menschliches Gate ist, weil sich Bedienführung nicht messen
lässt [PERMALINK: docs/00_Projektauftrag.md#abschnitt-5.6].

Der Zusammenhang der beiden: Ready verlangt ein testbar formuliertes
Abnahmekriterium, Done führt genau diese Tests aus. Ein Eintrag ohne
testbares Abnahmekriterium erfüllt die Definition of Ready nicht.

## Sprintumfang nach Prüfkapazität, nicht nach Erzeugungskapazität

Die Kapazität ist geklärt: 7 bis 10 Stunden pro Woche und Person, also 14
bis 20 Stunden im Team und **28 bis 40 Personenstunden je Sprint** von
zwei Wochen. Diese Stunden sind nicht Entwicklungszeit, sondern Review-,
Freigabe- und Feinschliffzeit, denn die Umsetzung übernimmt Claude Code
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8].

Daraus folgt die Planungsregel, die dem üblichen Vorgehen widerspricht:

> **Der Sprintumfang bemisst sich an der Prüfkapazität, nicht an der
> Erzeugungskapazität.**

Claude Code kann in einem Sprint mehr produzieren, als in 28 bis 40
Stunden sorgfältig geprüft werden kann. Würde der Sprint an dem bemessen,
was erzeugbar ist, entstünde ein wachsender Bestand ungeprüfter
Inkremente — bei einem Werkzeug mit Nachweispflicht die gefährlichste Form
von Fortschritt. Der Product Owner nimmt deshalb nur so viel in den
Sprint, wie das Team prüfen kann.

**Praktische Faustregel:** Vor der Aufnahme eines Backlog-Eintrags wird
der geschätzte **Prüfaufwand** notiert, nicht der Umsetzungsaufwand. Die
Summe darf 28 bis 40 Stunden nicht überschreiten. Die Schätzung ist
anfangs ungenau und wird über die Sprints kalibriert; die Retrospektive
ist der Ort dafür.

Aus demselben Grund weist die Roadmap keine Kalenderzahl aus, bevor das
Backlog geschätzt ist, und führt die menschlichen Review-Wartezeiten als
eigene Positionen, weil sie auf dem kritischen Pfad liegen
[PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8].

## Offene Punkte

- [OFFEN] Die Definition of Done als konkrete Befehlskette (welche
  Befehle, welche Schwellenwerte) ist noch nicht festgelegt; sie entsteht
  mit Schritt 3 der Lieferreihenfolge
  [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2].
- [OFFEN] Die personelle Besetzung von Product Owner und Scrum Master
  (Mensch oder Claude-Code-Rolle, und wer konkret) ist im Projektauftrag
  nicht ausgewiesen.
- [OFFEN] Der Start des ersten Sprints und damit der Sprintkalender sind
  nicht festgelegt.

## Platzhalter in diesem Dokument

Die Automatik ersetzt diese Platzhalter durch feste Verweise mit
vollständiger Commit-Prüfsumme:

- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.8]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.5]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-6.1]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.2]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-4.3]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-3.4]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-5.6]
- [PERMALINK: docs/00_Projektauftrag.md#abschnitt-2]
