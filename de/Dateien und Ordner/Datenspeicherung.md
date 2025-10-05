---
aliases:
  - Fortgeschrittene Themen/Wie Obsidian Daten speichert
description: Erfahre, wie Obsidian Daten auf deinem Gerät speichert.
mobile: true
permalink: datenspeicherung
publish: true
---

Obsidian speichert deine Notizen als [[Formatierungsgrundlagen|Markdown-formatierte]] Textdateien in einem *Vault*. Ein Vault ist ein Ordner in deinem lokalen Dateisystem, der Unterordner und Dateien enthält.

Da Notizen einfache Textdateien sind, kannst du sie mit einem beliebigen anderen Texteditor oder Dateimanager bearbeiten und verwalten. Obsidian aktualisiert deinen Vault automatisch, auch bei externen Änderungen.

Du kannst einen Vault überall dort erstellen, wo es dein Betriebssystem erlaubt. Obsidian synchronisiert sich mit [[Obsidian Sync/Einführung|Obsidian Sync]], Dropbox, iCloud, OneDrive, Git und vielen anderen Drittanbieter-Diensten.

Du kannst mehrere Ordner als einzelne Vaults öffnen, z.B. um Notizen für die Arbeit und für die Schule zu trennen.

> [!warning] Verschachtelte Vaults
> [[Interne Links|Interne Links]] beziehen sich immer lokal auf einen Vault. Deshalb ist es nicht ratsam, einen Vault innerhalb eines Vaults zu erstellen, da interne Links dann möglicherweise nicht korrekt aktualisiert werden.

## Vault-Einstellungen

Obsidian erstellt einen [[Konfigurationsordner|Konfigurationsordner]] `.obsidian` im Stammverzeichnis des Vaults, in welchem die spezifischen Einstellungen für diesen Vault gespeichert werden, z.B. [[Tastenkürzel|Tastenkürzel]], [[Themen|Themen]] und [[Externe Erweiterungen|Plugins]].

Standardmäßig werden bei den meisten Betriebssystemen Ordner, die mit einem Punkt (`.`) beginnen, als versteckte Verzeichnisse ausgeblendet. Du kannst in deinem Dateimanager versteckte Dateien einblenden.

- **macOS**: Im Finder drücke `Cmd + Umschalt + .` (Punkt), um versteckte Dateien einzublenden.
- **Windows**: [Ausgeblendete Dateien anzeigen](https://support.microsoft.com/de-de/windows/explorer-unter-windows-ef370130-1cca-9dc5-e0df-2f7416fe1cb1)
- **GNU/Linux:** Gib im Terminal `ls -a` ein, um versteckte Dateien anzuzeigen.

> [!tip] `.obsidian` unter Git
> Die Dateien `.obsidian/workspace.json` und `.obsidian/workspaces.json` speichern das aktive Workspace-Layout und werden jeweils aktualisiert, sobald du eine neue Datei öffnest. Wenn du [Git](https://git-scm.com) verwendest, um deinen Vault zu verwalten, möchtest du diese Dateien möglicherweise in der `.gitignore` hinzufügen.

## Globale Einstellungen

Globale Einstellungen speichert Obsidian in einem Systemverzeichnis. Der Speicherort hängt vom jeweiligen Betriebssystem ab.

- **macOS**: `/Users/deinbenutzername/Library/Application Support/obsidian`
- **Windows**: `%APPDATA%\Obsidian\`
- **Linux**: `$XDG_CONFIG_HOME/obsidian/` oder `~/.config/obsidian/`

> [!warning] Erstelle keinen Vault im Systemordner. Dies kann zu Datenbeschädigung oder -verlust führen.

## IndexedDB

IndexedDB ist eine client-seitige Low-Level-Datenbank, die Obsidian als Backend-Speicher verwendet. Sie wird benötigt, um [[Obsidian Sync/Einführung|Obsidian Sync]]-Verbindungen aufrecht zu erhalten und bewahrt den [[#Metadaten-Cache]], wenn die Anwendung geschlossen wird.

> [!warning] Auf Apple-Geräten mit aktiviertem [Blockierungsmodus](https://support.apple.com/de-de/105120), von dem Obsidian nicht ausgenommen ist, kann die Anwendung nicht in diese Datenbank speichern. Der Vault wird dann bei jedem Start neu indiziert.

### Metadaten-Cache

Um die Performanz der Anwendung zu erhöhen, speichert Obsidian lokale Metadaten zu den Dateien in deinem Vault im sogenannten **Metadaten-Cache**. Diese Metadaten werden für viele Funktionen benötigt, von der Gliederungsansicht bis zur Graph-Ansicht.

Obsidian synchronisiert diesen Cache automatisch mit den Dateien in deinem Vault. Dennoch kann es vorkommen, dass Metadaten und Dateien nicht mehr zueinander passen. Sollte dies der Fall sein, kannst du in den Einstellungen ( ![[lucide-settings.svg#icon]] ) einen Neuaufbau des Metadaten-Cache initiieren unter **Dateien & Links → Vault-Cache zurücksetzen**.
