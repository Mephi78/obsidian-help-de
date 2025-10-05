---
aliases:
cssclasses:
  - soft-embed
description: Die Standarderweiterung Vorlagen ermöglicht dir, vordefinierte Textbausteine in deine aktive Notiz einzufügen.
mobile: true
permalink: plugins/vorlagen
publish: true
---

Die [[Übersicht|Standarderweiterung]] *Vorlagen* ermöglicht dir, vordefinierte Textbausteine in deine aktive Notiz einzufügen.

## Speicherort für Vorlagen konfigurieren

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Gib unter **Obsidian-Erweiterungen → Vorlagen** einen **Speicherort für Vorlagen** ein.

## Vorlage in aktive Notiz einfügen

**Hinweis:**  Um eine Vorlage einzufügen, musst du zunächst einen [[#Speicherort für Vorlagen konfigurieren]].

1. Wähle **Vorlage einfügen** aus der Werkzeugleiste.
2. Wähle die Vorlage aus, die du an der aktuellen Cursor-Position in die aktive Notiz einfügen möchtest.

## Vorlagen-Variablen

Mit *Vorlagen-Variablen* kannst du einer Vorlage dynamische Inhalte hinzufügen. Wenn du eine Vorlage verwendest, die Variablen enthält, ersetzt die Erweiterung diese durch die entsprechenden Werte.

| Variable    | Beschreibung                                      |
| ----------- | ------------------------------------------------- |
| `{{title}}` | Titel der aktiven Notiz.                          |
| `{{date}}`  | Heutiges Datum. **Standardformat:** `YYYY-MM-DD`. |
| `{{time}}`  | Aktuelle Uhrzeit. **Standardformat:** `HH:mm`.    |

Das Format für `{{date}}` und `{{time}}` kannst du mit *Format-Token* anpassen.

Um das Ausgabeformat zu ändern, ergänze die Variable um einen Doppelpunkt ( `:`) gefolgt von einer Zeichenfolge aus [Moment.js-Token](https://momentjs.com/docs/#/displaying/format/), z.B. `{{date:YYYY-MM-DD}}`.

Auf diese Weise lässt sich das Format sowohl für `{{date}}`, als auch `{{time}}` definieren, bspw. `{{time:YYYY-MM-DD}}`.

Zudem lässt sich das Standardformat für beide Variablen in den Erweiterungseinstellungen anpassen. Gib dazu die entsprechenden Format-Token unter **Einstellungen → Vorlagen → Datumsformat** bzw. **Zeitformat** ein.

> [!tip] Tipp
> Die Variablen `{{date}}` und `{{time}}` sind möglicherweise hilfreich für die Erstellung von Vorlagen für [[Tägliche Notiz]] oder die [[Eindeutige Notiz]].

## Vorlagen-Eigenschaften

![[Eigenschaften#^templates-properties]]
