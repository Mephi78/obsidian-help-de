---
permalink: obsidian-markdown
publish: true
---

Obsidian strebt nach größtmöglicher Leistungsfähigkeit, ohne mit bestehenden Formaten zu brechen. Daher verwenden wir eine Kombination aus verschiedenen [[Formatierungsgrundlagen|Markdown]]-Varianten.

Obsidian unterstützt [CommonMark](https://commonmark.org/), [GitHub Flavored Markdown](https://github.github.com/gfm/) und [LaTeX](https://www.latex-project.org/). Obsidian unterstützt keine Markdown-Formatierung oder Leerzeilen innerhalb von HTML-Tags.

### Unterstützte Markdown-Erweiterungen

| Syntax                                                   | Beschreibung                                                   |
| -------------------------------------------------------- | -------------------------------------------------------------- |
| `[[Link]]`                                               | [[Interne Links\|Interner Link]]                              |
| `![[Link]]`                                              | [[Dateien einbetten\|Eingebettete Datei]]                            |
| `![[Link#^id]]`                                          | [[Interne Links#Block in einer Notiz verlinken\|Block-Referenz]]   |
| `^id`                                                    | [[Interne Links#Block in einer Notiz verlinken\|Block-Definition]] |
| `[^id]`                                                  | [[Formatierungsgrundlagen#Fußnoten\|Fußnote]]                  |
| `%%Text%%`                                               | [[Formatierungsgrundlagen#Kommentare\|Kommentar]]              |
| `~~Text~~`                                               | [[Formatierungsgrundlagen#Betonungen\|Streichung]]             |
| `==Text==`                                               | [[Formatierungsgrundlagen#Betonungen\|Hervorhebung]]           |
| `` ``` ``                                                | [[Formatierungsgrundlagen#Quelltext-Blöcke\|Quelltext-Block]]  |
| `- [ ]`                                                  | [[Formatierungsgrundlagen#Aufgabenlisten\|Offene Aufgabe]]     |
| `- [x]`                                                  | [[Formatierungsgrundlagen#Aufgabenlisten\|Erledigte Aufgabe]]  |
| `> [!note]`                                              | [[Callouts\|Callout]]                                          |
| \| Spalte1  \| Spalte2  \|<br>\|----------\|----------\| | [[Erweiterte Formatierung#Tabellen\|Tabelle]]                  |
