---
aliases:
  - Gestapelte Tabs
  - Verlinkte Ansicht
  - Fensterlayout
  - Benutzerschnittstelle/Registerkarten
permalink: registerkarten
---

Registerkarten (auch: Tabs) in Obsidian funktionieren ähnlich wie Registerkarten in anderen Anwendungen, wie z.B. Web-Browsern.

Du kannst in Obsidian beliebig viele Registerkarten öffnen. Zudem kannst du sie anordnen, um benutzerdefinierte Layouts zu erstellen, die über eine Sitzung hinaus bestehen bleiben.

## Neuen Tab öffnen

Klicke oben im Anwendungsfenster, rechts neben der letzten Registerkarte **Neuer Tab** ( ![[lucide-plus.svg#icon]] ) oder verwende das Tastenkürzel:

- **Windows und Linux:** `Strg + T`
- **macOS:** `Cmd + T`

## Link öffnen

Klicke einen Link in Obsidian, um ihn im aktiven Tab  zu öffnen.

Um einen Link in einem neuen Tab zu öffnen, drücke `Strg` (oder `Cmd` unter macOS), während du den Link anklickst.

Hier sind alle Tasten, die du drücken kannst, um Links auf verschiedene Weise zu öffnen:

| Aktion              | macOS                                       | Windows/Linux                                  |
| ------------------- | ------------------------------------------- | ---------------------------------------------- |
| **Navigieren**      | *Ohne*                                      | *Ohne*                                         |
| **Neuer Tab**       | `⌘` (+ `Umschalt` in der Quellcode-Ansicht) | `Ctrl` (+ `Umschalt` in der Quellcode-Ansicht) |
| **Neue Tab-Gruppe** | `⌘` `⌥`                                     | `Strg` `Alt`                                   |
| **Neues Fenster**   | `⌘` `⌥` `Umschalt`                          | `Strg` `Alt` `Umschalt`                        |

## Tabs und Fenster verwalten

Jede Registerkarte gehört zu einer *Tab-Gruppe*. Per Drag & Drop kannst du Tabs innerhalb einer Tab-Gruppe neu anordnen, in eine andere Tab-Gruppe verschieben oder eine neue Tab-Gruppe erstellen. Auf dem ![[lucide-monitor-check.svg#icon]] Desktop kannst du Registerkarten aus dem Fenster heraus ziehen, um sie in einem [[Pop-out Fenster|separaten Fenster]] zu öffnen.

Tabs in den Seitenleisten werden nur als Symbol dargestellt. Fahre mit der Maus darüber, um einen Tooltip mit dem Tab-Titel anzuzeigen.

### Tabs anordnen

Um die Reihenfolge von Registerkarten in einer Gruppe zu ändern, verschiebe sie per Drag & Drop innerhalb der Gruppe.

Wenn du einen Tab ziehst, werden *Ablagebereiche* hervorgehoben, auf die du den Tab verschieben kannst. Manche Registerkarten lassen sich nur in einer der Seitenleisten ablegen.

### Tab-Gruppen aufteilen

Öffne mit Rechtsklick auf eine Registerkarte das Kontextmenü und wähle **Rechts teilen** oder **Unten teilen**, um diesen Tab in einer neuen Tab-Gruppe rechts oder unterhalb der aktuellen zu öffnen.

Du kannst Tab-Gruppen auch auch teilen, indem du eine Registerkarte an den oberen, unteren, rechten oder linken Rand einer bestehenden Tab-Gruppe ziehst.

### Größe einer Tab-Gruppe ändern

Um die Größe einer Registerkartengruppe zu ändern, bewege die Maus über den Rand einer Gruppe. Der Mauszeiger ändert sich und der Rand wird hervorgehoben, sobald er sich ziehen lässt, um die Größe zu ändern.

Die Größe der Seitenleisten lässt sich auf ähnliche Weise ändern, um mehr Platz zu schaffen für den Hauptbereich in der Mitte.

### Tab in ein neues Fenster verschieben

**Drag & Drop:**

- Ziehe eine Registerkarte aus dem Anwendungsfenster heraus, um sie in ein neues Fenster zu verschieben.

**Befehlspalette:**

- Öffne die [[Command palette|Befehlspalette]] und wähle **Aktiven Tab in neues Fenster verschieben**.

### Tab in ein bestehendes Fenster verschieben

Um eine Registerkarte in ein anderes, bestehendes Fenster zu verschieben, ziehe sie per Drag & Drop auf das Fenster, in das du sie verschieben möchtest.

### Tabs anheften

Um eine Registerkarte anzuheften, öffne mit Rechtsklick auf den Tab das Kontextmenü und wähle **Anheften**. Wenn du einen Link in einer angehefteten Registerkarte anklickst, öffnet sich dieser immer in einem separaten Tab.

Möchtest du einen Tab nicht mehr anheften, öffne mit Rechtsklick auf denselben das Kontextmenü und wähle **Anheftung aufheben**.

## In einen anderen Tab wechseln

Klicke auf eine Registerkarte, um in diese zu wechseln oder verwende eine der folgenden Tastenkombinationen:

| Wechseln auf...               | MacOS        | Windows/Linux           |
| ----------------------------- | ------------ | ----------------------- |
| **nächsten Tab**              | `⌃`+`⇥`      | `Strg`+`Tab`            |
| **vorherigen Tab**            | `⌃`+`⇧`+`⇥`  | `Strg`+`Umschalt`+`Tab` |
| **ersten Tab von links**      | `⌘`+`1`      | `Strg`+`1`              |
| **zweiten bis achten Tab**    | `⌘`+`2`..`8` | `Strg`+`2`..`8`         |
| **letzten Tab**               | `⌘`+`9`      | `Strg`+`9`              |
| **zuletzt geschlossenen Tab** | `⌘`+`⇧`+`T`  | `Strg`+`Umschalt`+`T`   |

## Tab-Gruppen stapeln

Du kannst Registerkarten stapeln, um sie innerhalb einer Gruppe übereinander zu schieben.

Um Notizen zu stapeln, klicke auf den kleinen Pfeil nach unten in der rechten oberen Ecke einer Tab-Gruppe und wähle **Tabs stapeln**.

![tab-stacks](https://user-images.githubusercontent.com/693981/188205363-0f24b2a5-3706-4a8c-b38b-7a66baa68ce6.gif)

Die gestapelten Tabs wurden inspiriert von [Andy Matuschaks Sliding Notes](https://notes.andymatuschak.org/).

## Verlinkte Ansichten

*Verlinkte Ansichten* sind Registerkarten, die mit anderen in Verbindung stehen. Wenn sich der Inhalt einer referenzierten Registerkarte ändert, ändert sich auch die verlinkte Ansicht.

Beispiele verlinkter Ansichten für Notizen:

- [[Graph-Ansicht|Graph-Ansicht]] (lokal)
- [[Backlinks|Rückverweise]]
- [[Outline|Gliederung]]

Um eine verlinkte Ansicht für die aktive Notiz zu öffnen:

1. Öffne das **Drei-Punkte-Menü** ( ![[lucide-ellipsis-vertical.svg#icon]] ) rechts oben in der Notiz.
2. Unter **Verlinkte Ansicht öffnen** wähle die Ansicht, die du öffnen möchtest.

## Layouts speichern

Mit der [[Workspace]]-Erweiterung kannst du Fenster-Layouts speichern und wiederherstellen.
