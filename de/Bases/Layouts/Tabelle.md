---
permalink: bases/sichten/tabelle
publish: true
---

Die Tabellen-Sicht zeigt eine [[Einführung in Bases|Base]] als Tabelle an mit einer Zeile für jede Datei und Spalten für die [[Eigenschaften]].

![Beispiel einer Base-Tabellensicht auf eine Reihe von Büchern](bases-noshadow.png#interface)

## Einstellungen

Die Tabellen-Sicht kann in den [[Sichten#Sicht-Einstellungen|Sicht-Einstellungen]] konfiguriert werden.

### Zeilenhöhe

Du kannst die Zeilenhöhe anpassen, um mehr Informationen anzuzeigen. Wähle zwischen **short**, **medium**, **tall** und **extra tall**.

## Zusammenfassungen

Du kannst einer Tabellenspalte Zusammenfassungen hinzufügen, um schnell Summen, Durchschnittswerte, eine Anzahl oder dergleichen für die in einer Sicht angezeigten Zeilen zu berechnen.

Zusammenfassungen sind an die Sicht gebunden, nicht an die Base. Jede Sicht kann unterschiedliche Zusammenfassungen für dieselbe Spalte anzeigen.

### Eine Zusammenfassung hinzufügen

1. Öffne mit Rechtsklick auf den Spaltenkopf in einer Tabellensicht das Kontextmenü.
2. Wähle ![[lucide-calculator.svg#icon]] **Zusammenfassen…**.
3. Wähle eine der vorbelegten Zusammenfassungsfunktionen oder **Zusammenfassung hinzufügen**, um deine eigene zu definieren.

Die Zusammenfassung wird am unteren Rand der Spalte angezeigt. Wenn Ergebnisse [[Sichten#Ergebnisse sortieren und gruppieren|gruppiert]] sind, wird die Zusammenfassung für jede Gruppierung obehalb derselben angezeigt.

Sobald die Zusammenfassungsleiste hinzugefügt wurde, kannst du weitere Zusammenfassungen für andere Spalten hinzufügen, indem du auf die Zusammenfassung klickst. Wurden alle Zusammenfassungen entfernt, wird die Leiste automatisch versteckt.

### Vorbelegte Zusammenfassungen

Folgende Zusammenfassungen sind standardmäßig verfügbar. Die Optionen können je nach Eigenschaftstyp variieren.

#### Alle Eigenschaftstypen

- **Empty**: Anzahl der Zeilen ohne Wert.
- **Filled**: Anzahl der Zeilen mit Wert.
- **Unique**: Anzahl eindeutiger Werte.

#### Zahlen

- **Average**: Durchschnitt aller numerischen Werte.
- **Max**: Größter Wert.
- **Median**: Mittelwert.
- **Min**: Kleinster Wert.
- **Range**: Differenz zwischen größtem und kleinstem Wert.
- **Stddev**: Standardabweichung.
- **Sum**: Summe aller Werte.

#### Daten

- **Earliest**: Das kleinste/älteste Datum.
- **Latest**: Das größte/neueste Datum.
- **Range**: Differenz zwischen ältestem und neuestem Datum.

#### Checkboxen

- **Checked**: Anzahl der aktivierten Checkboxen.
- **Unchecked**: Anzahl der nicht aktivierten Checkboxen.

### Benutzerdefinierte Zusammenfassungen

Du kannst deine eigenen Zusammenfassungen mittels einer Formel definieren:

1. Im Menü **Zusammenfassen…** wähle ![[lucide-square-function.svg#icon]] **Zusammenfassung hinzufügen**.
2. Gib der Zusammenfassung einen Namen.
3. Gib eine Formel ein. Die Formel arbeitet die Liste der Werte in dieser Spalte ab (bspw. unter Verwendung einer [[Funktionen|Funktion]] wie `values.reduce(...)`).
4. Speichere die Zusammenfassung.

Benutzerdefinierte Zusammenfassungen sind hilfreich, wenn du eine Berechnung benötigst, die in den vorbelegten Zusammenfassungen nicht enthalten ist.

## Tastenkürzel

Halte die `Umschalt`-Taste gedrückt, während du eine Zelle anklickst, um sie auszuwählen. Öffne ein Kontextmenü für die Dateien mit Rechtsklick auf die Zellenauswahl.

| Tastenkürzel                        | Beschreibung                                                                                                  |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `Strg/Cmd-C`                        | Ausgewählte Zelle kopieren.                                                                                   |
| `Strg/Cmd-V`                        | Ausgewählten Zellen einfügen.                                                                                 |
| `Strg/Cmd-Z`, `Strg/Cmd-Umschalt-Z` | Rückgängig/Wiederholen der Änderungen beim Editieren.                                                         |
| `Strg/Cmd-A`                        | Alle Zellen der aktuellen Gruppe auswählen.                                                                   |
| `Strg/Cmd-Umschalt-Pfeiltaste`      | Alle Zellen in der jeweiligen Richtung auswählen.                                                             |
| `Ctrl-Leertaste`                    | Spalte auswählen.                                                                                             |
| `Umschalt-Leertaste`                | Zeile auswählen.                                                                                              |
| `Eingabetaste`                      | Kontextabhängig: Aktuelle Zelle fokussieren. Oder Checkbox aktivieren/deaktivieren. Oder Formeleditor öffnen. |
| `Pos1`                              | Zur ersten Spalte navigieren.                                                                                 |
| `Ende`                              | Zur letzten Spalte navigieren.                                                                                |
| `Bild hoch/runter`                  | Zur nächsten, vorhergehenden Seite navigieren.                                                                |
| `Escape`                            | Auswahl aufheben.                                                                                             |
| `Rücktaste`                         | Zelle löschen.                                                                                                |
| `Tab`                               | Zur nächsten Zelle navigieren.                                                                                |
| `Umschalt-Tab`                      | Zur vorhergehenden Zelle navigieren.                                                                          |
