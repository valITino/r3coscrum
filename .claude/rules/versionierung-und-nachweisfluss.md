# Versionierung und Nachweisfluss

Grundlage: Verfolgbarkeit nach dem Projektauftrag,
[Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md).
Diese Regel gilt für alle Commits, die von Arbeitsabläufen unter
`.github/workflows/` erzeugt werden — hier wie im Produkt-Repository.

## Identität automatisch erzeugter Commits

Automatisch erzeugte Commits tragen als Autor und als Committer die
offizielle Identität des GitHub-Actions-Bots:

```
git config user.name  "github-actions[bot]"
git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
```

Die numerische Kennung 41898282 ist die feste Konto-ID des Actions-Bots.
GitHub ordnet Commits über die E-Mail-Adresse einem Konto zu; nur diese
Form verlinkt den Commit auf das Konto des Actions-Bots selbst.

## Weshalb eine generische noreply-Adresse unzulässig ist

Die Adresse "noreply@users.noreply.github.com" ist keine neutrale
Absenderangabe. GitHub liest den Teil vor dem "@" als Benutzernamen — hier
"noreply" — und verlinkt den Commit auf das Profil des GitHub-Kontos
"noreply", also auf eine unbeteiligte dritte Person. Ein Nachweis, dessen
Autorenverweis auf Unbeteiligte zeigt, ist als Nachweis untauglich und
verletzt die Verfolgbarkeit nach Abschnitt 6.6.

Der angezeigte Name (`user.name`) ändert an der Zuordnung nichts;
massgeblich ist allein die E-Mail-Adresse.

## Bestand und Geltung

- Der Commit
  [`a3e149ee490e`](https://github.com/valITino/r3coscrum/commit/a3e149ee490e927998d46c800121703880505365)
  in diesem Repository trägt die falsche Identität "r3cosint-nachweise[bot]"
  mit der Adresse "noreply@users.noreply.github.com". Er bleibt unangetastet:
  Historie wird nicht umgeschrieben. Die Regel gilt für künftige Commits.
- `.github/workflows/eingang.yml` in diesem Repository setzt die korrekte
  Identität bereits (geprüft am 2026-08-21).
- Die Arbeitsabläufe im Produkt-Repository (nachweise-uebertragen.yml,
  meilenstein-tag.yml) liegen ausserhalb dieses Repositories; der offene
  Prüf- und Korrekturbedarf dort ist in `UEBERGABE.md` vermerkt.
