# Versionierung und Nachweisfluss

Grundlage: Verfolgbarkeit nach dem Projektauftrag,
[Abschnitt 6.6](https://github.com/valITino/r3cosint/blob/3f939cea7749d9fbe1df9a7bbc90ff94efe95cb6/docs/00_Projektauftrag.md).
Diese Regel gilt für alle Commits, die von Arbeitsabläufen unter
`.github/workflows/` erzeugt werden — hier wie im Produkt-Repository. Sie ist
am 2026-08-25 an die gleichnamige Regel des Produkt-Repositories angeglichen
worden (Einheit E5 des freigegebenen Plans): zwei gleichnamige Regeln sagten
zur Commit-Identität Verschiedenes.

## Identität automatisch erzeugter Commits

Massgeblich ist allein die E-Mail-Adresse. Jeder automatisch erzeugte Commit
trägt als `user.email`:

```
41898282+github-actions[bot]@users.noreply.github.com
```

Die numerische Kennung 41898282 ist die feste Konto-ID des Actions-Bots.
GitHub ordnet Commits über die E-Mail-Adresse einem Konto zu; nur diese Form
verlinkt den Commit auf das Konto des Actions-Bots selbst.

Der `user.name` ist dagegen reine Anzeige und darf der sprechende Name des
jeweiligen Arbeitsablaufs sein (im Produkt-Repository `r3cosint-nachweise[bot]`
und `r3cosint-meilenstein[bot]`; `eingang.yml` hier verwendet
`github-actions[bot]`). Die frühere Fassung dieser Regel verlangte auch für
den Namen `github-actions[bot]` und widersprach damit der Regel des
Produkt-Repositories; sachlich trägt dessen Fassung, weil der Name an der
Kontozuordnung nichts ändert.

## Weshalb eine generische noreply-Adresse unzulässig ist

Die Adresse "noreply@users.noreply.github.com" ist keine neutrale
Absenderangabe. GitHub liest den Teil vor dem "@" als Benutzernamen — hier
"noreply" — und verlinkt den Commit auf das Profil des GitHub-Kontos
"noreply", also auf eine unbeteiligte dritte Person. Ein Nachweis, dessen
Autorenverweis auf Unbeteiligte zeigt, ist als Nachweis untauglich und
verletzt die Verfolgbarkeit nach Abschnitt 6.6.

## Bestand und Geltung

- Zwei Commits in diesem Repository tragen die falsche Identität
  "r3cosint-nachweise[bot]" mit der Adresse
  "noreply@users.noreply.github.com":
  [`a3e149ee490e`](https://github.com/valITino/r3coscrum/commit/a3e149ee490e927998d46c800121703880505365)
  und
  [`5783d0930b63`](https://github.com/valITino/r3coscrum/commit/5783d0930b63152e662eccc23c74b1df3683c201).
  Der zweite entstand nach Erlass der Regel, weil der erzeugende Arbeitsablauf
  im Produkt-Repository erst später korrigiert wurde. Beide bleiben
  unangetastet: Historie wird nicht umgeschrieben. Die Regel gilt für künftige
  Commits.
- `.github/workflows/eingang.yml` in diesem Repository setzt die korrekte
  Identität (geprüft am 2026-08-21).
- Die Arbeitsabläufe im Produkt-Repository (nachweise-uebertragen.yml,
  meilenstein-tag.yml) setzen die korrekte Adresse seit dem 2026-08-25, Commit
  [`47dd3086f1d6`](https://github.com/valITino/r3cosint/commit/47dd3086f1d69820ab66a7eae317e1dd0c07e451).
  Der früher hier vermerkte offene Prüf- und Korrekturbedarf ist damit
  erledigt.
