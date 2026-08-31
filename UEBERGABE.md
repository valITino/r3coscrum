# Übergaben

Vermerke je Arbeitseinheit in diesem Repository, neueste zuoberst.

---

## 2026-08-31 — Fremdes Skill-Repository ausgewertet, erste zwei Skills

Der Auftraggeber hat `valITino/claude-skills-fullstack` angebunden, mit der
Weisung, es genau anzusehen und zu uebernehmen, was Qualitaet und Rollenmodell
staerkt. Der Hauptteil liegt im Produkt-Repository
(`docs/uebergaben/2026-08-31_skill-repository-ausgewertet.md`); hier der
methodische Anteil.

### Erledigt

- **S6 und S7** als methodische Entscheide (siehe `methodik/entscheide.md`):
  fremdes Material wird nie woertlich uebernommen, und ein Skill entsteht nur,
  wenn mehrere Rollen dieselbe Prozedur gleich ausfuehren.
- **Neuer offener Punkt** zum Herkunftsvermerk bei fehlendem Rechteinhaber,
  vorzubereiten durch den Legal Reviewer, zu entscheiden durch den
  Auftraggeber.

### Was den Ausschlag gab

Der fremde Bestand fuehrt 67 Skills, darunter Rollen wie DevOps Engineer,
Code Reviewer und Security Reviewer — als Skills, nicht als Rollen. Genau
daran zeigt sich die Grenze, die S7 zieht: Ein Skill ist eine Prozedur, keine
handelnde Instanz. Waeren unsere Pruefrollen Skills, liesse sich weder
abbilden, dass der Pentester nicht schreiben darf, noch dass Pruefung und
Umsetzung auf verschiedenen Modellen laufen. Aus rund zwanzig beurteilten
Kandidaten sind deshalb genau zwei Skills entstanden.

Die Lizenzlage gab den Ausschlag fuer S6. Die Lizenz ist MIT, ihre
Urheberrechtszeile lautet aber "Copyright (c) 2025" ohne benannten
Rechteinhaber; dreizehn Dateien fuehren Inhalte aus einem dritten Projekt
weiter, eine davon ohne Lizenzangabe. Ein Vermerk, der niemanden nennt, ist
in einem Projekt mit Belegpflicht nicht belegtauglich.

### Eine Feststellung zur Beweisfuehrung

Die Auswertung ist von einer unabhaengigen Vollstaendigkeitskritik
gegengelesen worden; sie fand im Vorschlag sechzehn Luecken und sieben falsche
Belegstellen. Keine Angabe ist ungeprueft in ein Artefakt gelangt. Eine
Behauptung der Kritik hat die Nachpruefung selbst nicht ueberstanden und ist
deshalb nirgends uebernommen. Das ist der Grund, weshalb V10 ("eine Abgrenzung
ist keine Erlaubnis") einen Zwilling braucht, der hier nicht als Entscheid,
aber als Arbeitsweise festgehalten wird: **Eine Fundstelle, die niemand
nachgeschlagen hat, ist kein Beleg** — auch dann nicht, wenn sie von einer
Pruefinstanz stammt.

### Stand im Produkt-Repository

| Gegenstand | Commit |
|---|---|
| Erste zwei Skills, `skills:`-Feld bei neun Rollen, ADR 0001 berichtigt | [`080d4689c3e5`](https://github.com/valITino/r3cosint/commit/080d4689c3e5615d5e73bf034b62270f3f57d92e) |
| Einordnung der Uebernahmen ins Backlog | [`364b1b568a3c`](https://github.com/valITino/r3cosint/commit/364b1b568a3c74610ef0f324cd5e64f27ebdb815) |
| Notation der Abnahmekriterien in der Definition of Ready | [`90c9923cf43e`](https://github.com/valITino/r3cosint/commit/90c9923cf43ecb81dfe410375d10d956866d1c87) |

### Abbruch nach 3.4 -- die beiden Skills sind nicht abgenommen

Dieselbe Pruefung ist dreimal am selben Kriterium gescheitert: eine Aussage
ueber die Herkunft, die staerker ist als die Quelle sie traegt. Nach
Eskalationsregel 3.4 ist die Einheit insoweit abgebrochen und dem
Auftraggeber vorgelegt; Einzelheiten in der Uebergabe des
Produkt-Repositories.

**Das bestaetigt S2, und zwar am eigenen Leib.** S2 haelt fest: CLAUDE.md ist
Kontext, keine Durchsetzung -- wer eine Regel garantiert durchsetzen will,
braucht einen Hook. Der Skill `pruefbefund-melden` stellt die Regel auf, dass
jede Aussage ihre Herkunft traegt, und ist an genau dieser Regel dreimal
gescheitert. Eine Regel, die nur als Vorsatz existiert, wird von demselben
Text verletzt, der sie aufstellt. Das ist kein neuer Entscheid, sondern der
dritte Beleg fuer einen bestehenden -- und das Argument, das hinter R3-Q-001
steht.

### Offen

- Wer `.claude/skills/` beschreiben darf (ADR 0001 weist `.claude/` keiner
  Rolle zu).
- Ob die beiden Skills bis zu einer maschinellen Pruefregel in Kraft bleiben
  oder ruhen. Entscheidet der Auftraggeber.
- Ob das Vorladen eines Skills je Rolle in dieser Umgebung ueberhaupt wirkt.
  Ein Kontrollversuch war negativ; er widerlegt nichts, weil Aenderungen an
  Rollendateien in der laufenden Sitzung nicht wirken. Zu Beginn der naechsten
  Sitzung erneut zu pruefen.
- Die Rechtsfrage aus S6.

---

## 2026-08-31 — Definition-of-Done-Kette abgenommen, O-13 entschieden

Der Hauptteil dieser Arbeitseinheit liegt im Produkt-Repository (Uebergaben
`docs/uebergaben/2026-08-31_makefile-dod-drei-befunde-behoben.md`); hier der
methodische Anteil.

### Erledigt

- **Zwei neue methodische Entscheide** in `methodik/entscheide.md`:
  - **V9** — Steht eine Abwaegung zwischen Laufzeit oder Bequemlichkeit und
    Beweiskraft, entscheidet die Beweiskraft. Woertliche Weisung des
    Auftraggebers vom 2026-08-31. Erstmals angewandt auf O-13 des
    Architekturentscheids 0002: Die Kette benutzt den Zwischenspeicher des
    Paketwerkzeugs nicht mehr, weil dessen Inhalt nicht erneut gegen die
    Sperrdatei geprueft wird.
  - **V10** — Eine Abgrenzung ist keine Erlaubnis. Was sich schliessen laesst,
    wird geschlossen; abgegrenzt wird nur, was sich mit den Mitteln des
    jeweiligen Artefakts nicht schliessen laesst.

### Woher V10 kommt

Aus einem belegten Fehler im eigenen Vorgehen, nicht aus einer Ueberlegung.
Der Kopfabschnitt des Makefiles grenzte einen Angriffsweg ab -- "dagegen
schuetzt die Kette nicht" --, obwohl er mit einer einzigen Zeile zu schliessen
war. Damit war die Abgrenzung vom Ergebnis einer Pruefung zu ihrer Ausrede
geworden. Die unabhaengige Nachpruefung hat das benannt; der Auftraggeber hat
mit V9 entschieden; geschlossen wurde es am selben Tag.

Das ist der Grund, weshalb dieser Entscheid hier steht und nicht nur im
Architekturentscheid: Er betrifft nicht diese eine Kette, sondern jede
Stelle, an der eine Abgrenzung geschrieben wird.

### Stand im Produkt-Repository

| Gegenstand | Commit |
|---|---|
| Zwei blockierende Befunde behoben, Kette abgenommen | [`acda82dd39ea`](https://github.com/valITino/r3cosint/commit/acda82dd39ea1b26a67131225901ec0da02aece0) |
| O-13 umgesetzt (`UV_NO_CACHE=1`) | [`7d1fe2fdea8d`](https://github.com/valITino/r3cosint/commit/7d1fe2fdea8dc339a7890ece18e4859418cfd6f6) |
| Abgrenzungsabschnitt nachgefuehrt | [`2bc0255c83e7`](https://github.com/valITino/r3cosint/commit/2bc0255c83e7bbbd2664df759aceeebe747246e0) |

### Offen

- **O-12** — ein Lauf der Kette auf der Gegenseite, in einer Umgebung, die der
  Aufrufer nicht setzt. Solange er fehlt, ist die Kette die Selbstpruefung
  eines kooperierenden Aufrufers. Terminiert mit dem Grundgeruest, weil die
  Kette heute planmaessig rot endet (fehlende Pruefmittel, Lage C) und ein
  dauerhaft roter Pflichtlauf niemanden schuetzt, sondern nur ignoriert wird.
- **O-7, O-8, O-10, O-11** unveraendert offen.

---

## 2026-08-25 — Full-Review: Anteil dieses Repositories (zieht E5 vor)

Aus dem Full-Review über beide Repositories auf Weisung des Auftraggebers vom
2026-08-25. Der Hauptteil liegt im Produkt-Repository
(`docs/uebergaben/2026-08-25_full-review-konfiguration.md`); hier die sechs
Punkte dieses Repositories.

### Erledigt

- **E5 vorgezogen:** `.claude/rules/versionierung-und-nachweisfluss.md` an die
  gleichnamige Regel des Produkt-Repositories angeglichen. Massgeblich ist
  allein die E-Mail-Adresse
  `41898282+github-actions[bot]@users.noreply.github.com`; der `user.name`
  darf der sprechende Name des Arbeitsablaufs sein. Zwei gleichnamige Regeln
  sagten Verschiedenes; sachlich trug die Fassung des Produkt-Repositories.
  Im Bestand der zweite Commit mit falscher Identität nachgetragen
  (`5783d0930b63…`, entstanden nach Erlass der Regel, weil der erzeugende
  Arbeitsablauf im Produkt-Repository erst am 2026-08-25 korrigiert wurde);
  der dort früher vermerkte Korrekturbedarf ist als erledigt geführt
  (`47dd3086f1d6…`).
- **`eingang.yml`:** Die VERALTET-Erkennung las die Nachweisliste des
  Standardzweigs durch eine Pipe in `grep -qFx`. Unter dem gesetzten
  `pipefail` kann der SIGPIPE-Rückgabewert des abgebrochenen `sed` den
  Treffer überschreiben — ein bereits gemergter Sammelzweig würde dann
  fortgeschrieben, die Folge wäre ein Pull Request mit bereits gemergten
  Einträgen. Latent (erst bei grosser Nachweisliste auslösbar), aber exakt
  die Falle, die in beiden Arbeitsabläufen des Produkt-Repositories bereits
  behoben und kommentiert war. Die Liste geht jetzt in eine Datei unter
  `$RUNNER_TEMP`; es gibt keine Pipe mehr.
- **`methodik/arbeitsprodukte.md`** führte Stakeholderliste, Glossar,
  Kontextmodell und Product Backlog als "noch nicht angelegt", obwohl alle
  vier seit Schritt 3 existieren und das eigene Nachweisverzeichnis
  (`nachweise/NACHWEISE.md`) sie mit festen Verweisen führt. Auf "vorhanden"
  mit 40-stelligen Prüfsummen nachgeführt; die beiden überholten
  [OFFEN]-Punkte aufgelöst; die zwei PERMALINK-Platzhalter zur Prototyp-Demo
  durch den festen Verweis ersetzt (der Nachweis-Eintrag existiert seit dem
  2026-08-21).
- **`methodik/re-prozess.md`** behauptete, Schritt 3 sei "noch nicht
  begonnen"; er ist erledigt und seit dem 2026-08-20 freigegeben. Offen
  bleibt allein die Facettenbeurteilung als eigene belegte Analyse —
  präzisiert statt pauschal offen.
- **`methodik/scrum-aufbau.md`** führte die DoD-Befehlskette als "noch nicht
  festgelegt"; sie liegt als Vorschlag in ADR 0002 Abschnitt 6 vor. Offen
  bleiben Bestätigung der Befehle und Hook-Erzwingung (R3-Q-001).
- **`UEBERGABE.md`:** Guillemets durch gerade Anführungszeichen ersetzt
  — Verstoss gegen die Regel dieses Repositories, entstanden in der eigenen
  Einheit E2 vom 2026-08-25.

### Geprüft und bewusst NICHT geändert

`methodik/entscheide.md` vergibt für die Rollenmodell-Entscheide die Kennungen
R1 bis R5. Ich hatte zunächst eine Umbenennung erwogen, weil der Projektauftrag
4.4 die Rechtsregime R1 bis R5 nennt. Bei genauer Prüfung trägt der Befund
nicht: 4.4 "Zur Bezeichnung" reserviert ausdrücklich nur die Kürzel 1a, 1b, 2
(für die Klassifizierung) und hält fest, dass die Regime R1 bis R5 heissen — es
reserviert die Kürzel R1 bis R5 nicht exklusiv für Regime. Dieselben Kürzel
stehen zudem im Produkt-Repository in `docs/06_Definition_of_Ready_und_Done.md`
für die DoR-Qualitätskriterien (R1 adäquat, R2 notwendig, ...), von niemandem
beanstandet. R1 bis R5 sind hier tabellenlokale Entscheid-Kennungen, keine
Regime-Verweise, und werden in keinem der beiden Repositories referenziert. Eine
Umbenennung wäre eine Änderung ohne Regelgrundlage an einem Dokument mit
Entscheidcharakter — deshalb unterbleibt sie. Damit ist meine frühere Ansage,
auf RM1 bis RM5 umzubenennen, zurückgenommen.

### Nicht angetastet

`actions/checkout@v4` bleibt an beiden Stellen auf ein bewegliches
Versionsschild gepinnt; zum Pinnen fehlt weiterhin der Zugriff auf die
Prüfsumme (Sitzungszugang auf `valITino/*` beschränkt).
**Richtigstellung vom 2026-08-25:** Die Aussage war falsch. Öffentliche
Repositories sind über den Git-Proxy der Sitzung lesbar; beide Stellen in
`eingang.yml` sind seither auf `11d5960a326750d5838078e36cf38b85af677262`
(v4.4.0) gepinnt, und `.github/dependabot.yml` hält sie aktuell.

---

## 2026-08-25 — Eingangskanal an der Quelle abgesichert (Anteil dieses Repositories an E2)

Einheit E2 des freigegebenen Plans. Der Hauptteil liegt im Produkt-Repository
([`103edb45d7bf`](https://github.com/valITino/r3cosint/blob/103edb45d7bf467ba993fe9aadc6a8c7e2326112/docs/uebergaben/2026-08-25_eingangskanal-abgesichert.md));
hier liegt die Quelle des Kanals.

### Der Zusammenhang

`.github/workflows/eingang.yml` schreibt Commit-Nachrichten und Dateinamen aus
diesem Repository nach `docs/EINGANG_METHODIK.md` in Repo A. Von dort trägt ein
SessionStart-Hook sie in den Sitzungskontext eines Sprachmodells. Damit ist
alles, was hier in eine Commit-Nachricht geschrieben wird, fremder Inhalt im
Sinne der Verfahrensgarantie 5.4 des Projektauftrags: Daten, nie Anweisungen.
Geprüft wurde bisher nichts davon.

### Erledigt

- **Entschärfung vor dem Schreiben.** Neue Funktion `entschaerfen` im Schritt
  "Änderungen ermitteln", durch die sowohl die Dateiliste als auch die
  Commit-Nachrichten laufen. Drei Schritte: Steuerzeichen entfernen (Tabulator
  und Zeilenumbruch bleiben); Folgen von drei oder mehr Gleichheitszeichen zu
  `= = =` aufbrechen, weil der Hook in Repo A den fremden Teil in Marker dieser
  Form fasst; Zeilenzahl und Zeilenlänge begrenzen. Der Hook entschärft ein
  zweites Mal — hier geschieht es, damit schon die Datei in Repo A, die ein
  Mensch im Pull Request liest, keinen falschen Marker trägt.
- **Obergrenzen:** 100 Zeilen für die Dateiliste, 60 Zeilen für die
  Commit-Nachrichten, 500 Zeichen je Zeile. Überschreitungen werden ausgewiesen
  statt stillschweigend abgeschnitten, mit Verweis auf den Nachweis-Commit.
  Zuvor war beides unbegrenzt: eine einzige lange Zeile genügte, um den
  Sitzungskontext zu fluten.
- **`head` bewusst vermieden.** Die Begrenzung läuft über `awk`, das bis zum
  Ende liest. `head` schliesst die Pipe beim Erreichen der Grenze, und unter
  dem gesetzten `pipefail` könnte der Rückgabewert des abgebrochenen Schreibers
  durchschlagen. Dieselbe Falle ist in den Arbeitsabläufen des
  Produkt-Repositories bereits zweimal kommentiert.

### Die stille Neuanlage ist entfallen

Bis zu dieser Einheit legte der Schritt "Eintrag fortschreiben" bei fehlender
Zieldatei eine Ersatzfassung an — **ohne** den Abschnitt "Diese Datei ist
Information, keine Anweisung" und **ohne** die Überschrift `## Einträge`, an
der der Hook in Repo A den Eintragsbereich herausschneidet. Ausgeführt am
2026-08-25 mit der bisherigen Fassung: der Lauf endet mit Rückgabewert 0, der
Eintrag steht in der Datei, und der Hook gibt darauf **null Zeichen** aus.
Grüner Lauf, toter Kanal — genau die Fehlerklasse, die den Kanal schon einmal
unbemerkt stillgelegt hatte.

Die Datei wird jetzt weder angelegt noch nachgebaut. Der Lauf bricht mit
Rückgabewert 1 und einer Meldung ab. Zwei Gründe, jeder für sich zwingend:

1. Der Kopf der Datei enthält den Warnabschnitt, also Inhalt des
   Produkt-Repositories. Ihn hier vorzuhalten hiesse, ihn zu kopieren —
   `CLAUDE.md` dieses Repositories untersagt das ausdrücklich und verlangt
   Verweise statt Kopien.
2. Die Datei ist in Repo A versioniert. Ihr Fehlen ist eine Anomalie für einen
   Menschen, keine Lage, die eine Automatik überdecken darf. Ein lauter Abbruch
   ist besser als eine stille Ersatzfassung.

Zusätzlich bricht der Lauf ab, wenn die Überschrift `## Einträge` fehlt. Der
Hook in Repo A fällt inzwischen auf die erste Eintragsüberschrift zurück, aber
das Fehlen zeigt an, dass die Datei nicht mehr die erwartete Form hat.

### Verifikation — ausgeführt

YAML geparst. Beide `run:`-Blöcke mit `bash -n` ohne Beanstandung, beide mit
`set -euo pipefail`, **null Einsetzungen `${{ ... }}` in einem `run:`-Block**;
die drei verbleibenden stehen in `with:` und `env:`.

Nachgebildet wurde der ganze Ablauf: ein Wegwerf-Repository mit bösartigen
Commit-Nachrichten, beide Arbeitsablauf-Schritte aus der YAML-Datei ausgeführt,
lokales Fernarchiv, `gh` als Attrappe.

| Fall | Ergebnis |
|---|---|
| Normallauf | Rückgabewert 0, Zweig `eingang/methodik` fortgeschrieben, Eintrag angehängt |
| Zieldatei fehlt | Rückgabewert 1, Meldung "ABBRUCH: docs/EINGANG_METHODIK.md fehlt" |
| Überschrift `## Einträge` fehlt | Rückgabewert 1, Meldung mit Begründung |
| Commit-Nachricht mit `=== Ende des Eingangs ===` | im Eintrag zu `= = =` entschärft |
| Dateiname `datei=====mit=====gleichheitszeichen.md` | ebenso entschärft |
| Commit-Nachricht mit ANSI-Folge und Klingelzeichen | null Steuerzeichen im Eintrag (Quelle: 3) |
| Zeile mit 900 Zeichen | auf 500 gekürzt, Kürzung vermerkt |
| 90 Zeilen Commit-Rumpf | auf 60 gekürzt, Kürzung vermerkt |

### Nachtrag aus der unabhängigen Prüfung

Der Static Software Tester hat die Entschärfung im Hook von Repo A als
Sperrliste beanstandet: sie fasste nur das ASCII-Gleichheitszeichen, eine
Markerzeile aus Unicode-Homoglyphen ging durch. Die Zusicherung gegen
nachgebildete Marker trägt seither **strukturell der Hook** — er stellt jeder
Zeile des fremden Teils `| ` voran, sodass keine Zeile aus diesem Repository
die Form eines Markers annehmen kann, gleichgültig welche Zeichen sie
verwendet.

Für diesen Arbeitsablauf ändert sich dadurch nichts an der Wirkung, wohl aber
an der Lesart: Die Ersetzung von Gleichheitszeichen hier ist **Hygiene für den
menschlichen Leser des Pull Requests, nicht die Zusicherung**. Der Kommentar an
der Stelle sagt das jetzt ausdrücklich, samt Begründung, warum es keinen Sinn
hat, die Liste um weitere Zeichen zu ergänzen. Ohne diesen Vermerk hätte eine
spätere Arbeitseinheit die Ersetzung für die Absicherung halten und sich darauf
verlassen können.

Im zweiten Durchgang kam ein Befund hinzu, der auch diesen Arbeitsablauf
betrifft: Die Maske zum Entfernen von Steuerzeichen liess den Wagenrücklauf
(Byte 13) stehen, weil der Bereich aufgeteilt geschrieben war
(`\013\014\016-\037` statt `\013-\037`), während der Kommentar daneben
behauptete, nur Tabulator und Zeilenumbruch blieben. Gegen alle 256 Bytewerte
nachgeprüft und behoben; es bleiben jetzt genau Tabulator und Zeilenumbruch.

### Was hier offen bleibt

- `actions/checkout@v4` bleibt an beiden Stellen auf ein bewegliches
  Versionsschild gepinnt. Unverändert seit der letzten Einheit: zum Pinnen wird
  die Prüfsumme aus `actions/checkout` gebraucht, der GitHub-Zugang der Sitzung
  ist auf `valITino/*` beschränkt. **Richtigstellung vom 2026-08-25:** falsch,
  siehe oben; inzwischen gepinnt.
- `.claude/rules/versionierung-und-nachweisfluss.md` widerspricht weiterhin der
  gleichnamigen Regel im Produkt-Repository (sprechender Name je Arbeitsablauf).
  Das ist Einheit E5 und bleibt dort.

---

## 2026-08-25 — Automatik gehärtet (Anteil dieses Repositories an E1)

Aus dem Deep Review vom 2026-08-25 über beide Repositories. Der Hauptteil
der Einheit liegt im Produkt-Repository
([valITino/r3cosint#9](https://github.com/valITino/r3cosint/pull/9)); hier
liegen die zwei Punkte, die dieses Repository betreffen.

### Erledigt

- `.github/workflows/eingang.yml`: `persist-credentials: false` beim
  Auschecken dieses Repositories. Aus diesem Auscheckvorgang wird nur
  gelesen — geschrieben wird ausschliesslich im Produkt-Repository, das
  gleich darauf mit eigenem Token ausgecheckt wird. Ohne die Zeile bliebe
  das Token des Laufs in `.git/config` des Läufers stehen, während der Lauf
  danach fremde Commit-Nachrichten verarbeitet. Der zweite Auscheckvorgang
  bleibt unverändert: er braucht seine Zugangsdaten zum Schreiben.
- `.gitignore`: Zugangsdaten-Block ergänzt (`.env`, `.env.*`, `*.pem`,
  `*.key`, `*.p12`, `secrets/`), wie ihn `r3cosint/.gitignore` bereits
  führt. Bisher deckte die Datei nur Betriebssystem- und Editor-Artefakte
  ab, obwohl `CONTRIBUTING.md` ausdrücklich festhält, dass dieses
  Repository öffentlich ist. Der Block ist in beiden Repositories gleich,
  damit eine Datei nicht im einen geschützt ist und im anderen nicht.

### Befund, der hier offen bleibt

`.claude/rules/versionierung-und-nachweisfluss.md` verlangt in diesem
Repository `user.name "github-actions[bot]"` für automatisch erzeugte
Commits. Die gleichnamige Regel im Produkt-Repository erlaubt dagegen
ausdrücklich den sprechenden Namen je Arbeitsablauf
(`r3cosint-nachweise[bot]`, `r3cosint-meilenstein[bot]`) und begründet das
damit, dass GitHub die Zuordnung allein über die E-Mail-Adresse vornimmt —
was die Regel hier selbst einräumt. Zwei gleichnamige Regeldateien sagen
damit Verschiedenes. Sachlich trägt die Fassung des Produkt-Repositories;
diese hier ist anzugleichen. Das ist Einheit E5 des freigegebenen Plans und
gehört nicht in diese Einheit.

### Nicht angetastet

`actions/checkout@v4` bleibt an beiden Stellen auf ein bewegliches
Versionsschild gepinnt. Für ein Projekt, dessen Nachweisdoktrin auf
40-stelligen Prüfsummen statt beweglichen Verweisen beruht, ist das ein
Selbstwiderspruch. Zum Pinnen wird die Prüfsumme aus `actions/checkout`
gebraucht; der GitHub-Zugang der Arbeitssitzung war angeblich auf `valITino/*`
(diese Annahme war falsch, siehe Richtigstellung vom 2026-08-25)
beschränkt.

---

## 2026-08-21 — Identität automatisch erzeugter Commits

> **Stand 2026-08-25:** Die beiden unter "Offen im Produkt-Repository"
> aufgeführten Punkte sind erledigt — Commit
> [`47dd3086f1d6`](https://github.com/valITino/r3cosint/commit/47dd3086f1d69820ab66a7eae317e1dd0c07e451)
> im Produkt-Repository setzt in beiden Arbeitsabläufen die Adresse
> `41898282+github-actions[bot]@users.noreply.github.com`. Der Abschnitt
> bleibt als Vermerk der damaligen Einheit stehen; Historie wird nicht
> umgeschrieben.

Vermerk aus der Arbeitseinheit vom 2026-08-21 (Zweig
"claude/github-actions-author-identity-4p94j0"). Die zugehörige Regel steht
in `.claude/rules/versionierung-und-nachweisfluss.md`.

### Hinweis zur Verortung

Die Aufgabenstellung verortete "nachweise-uebertragen.yml" in diesem
Repository und "eingang.yml" im jeweils anderen. Tatsächlich ist es
umgekehrt: "eingang.yml" liegt hier; "nachweise-uebertragen.yml" und
"meilenstein-tag.yml" liegen im Produkt-Repository valITino/r3cosint
(vgl. `nachweise/NACHWEISE.md`, Abschnitt "Übertragung nach Repo B").

### In diesem Repository erledigt

- `.github/workflows/eingang.yml` geprüft: Autor und Committer stehen dort
  bereits korrekt auf "github-actions[bot]" mit der Adresse
  "41898282+github-actions[bot]@users.noreply.github.com". Keine Änderung
  nötig.
- Regel zur Identität automatisch erzeugter Commits festgehalten in
  `.claude/rules/versionierung-und-nachweisfluss.md`.

### Offen im Produkt-Repository (nächste Einheit)

1. `.github/workflows/nachweise-uebertragen.yml`: setzt die Autor-Identität
   der erzeugten Commits auf die generische Adresse
   "noreply@users.noreply.github.com". Beleg in diesem Repository: Commit
   [`a3e149ee490e`](https://github.com/valITino/r3coscrum/commit/a3e149ee490e927998d46c800121703880505365)
   trägt Autor und Committer "r3cosint-nachweise[bot]" mit ebendieser
   Adresse; GitHub verlinkt ihn dadurch auf das Profil des unbeteiligten
   Kontos "noreply". Zu setzen ist:

   ```
   git config user.name  "github-actions[bot]"
   git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
   ```

2. `.github/workflows/meilenstein-tag.yml`: auf dieselbe generische Adresse
   prüfen und gegebenenfalls gleich korrigieren.

### Unangetastet

Der bestehende Commit
[`a3e149ee490e`](https://github.com/valITino/r3coscrum/commit/a3e149ee490e927998d46c800121703880505365)
behält seine falsche Identität: Historie wird nicht umgeschrieben
([Projektauftrag, Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)).
