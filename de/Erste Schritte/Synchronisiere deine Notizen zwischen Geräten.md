---
aliases:
  - Gewusst wie/Geräteübergreifende Synchronisation
cssclasses:
  - soft-embed
description: Wie man Obsidian Notizen zwischen Geräten und Plattformen synchronisiert.
mobile: true
permalink: notizen-synchronisieren
publish: true
---

Obsidian speichert Notizen lokal auf deinem Gerät, so dass du jederzeit Zugriff darauf hast, sogar offline. Um deine Notizen auf mehreren Geräten verfügbar zu machen, musst du eine Synchronisierung einrichten.

Dieser Leitfaden erklärt gängige Synchronisierungsmethoden und gibt Tipps, wie du Datenverlust vermeiden und einen reibungslosen Ablauf sicherstellen kannst.

Wir empfehlen auch, unseren [[Back up your Obsidian files|Backup-Leitfaden]] zu lesen, um deine Daten zu sichern.

## Synchronisierungsmethoden

Obsidian speichert deine Daten einfach als Dateien in einem Ordner, dem sogenannten [[Local and remote vaults|Vault]]. Damit ergeben sich viele Möglichkeiten, deine Daten zu synchronisieren.

Hier sind einige Synchronisierungsmethoden, die sich für [Obsidian-Nutzer](https://obsidian.md/community) bewährt haben:

1. **Unsere Eigenentwicklung**: [[#Obsidian Sync]]
2. **Cloud-Lösungen von Drittanbietern**: [[#iCloud]], [[#OneDrive]] oder [[#Google Drive]]
3. **Lokale Synchronisierung**: [[#Syncthing]]
4. **Versionskontrolle**: [[#Git]] und [[#Working Copy]]

## Obsidian Sync

**Empfohlene Systeme**: `Windows`, `macOS`, `Linux`, `iOS`, `Android`

Die einfachste und offiziell unterstützte Synchronisierungsmethode bietet unsere Lösung aus erster Hand: [[Introduction to Obsidian Sync|Obsidian Sync]].

Obsidian Sync ist Ende-zu-Ende-verschlüsselt für maximale Privatsphäre und bietet eine nahtlose Integration in Obsidian.

Folge dem [[Set up Obsidian Sync|Konfigurationsleitfaden]], um Obsidian Sync einzurichten.

> [!Important] Vermeide die gleichzeitige Nutzung von Obsidian Sync mit anderen Cloud-Diensten, wie Dropbox oder OneDrive, **für denselben Vault**, da dies zu Datenkonflikten und Beschädigung deiner Dateien führen kann.

## iCloud

**Empfohlene Systeme**: `macOS`, `iOS`, `iPadOS`

iCloud kann verwendet werden, um Vaults zwischen iOS und macOS zu synchronisieren. Allerdings kann die Verwendung von **iCloud Drive unter Windows** zur Duplizierung oder Beschädigung von Dateien führen.

**Wie du einen Vault mit iCloud Drive synchronisierst**:

- **Aktiviere iCloud Drive**:
    - macOS: Öffne die **Systemeinstellungen**, klicke auf **Apple ID** bzw. **iCloud → iCloud Drive**.
    - iOS: Öffne die **Einstellungen**, tippe auf deinen **Namen → iCloud → iCloud Drive**.
- **Erstelle einen neuen Vault in iCloud**:
    - macOS:
        1. Öffne **Obsidian** und wähle **Einen neuen Vault erstellen**.
        2. Im Dateiauswahl-Dialog navigiere zu **iCloud Drive → Obsidian**.
        3. Erstelle einen Ordner für deinen Vault und gib ihm einen Namen.
        4. Wähle **Erstellen**.
    - iOS:
        1. Öffne **Obsidian** und tippe **Einen neuen Vault erstellen**.
        2. Gib einen Namen für deinen Vault ein.
        3. Aktiviere **In iCloud speichern**.
        4. Tippe **Erstellen**.
- **Öffne den Vault auf einem anderen Apple Gerät**: 
    - Auf einem anderen macOS oder iOS Gerät starte **Obsidian**, öffne die [[Manage vaults|Vault-Verwaltung]] und wähle **Ordner als Vault öffnen**. Navigiere zu **iCloud Drive → Obsidian**.

> [!Tip] Erfolgsrezepte:
> - Unter **macOS 14 (Sonoma) und älter**: Deaktiviere **Speicher optimieren** in den iCloud Einstellungen, um zu verhindern, dass Dateien ausgelagert werden. Diese Einstellung wirkt sich auf deinen gesamten iCloud Speicher aus, nicht nur auf Obsidian
> - Unter **macOS 15 (Sequoia)**: Klicke im iCloud Drive mit Rechts auf den **Obsidian** Ordner und wähle **Heruntergeladene Dateien behalten**.

## OneDrive

**Empfohlene Systeme**: `Windows`, `macOS` (eingeschränkte Funktionalität auf Android)

[OneDrive](https://support.microsoft.com/de-de/office/synchronisieren-mit-onedrive-bb89981b-e382-4969-b8fd-d413a90b6db3) ist ein beliebter Cloud-Speicher für Windows und macOS. Unter Android ist dieser allerdings nur eingeschränkt nutzbar. Eine Synchronisierung von Obsidian Vaults auf iOS wird nicht offiziell unterstützt.

> [!Important] Vor der Synchronisierung mit OneDrive solltest unbedingt du sicherstellen, dass für deinen Vault-Ordner die Option **Immer auf diesem Gerät behalten** aktiviert ist. Diese Einstellung verhindert, dass OneDrive Dateien auslagert und Obsidian denken lässt, dass diese fehlen.

**Wie du einen Vault mit OneDrive synchronisierst**:

1. **OneDrive einrichten**:
   - Windows: Melde dich mit deinem Microsoft-Benutzerkonto in der OneDrive App an.
   - macOS: Lade die OneDrive App herunter und melde dich an.
1. **Erstelle einen neuen Vault in OneDrive**:
   - Windows/macOS:
     1. Öffne den **Explorer** (Windows) oder den **Finder** (macOS) und navigiere zu **OneDrive → Dokumente**.
     2. Erstelle einen neuen Ordner (z.B. "Obsidian Vault").
     3. Starte **Obsidian**, klicke **Einen neuen Vault erstellen** und wähle den OneDrive Ordner aus.
1. **Öffne den Vault auf einem anderen Gerät**:
	- Auf einem anderen Gerät starte **Obsidian**, öffne die [[Manage vaults|Vault-Verwaltung]] und wähle **Ordner als Vault öffnen**. Navigiere zu **OneDrive → Dokumente**.

> [!Note] OneDrive funktioniert möglicherweise nicht gut für die Synchronisierung mit Android. Wir empfehlen die Nutzung anderer Apps, wie [Dropsync](https://play.google.com/store/apps/details?id=com.ttxapps.dropsync&hl=de) oder [FolderSync](https://play.google.com/store/apps/details?id=dk.tacit.android.foldersync.lite&hl=de).

> [!Tip] Erfolgsrezepte:
> - Behalte deine Vault-Dateien immer **Offline verfügbar** mit Rechtsklick auf den Ordner und der Auswahl **Immer auf diesem Gerät behalten**.
> - Verzichte auf die Verwendung der OneDrive-Funktion **Files On-Demand** für deine Vaults, um Synchronisierungsprobleme zu vermeiden.

## Google Drive

**Empfohlene Systeme**: `Windows`, `macOS`, `Android` (eingeschränkte Funktionalität unter iOS)

[Google Drive](https://support.google.com/a/users/answer/9310246?hl=de) ist eine weitere beliebte Cloud-Speicher-Lösung. Obwohl nicht offiziell als Synchronisierungsmethode unterstützt, kannst du Drittanbieter-Anwendungen und Plugins verwenden, um deine Obsidian Vaults geräteübergreifend zu synchronisieren.

> [!Important] Google Drive wird nicht offiziell unterstützt für die Synchronisierung von Obsidian Vaults unter iOS. Wir empfehlen die Verwendung anderer Synchronisierungsmethoden.

**Wie du einen Vault mit Google Drive synchronisierst**:

1. **Google Drive einrichten**:
    - Windows/macOS: Lade die Google Drive App herunter und melde dich an.
    - Android: Stelle sicher, dass Google Drive aktiviert ist und melde dich an.
2. **Erstelle einen neuen Vault in Google Drive**:
    - Windows/macOS:
        1. Öffne den **Explorer** (Windows) oder **Finder** (macOS) navigiere zu **Google Drive**.
        2. Erstelle einen neuen Ordner (z.B. "Obsidian Vault").
        3. Starte **Obsidian**, klicke **Einen neuen Vault erstellen** und wähle den Google Drive Ordner aus.
3. **Öffne den Vault auf einem anderen Gerät**:
	- Auf einem anderen Gerät starte **Obsidian**, öffne die [[Manage vaults|Vault-Verwaltung]] und wähle **Ordner als Vault öffnen**. Navigiere zu deinem Google Drive Ordner.

> [!Tip] Erfolgsrezepte:
> - Setze deine Vault-Dateien auf **Offline verfügbar**, um Synchronisierungsprobleme mit Google Drive aufgrund von Dateiauslagerungen zu vermeiden.
> - Für iOS empfehlen wir, eine alternative Synchronierungsmethode zu nutzen, wie [[Introduction to Obsidian Sync|Obsidian Sync]], [[#iCloud]] oder das **Remotely Save** Plugin.

## Syncthing

**Empfohlene Systeme**: `Windows`, `macOS`, `Linux`, `Android`

Syncthing ermöglicht die dezentralisierte Synchronisierung von Dateien ohne Cloud-Speicher. Die quelloffene Software synchronisiert deine Daten direkt zwischen deinen Geräten, privat und sicher, über eine Peer-to-Peer-Verbindung.

**Wie du einen Vault mit Syncthing synchronisierst**:

1. **Syncthing einrichten**:
   - Installiere Syncthing auf jedem Gerät, mit dem du deine Dateien synchronisieren möchtest. Eine Installationsanleitung findest du in der [Syncthing-Dokumentation](https://docs.syncthing.net/).
1. **Einen freigegebenen Ordner erstellen und einrichten**:
   - Auf allen Geräten:
     1. Öffne Syncthing und erstelle einen freigegebenen Ordner (Sharing). Setze den Verzeichnispfad auf deinen Obsidian Vault.
     2. Stelle sicher, dass auf allen Geräten derselbe Ordner ausgewählt ist.
     3. Konfiguriere die Verzeichnissynchronisation (z.B. **Send & Receive** für die bidirektionale Synchronisierung).
1. **Öffne den Vault auf einem anderen Gerät**:
	- Sobald der Ordner geräteübergreifend synchronisiert ist, starte **Obsidian** auf einem anderen Gerät, öffne die [[Manage vaults|Vault-Verwaltung]] und wähle **Ordner als Vault öffnen**.

> [!Note] Syncthing funktioniert am besten, wenn mindestens ein Gerät immer eingeschaltet ist, um eine kontinuierliche Synchronisation zu gewährleisten.

> [!Tip] Erfolgsrezepte:
> - Für die lokale Synchronisierung stelle sicher, dass alle Geräte mit demselben Netzwerk verbunden sind.
> - Schließe den Ordner `.obsidian` von der Synchronisation aus, wenn du Obsidian auf deinen Geräten unterschiedlich konfigurieren möchtest.
> - Verwende die Funktion **Ignore Patterns**, um temporäre Dateien oder Sicherungskopien von der Synchronisation auszuschließen.

## Git

**Empfohlene Systeme**: `Windows`, `macOS`, `Linux`

**Git** ist ein verteiltes Versionskontrollsystem, das es dir ermöglicht, gleichzeitig mit anderen an einem Vault zu arbeiten, Änderungen nachzuverfolgen und den Vault über ein Repository zu synchronisieren, bspw. auf Codeberg, GitHub, GitLab oder einer selbst gehosteten Instanz.

**Wie du einen Vault mit Git synchronisierst**:

1. **Ein Remote-Repository einrichten**:
    - Erstelle ein Repository auf einer Git-Hosting-Plattform (z.B. Codeberg, GitHub, GitLab, oder Self-Hosting).
2. **Synchronisiere deinen Vault**:
    1. Öffne ein Terminal oder einen Git-Client mit graphischer Bedienoberfläche (z.B. GitKraken oder Sourcetree) und wechsle in deinen Vault-Ordner: `cd pfad/zum/vault`
    2. Initialisiere ein Git-Repository in deinem Vault-Ordner: `git init`
    3. Füge das Remote-Repository hinzu: `git remote add origin [URL]`
    4. Füge die Dateien, die du synchronisieren möchtest, dem Staging-Bereich zu: `git add .`
    5. Committe deine Änderungen: `git commit -m "Deine Commit-Nachricht"`
    6. Übertrage deine Änderungen: `git push origin main`
3. **Synchronisiere deinen Vault mit anderen Geräten**:
    - Klone das Repository auf einem anderen Gerät und rufe die Änderungen ab, um sie auf das Gerät zu übertragen: `git pull origin main`
    - Denke daran, Änderungen auf diesem Gerät wiederum an das Remote-Repository zu übertragen (siehe oben).

> [!Note] Git bietet eine starke Versionskontrolle, aber die Synchronisierung erfolgt nicht automatisch. Du musst Änderungen manuell herunterladen (pullen) bzw. übertragen (pushen).

## iPhone und iPad

**Empfohlene Methoden**:
- [[Introduction to Obsidian Sync|Obsidian Sync]]
- [[#iCloud]]

> [!Important] Vermeide die gleichzeitige Verwendung unterschiedlicher Synchronisierungsdienste **für denselben Vault** (bspw. die gleichzeitige Nutzung von Obsidian Sync und iCloud), da dies zu Datenkonflikten und Beschädigung deiner Dateien führen kann.

**Nicht unterstützte Methoden**:

Die folgenden Dienste sind nicht offiziell unterstützt auf iOS, aber Obsidian-Anwender haben Workarounds gefunden für den Einsatz von Drittanbieter-Tools oder Plugins:

- Dropbox
- Google Drive
- OneDrive
- Syncthing

Einige Anwender haben Plugins wie **Remotely Save** oder **LiveSync** erfolgreich zur Vault-Synchronisierung unter iOS eingesetzt. Allerdings sind diese Methoden nicht offiziell unterstützt und die Ergebnisse können unterschiedlich ausfallen.

### Working Copy

**Empfohlene Systeme**: `iOS`
**Erfordert**: [[#Git]]

**Working Copy** ist ein Git-Client für iOS, der es ermöglicht, ein Git-Repository zu klonen und Änderungen via Commit und Push zu übertragen. Die Lösung funktioniert gut für die Git-Synchronisierung von Obsidian-Vaults, jedoch sind einige Funktionen kostenpflichtig und erfordern In-App-Käufe.

**Wie du einen Vault mit Working Copy synchronisierst**:

1. **Installiere Working Copy**:
    - Lade die **[Working Copy](https://apps.apple.com/de/app/working-copy-git-client/id896694807)** App auf dein iPhone oder iPad.
2. **Klone dein Git-Repository**:
    - Öffne die Working Copy App, tippe auf das `+` rechts oben in der Repository-Liste, gib die URL deines Repositorys ein und tippe auf **Klonen**.
3. **Repository mit Obsidian verknüpfen**:
    - Verknüpfe den Ordner des geklonten Repositorys mit einem leeren Vault in **Obsidian**.
4. **Synchronisiere deinen Vault mit anderen Geräten**:
    - Übertrage deine Änderungen im Obsidian-Vault, indem du diese mit Working Copy committest und auf dein Remote-Repository pushst.
    - Klone dein Remote-Repository auf anderen Geräten und pulle die Änderungen mit [[#Git]].

> [!Note] Obwohl Working Copy nicht offiziell unterstützt wird, haben viele Anwender ihre Obsidian-Vaults bereits erfolgreich mit Git synchronisiert.

## Vergleich

Jede Synchronisierungsmethode hat ihre Vor- und Nachteile, was Kosten, Privatsphäre und Funktionalität betrifft.

|                                                  | Ende-zu-Ende<br>Verschlüsselung | Versions-<br>Historie |
| ------------------------------------------------ | ------------------------ | ------------------ |
| [[Introduction to Obsidian Sync\|Obsidian Sync]] | ✅                        | ✅                  |
| iCloud                                           | Optional                 | ❌                  |
| OneDrive                                         | ❌                        | ❌                  |
| Google Drive                                     | ❌                        | ❌                  |
| Syncthing                                        | Optional                 | ✅                  |
| Git                                              | ❌                        | ✅                  |

## Häufig gestellte Fragen (FAQ)

**Warum wird mein bevorzugter Synchronisierungsdienst nicht offiziell unterstützt?**

Im Gegensatz zu anderen Notiz-Apps, die nur jeweils auf einzelne Dateien zugreifen, benötigt Obsidian den Zugriff auf den gesamten Vault, damit bestimmte Funktionen - wie die automatische Aktualisierung von Links beim Umbenennen von Notizen - wirksam werden. Das erschwert es einigen Diensten, zuverlässig mit Obsidian zu funktionieren.

**Warum sollte ich Dateien "Offline verfügbar" halten?**

Wenn Dienste wie OneDrive oder iCloud Dateien auslagern, (z.B. mit Funktionen wie **Files On-Demand** oder **Speicher optimieren**), kann Obsidian nicht darauf zugreifen, was zu Synchronisierungsproblemen führt. Kennzeichne deinen Vault-Ordner als **Immer auf diesem Gerät behalten** (OneDrive) bzw. stelle sicher, dass **Heruntergeladene Dateien behalten** aktiviert ist (iCloud).

**Wie verwalte ich unterschiedliche Einstellungen für meine Vaults?**

Obsidian erlaubt dir, für jeden Vault-Ordner auf jedem Gerät das Verzeichnis für die Konfigurationsdateien festzulegen mit der [[Configuration folder|Konfigurationsordner-Einstellung]].
