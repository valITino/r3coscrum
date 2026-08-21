# Übergabe: Identität automatisch erzeugter Commits

Vermerk aus der Arbeitseinheit vom 2026-08-21 (Zweig
"claude/github-actions-author-identity-4p94j0"). Die zugehörige Regel steht
in `.claude/rules/versionierung-und-nachweisfluss.md`.

## Hinweis zur Verortung

Die Aufgabenstellung verortete "nachweise-uebertragen.yml" in diesem
Repository und "eingang.yml" im jeweils anderen. Tatsächlich ist es
umgekehrt: "eingang.yml" liegt hier; "nachweise-uebertragen.yml" und
"meilenstein-tag.yml" liegen im Produkt-Repository valITino/r3cosint
(vgl. `nachweise/NACHWEISE.md`, Abschnitt "Übertragung nach Repo B").

## In diesem Repository erledigt

- `.github/workflows/eingang.yml` geprüft: Autor und Committer stehen dort
  bereits korrekt auf "github-actions[bot]" mit der Adresse
  "41898282+github-actions[bot]@users.noreply.github.com". Keine Änderung
  nötig.
- Regel zur Identität automatisch erzeugter Commits festgehalten in
  `.claude/rules/versionierung-und-nachweisfluss.md`.

## Offen im Produkt-Repository (nächste Einheit)

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

## Unangetastet

Der bestehende Commit
[`a3e149ee490e`](https://github.com/valITino/r3coscrum/commit/a3e149ee490e927998d46c800121703880505365)
behält seine falsche Identität: Historie wird nicht umgeschrieben
([Projektauftrag, Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md)).
