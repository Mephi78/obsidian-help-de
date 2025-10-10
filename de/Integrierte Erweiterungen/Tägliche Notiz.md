---
permalink: plugins/taegliche-notizen
---

Die [[Standarderweiterungen|Standarderweiterung]] *Tägliche Notizen* erstellt oder öffnet eine Notiz basierend auf dem aktuellen Datum. Verwende tägliche Notizen, um ein Journal, ein Tagebuch oder Aufgabenlisten zu erstellen.

Um die heutige Notiz zu öffnen:

- Klicke **Heutige Notiz öffnen** ( ![[lucide-calendar.svg#icon]] ) in der [[Werkzeugleiste]].
- Oder wähle den Befehl **Heutige Notiz öffnen** aus der [[Befehlspalette]].
- Oder verwende ein [[Tastenkürzel#Tastenkürzel zuweisen|Tastenkürzel]] für den Befehl **Heutige Notiz öffnen**.

Standardmäßig wird eine neue leere Notiz erzeugt und nach dem heutigen Datum im Format `YYYY-MM-DD` benannt.

> [!tip] Wenn du deine täglichen Notizen lieber in einem separaten Ordner speichern möchtest, kannst du in den Erweiterungseinstellungen den **Speicherort für neue Tagesnotizen** konfigurieren.

> [!example]- Automatische Unterordner
> Über die Erweiterungseinstellung **Datumsformat** kannst du deine täglichen Notizen automatisch in Unterordner einsortieren.
> 
> Setze bspw. das Datumsformat `YYYY/MMMM/YYYY-MMM-DD`, damit deine Notizen in der Form `2023/Januar/2023-Jan-01` erstellt werden.
> 
> Erfahre mehr über mögliche Datumsformate in der [momentJS](https://momentjs.com/docs/#/displaying/format/) Dokumentation.

## Tägliche Notiz aus Vorlage erstellen

Wenn deine täglichen Notizen immer denselben Aufbau haben, kannst du eine [[Vorlagen|Vorlage]] verwenden, um bei der Erstellung die neue Tagesnotiz mit bestimmten Inhalten vorzubefüllen.

1. Erstelle dafür eine neue Notiz, z.B. "Tägliche Vorlage" mit dem folgenden Text (oder was immer dir sinnvoll erscheint):

   ```md
   # {{date:YYYY-MM-DD}}

   ## Aufgaben

   - [ ]
   ```

2. Öffne die **Einstellungen**.
3. Wähle unter Obsidian-Erweiterungen **Tägliche Notizen**.
4. Klicke in das Textfeld neben **Speicherort der Vorlagendatei** und wähle die soeben erstellte Notiz "Tägliche Vorlage" aus.

Wenn du deine nächste tägliche Notiz erstellst, wird Obsidian diese Vorlage verwenden.

## Tägliche Notizen und Eigenschaften

Wenn die Erweiterung *Tägliche Notizen* aktiviert ist und eine Notiz eine [[Eigenschaften|Eigenschaft]] vom Typ **Datum** enthält, wird Obsidian automatisch einen Link zur entsprechenden Tagesnotiz generieren.

Hast du bspw. in einer Notiz `beispiel.md` eine beliebige Eigenschaft vom Typ **Datum** auf `2023-01-01` gesetzt, wird dieses Datum in der [[Ansichten und Modi#Live-Vorschau|Live-Vorschau]] und in den [[Eigenschaften-Ansicht|Dateieigenschaften der aktiven Notiz]] als interaktiver Link dargestellt.

![[daily-notes-and-date-properties.png#interface|300]]
^daily-notes-date
