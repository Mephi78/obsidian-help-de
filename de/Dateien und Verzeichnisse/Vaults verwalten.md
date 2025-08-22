---
aliases:
  - Benutzerschnittstelle/Vault-Verwaltung
  - Gewusst wie/Mit mehreren Vaults arbeiten
  - Vault-Verwaltung
permalink: vaults-verwalten
---

Ein **Vault** ist ein Ordner in deinem Dateisystem, der deine Notizen, [[Attachments|Anhänge]] und den [[Konfigurationsordner]] mit Obsidian-spezifischen Einstellungen enthält. Erfahre mehr über Vaults im Abschnitt [[Datenspeicherung]].

Du kannst deine Vaults über die **Vault-Verwaltung** organisieren. Der Dialog für die Vault-Verwaltung öffnet sich, wenn du Obsidian zum ersten Mal startest.

Aus einem geöffneten Vault heraus kannst du zwischen Vaults wechseln, indem du unten in der [[Seitenleisten|linken Seitenleiste]] auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil** klickst und den Vault auswählst, den du öffnen möchtest. Wähle **Vaults verwalten...**, falls der gewünschte Vault nicht in der Liste erscheint. Alternativ kannst du über die [[Command palette|Befehlspalette]] den Befehl **Einen anderen Vault öffnen** auswählen.

## Neuen Vault erstellen

1. Starte Obsidian.
2. Klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
3. Wähle **Vaults verwalten...**.
4. Klicke rechts neben **Einen neuen Vault erstellen** auf **Erstellen**.
5. Gib unter **Name des Vaults** den Namen deines neuen Vaults ein.
6. Klicke **Wählen**, um den **Speicherort** deines neuen Vaults auszuwählen.
7. Klicke **Erstellen**.

## Bestehenden Ordner als Vault öffnen

1. Starte Obsidian.
2. Klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
3. Wähle **Vaults verwalten...**.
4. Klicke rechts neben **Ordner als Vault öffnen** auf **Öffnen**.
5. Wähle im Dateibrowser den Ordner, den du als Vault verwenden möchtest.
6. Klicke **Öffnen**.

> [!tip] Vault aus Obsidian Sync öffnen
> Um zu erfahren, wie du einen Remote-Vault mit Obsidian Sync öffnest, siehe [[Set up Obsidian Sync|Obsidian Sync konfigurieren]].

## Vault umbenennen

Der Name eines Vaults und der des zugehörigen Ordners sind immer identisch. Daher wird beim Umbenennen eines Vaults auch der Ordner umbenannt.

1. Starte Obsidian.
2. Klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
3. Wähle **Vaults verwalten...**.
4. Öffne mit Rechtsklick auf den Vault, den du umbenennen möchtest oder mit Klick auf das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) daneben das Kontextmenü.
5. Wähle ![[lucide-edit-3.svg#icon]] **Vault umbenennen...**.
6. Gib den neuen Namen deines Vaults ein und drücke die `Eingabetaste`.

## Vault in einen anderen Ordner verschieben

1. Starte Obsidian.
2. Klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
3. Wähle **Vaults verwalten...**.
4. Schließe deinen Vault im Hintergrund, aber lass die **Vault-Verwaltung** geöffnet.
5. Öffne mit Rechtsklick auf den Vault, den du verschieben möchtest oder mit Klick auf das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) daneben das Kontextmenü.
6. Wähle ![[lucide-send.svg#icon]] **Vault verschieben...**.
7. Wähle den neuen Speicherort für deinen Vault im sich öffnenden Dateimanager-Dialog.

Manche Betriebssysteme erlauben es nicht, einen Vault über die Vault-Verwaltung zu verschieben. Trifft das für dich zu, musst du den Vault manuell verschieben:

1. Schließe Obsidian.
2. Verschiebe über den Dateimanager deines Betriebssystems den Vault-Ordner an den neuen Speicherort. Vermeide dabei die Verwendung von Verzeichnissen, die von anderen Synchronisierungsdiensten verwaltet werden.
3. Starte Obsidian.
4. Falls die Vault-Verwaltung sich nicht ohnehin bereits automatisch geöffnet hat, klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
5. Wähle **Vaults verwalten...**.
6. Klicke rechts neben **Ordner als Vault öffnen** auf **Öffnen**.
7. Wähle im Dateibrowser den Ordner, den du als Vault verwenden möchtest.
8. Klicke **Öffnen**.
9. Überprüfe, ob der Inhalt deines Vaults unverändert ist. Aktiviere ggf. in den **Einstellungen** ( ![[lucide-settings.svg#icon]] ) die externen Erweiterungen erneut unter **Externe Erweiterungen → Community-Erweiterungen aktivieren**.

## Vault entfernen

Wenn du einen Vault in der Vault-Verwaltung entfernst, wird er nur aus der Liste entfernt, aber nicht gelöscht.

1. Starte Obsidian.
2. Klicke links unten auf dein ![[lucide-chevrons-up-down.svg#icon]] **Vault-Profil**.
3. Wähle **Vaults verwalten...**.
4. Öffne mit Rechtsklick auf den Vault, den du aus der Liste entfernen möchtest oder mit Klick auf das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) daneben das Kontextmenü.
5. Wähle ![[lucide-x.svg#icon]] **Von Liste entfernen**.

## Einstellungen auf einen anderen Vault übertragen

Um deine Vault-Einstellungen auf einen anderen Vault zu übertragen, verwende deinen bevorzugten Dateimanager (oder das Terminal), um den Ordner `.obsidian` aus dem Stammverzeichnis deines Vaults in das Stammverzeichnis des Ziel-Vaults zu kopieren.

Falls der betroffene Vault bereits geöffnet ist, musst du in möglicherweise neu starten, um die Änderungen zu übernehmen.

> [!note] Wo finde ich den `.obsidian` Ordner?
> Die meisten Betriebssysteme blenden Ordner standardmäßig aus, wenn deren Name mit einem Punkt (`.`) beginnt. Erfahre mehr über den `.obsidian` Ordner und wie du darauf zugreifen kannst unter [[Datenspeicherung#Vault-Einstellungen|Vault-Einstellungen]] bzw. [[Konfigurationsordner|Konfigurationsordner]].
