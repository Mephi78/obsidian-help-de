---
aliases:
description: Mit der Standarderweiterung Importprogramm für Markdown Format kannst du Markdown aus anderen Anwendungen in das Obsidian Format konvertieren.
mobile: true
permalink: plugins/markdown-import
publish: true
---

Mit der [[Übersicht|Standarderweiterung]] *Importprogramm für Markdown Format* kannst du Markdown aus anderen Anwendungen in das Obsidian Format konvertieren. Zudem kannst du damit bestimmte [[Eigenschaften]] in erforderliche neue Formate umwandeln.

> [!warning] Achtung
> Das Importprogramm konvertiert deinen gesamten Vault basierend auf deinen Einstellungen. [[Sichere deinen Vault|Sichere deinen Vault]], bevor du die Konvertierung startest.

Um alle Notizen in deinem Vault zu konvertieren:

1. Wähle den Befehl **Markdown Importprogramm öffnen** aus der [[Befehlspalette]]. Oder klicke in der [[Werkzeugleiste]] auf **Markdown Importprogramm öffnen** ( ![[lucide-binary.svg#icon]] ).
2. Aktiviere die Regeln, die bei der Konvertierung angewendet werden sollen.
3. Klicke **Konvertierung starten**.

Mehr Informationen findest du im Abschnitt [[Formatierungsgrundlagen]].

## Unterstützte Formate

### Roam Research

Das Importprogramm kann die folgende Roam Research Syntax konvertieren:

- **Tags**: Konvertiert `#tag` und `#[[tag]]` nach `[[tag]]`
- **Hervorhebungen**: Konvertiert `^^highlight^^` nach `==highlight==`
- **TODO-Elemente**: Konvertiert `{{[[TODO]]}}` nach `[ ]`

### Bear

Das Importprogramm kann die folgende Bear Syntax konvertieren:

- **Hervorhebungen**: Konvertiert `::highlight::` nach `==highlight==`

### Zettelkasten

Das Importprogramm kann die folgende Zettelkasten Syntax konvertieren:

- **Vollständige Links**: Konvertiert `[[UID]]` nach `[[UID File Name]]`
- **Verschönerte Links**: Konvertiert `[[UID]]` nach `[[UID File Name|File Name]]`

### [[Eigenschaften]]

Seit Obsidian `1.9.3` kann das Importprogramm [[Eigenschaften#Veraltete Eigenschaften|veraltete Eigenschaften]] in die erforderlichen neuen Formate konvertieren:

**Aliases**

```yaml
# Vorher

alias: Titel meiner Notiz

# Nachher

aliases:
  - Titel meiner Notiz
```

**Tags**

```yaml
# Vorher

tag: project, important

# Nachher

tags:
  - project
  - important
```

**CSS Classes**

```yaml
# Vorher

cssclass: mein-stil

# Nachher

cssclasses:
  - mein-stil
```

