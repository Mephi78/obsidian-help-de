---
aliases:
  - Alias
  - Gewusst wie/Aliasse für eine Notiz definieren
permalink: aliasse
cssclasses:
  - soft-embed
---

Wenn du eine Notiz unter verschiedenen Namen referenzieren möchtest, kannst du *Aliasse* hinzufügen. Ein Alias ist ein alternativer Name für eine Notiz.

Verwende Aliasse für Akronyme, Abkürzungen oder um in einer anderen Sprache auf eine Notiz zu verweisen.

Wenn du die Darstellung eines Links nur an einer Stelle ändern möchtest, kannst du stattdessen den [[Interne Links#Anzeigetext für einen Link ändern|Anzeigetext anpassen]].

![[Interne Links#^callout-internal-links-link-text]]

## Alias zu einer Notiz hinzufügen

Um einen Alias für eine Notiz zu definieren, füge die [[Eigenschaften|Eigenschaft]] `aliases` hinzu. Aliasse sollten im YAML-Block immer als Liste formatiert sein.

```md
---
aliases:
  - Verknüpfung
  - Verweis
  - Referenz
---

# Link
```

## Notiz über einen Alias verlinken

Um eine Notiz mit Hilfe eines Alias zu verlinken, beginne, den Alias in einem [[Interne Links|internen Link]] einzutippen. Ein Alias wird in der Autovervollständigen-Liste angezeigt mit einem gekrümmten Pfeil daneben.

Obsidian erstellt den Link mit dem ausgewählten Alias als Anzeigetext, bspw. `[[Künstliche Intelligenz|KI]]`.

> [!note] Hinweis
> Anstatt nur den Alias als Link-Ziel anzugeben (`[[KI]]`), erstellt Obsidian den Link im Format `[[Künstliche Intelligenz|KI]]`, um Interoperabilität mit anderen Anwendungen zu gewährleisten, die Wiki-Links verwenden.

## Nicht verlinkte Erwähnungen für eine Notiz finden

Über die [[Rückverweise|Rückverweise]] kannst du nicht verlinkte Erwähnungen eines Notiztitels oder Alias finden.

Wenn du bspw. "KI" als Alias für "Künstliche Intelligenz" definiert hast, kannst du Erwähnungen von "KI" in anderen Notizen finden.

Wenn du mit dem Mauszeiger in der Rückverweise-Ansicht über eine nicht verlinkte Erwähnung fährst, erscheint ein interaktiver Tooltip **Verlinken**. Klickst du darauf, ersetzt Obsidian die Erwähnung durch einen [[Interne Links|internen Link]] mit dem erwähnten Alias als Anzeigetext.
