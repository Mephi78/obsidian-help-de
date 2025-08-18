---
aliases:
  - Fortgeschrittene Themen/Dateien löschen
  - Gewusst wie/Notizen umbenennen
description: Erfahre, wie du Dateien und Verzeichnisse in deinem Vault verwalten kannst.
mobile: false
permalink: notizen-verwalten
publish: true
---

Dateien und Verzeichnisse lassen sich auf verschiedene Arten verwalten, indem du [[Tastenkürzel|Tastenkürzel]], [[Command palette|Befehle]] oder den [[File explorer|Dateiexplorer]] verwendest.

## Neue Notiz erstellen

Um eine neue Datei zu erstellen:

1. Drücke `Strg+N` (oder `Cmd+N` unter macOS).
2. Gib einen Titel ein und bestätige mittels `Eingabetaste`, um mit der Bearbeitung der Notiz zu beginnen.

Du kannst neue Notizen auch über den [[File explorer#Create a new note|Dateiexplorer]] erstellen oder indem du **Neue Notiz erstellen** aus der [[Command palette|Befehlspalette]] wählst.

> [!hint] Systemabhängige Zeichenbegrenzung
> Obsidian beachtet die Dateinamenbeschränkungen des Betriebssystems, auf dem du die Notiz erstellst. Wenn du deine [[Synchronisiere Notizen zwischen Geräten|Notizen zwischen Geräten synchronisieren]] möchtest, stelle sicher, dass die Dateinamen auch [für andere Betriebssysteme geeignet](https://stackoverflow.com/q/1976007) sind.
^blockquote-system-limitation

## Notiz umbenennen

Um eine aktive Notiz umzubenennen:

1. Wähle den Titel der Notiz ganz oben im Editor aus (oder drücke `F2`).
2. Gibt den neuen Titel ein und bestätige mit der `Eingabetaste`.

Wenn du eine Datei umbenennst, aktualisiert Obsidian bei Bedarf alle Links, die auf diese Datei verweisen, automatisch.

Über den [[File explorer#Rename a file or folder|Dateiexplorer]] kannst du Dateien oder Ordner auch umbenennen, ohne diese zu öffnen.

## Notiz löschen

Um eine Notiz zu löschen, wähle **![[lucide-trash-2.svg#icon]] Datei löschen** über das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) oben rechts in der aktiven Notiz.

Oder wähle **Aktuelle Datei löschen** aus der [[Command palette|Befehlspalette]].

Du kannst Dateien oder Ordner auch über den [[File explorer#Delete a file or folder|Dateiexplorer]] löschen.

> [!question] Was passiert mit Dateien, nachdem ich sie gelöscht habe?
> Um festzulegen, was mit gelöschten Dateien geschehen soll, wähle eine der folgenden Optionen unter **Einstellungen → Dateien & Links**:
>
> - **In Papierkorb (System) verschieben**: Standardmäßig landen gelöschte Dateien im Papierkorb deines Betriebssystems. Um eine Datei wiederherzustellen, kannst du deinen bevorzugten Dateimanager verwenden.
> - **In Papierkorb (Obsidian, .trash Ordner) verschieben**: Du kannst gelöschte Dateien auch in den `.trash`-Ordner deines Vaults verschieben lassen.
> - **Endgültig löschen**: Dateien werden sofort gelöscht und können nicht wiederhergestellt werden.
