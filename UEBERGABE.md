# Übergaben

Vermerke je Arbeitseinheit in diesem Repository, neueste zuoberst.

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
gebraucht; der GitHub-Zugang der Arbeitssitzung war auf `valITino/*`
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
