---
permalink: web-clipper/marker
aliases:
  - Markierungen
  - Hervorhebungen
  - Highlighting
publish: true
---

Mit dem [[Einführung in Obsidian Web Clipper|Web Clipper]] kannst du Text auf Webseiten markieren und die Elemente auswählen, die du nach Obsidian speichern möchtest. Deine Markierungen werden gepeichert, so dass du sie Your highlights are saved, so you can revisit them when you return to a page.

Markierungen können [[Webseiten speichern|erfasst]] und nach Obsidian gespeichert werden.

## Marker aktivieren

Je nach Browser kannst du die Markierungsfunktion auf verschiedene Weise aktivieren:

- Über das Marker-Symbol im Erweiterungsdialog.
- Oder über Tastenkürzel, wenn du die Erweiterung mittels Tastatur aktivieren möchtest.
- Oder über ein Kontextmenü, das du mit Rechtsklick auf die Webseite öffnest, die du gerade besuchst.

Sobald du **Highlighting** aktiviert hast, kannst du Elemente, wie Text oder Bilder, in der Webseite markieren.

## Marker-Einstellungen

Du kannst das Highlighting-Verhalten über die Web Clipper-Einstellungen im Abschnitt **Marker** ändern. Dort kannst du auch deine Markierungen in eine `.json`-Datei exportieren.

Es gibt drei Möglichkeiten, wie Web Clipper Markierungen beim Export nach Obsidian auf über die [[Variablen|Variable]] `{{content}}` hinzugefügte Inhalte anwendet:

- **Seiteninhalt markieren**: fügt Markierungen direkt in den Text ein mittels [[Obsidian Flavored Markdown|Markdown Syntax]] `==markieren==`.
- **Seiteninhalt ersetzen**: erstellt eine Liste aus dem markierten Inhalt ohne den Rest des Seiteninhalts.
- **Nichts tun**:  ignoriert die Markierungen und verwendet den Seiteninhalt ohne Highlighting.

Du kannst Markierungen direkt in die Notiz einfügen, indem du in deiner [[Obsidian Web Clipper/Vorlagen|Vorlage]] die Variable `{{highlights}}` verwendest, wie im Beispiel unten.

```
{{highlights|map: item => item.text|join:"\n\n"}}
```
