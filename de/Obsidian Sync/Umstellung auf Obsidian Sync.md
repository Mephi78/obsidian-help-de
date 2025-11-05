---
aliases:
  - Obsidian Sync/Obsidian Sync und Drittanbieter-Dienste
  - Obsidian Sync/Migration nach Obsidian Sync
cssclasses:
  - soft-embed
description: Erfahre, wie du von einem Drittanbieter-Dienst nach Obsidian Sync wechselst.
mobile: true
permalink: sync/migration
publish: true
---

Erfahre, wie du deinen Vault von der derzeitigen Synchronisierungslösung auf Obsidian Sync umstellen kannst.

> [!warning] Vermeide die gleichzeitige Verwendung mehrerer Synchronisierungslösungen für dieselben Dateien
> Es ist [[Häufig gestellte Fragen#Kann ich einen Drittanbieter-Synchronisierungsdienst mit Obsidian Sync verwenden?|nicht empfohlen]], Obsidian Sync neben Cloud-Speicherdiensten (z.B.  iCloud, Dropbox, OneDrive, Google Drive) zu verwenden, da dies zu Konflikten führen kann. Cloud-Speicherdienste können jedoch eine Rolle in deiner [[Sichere deinen Vault|Backup]]-Strategie spielen.

## Verschiebe deinen Vault aus deinem Drittanbieter-Sync- oder Cloud-Speicher

Wenn dein Vault an einem der folgenden Speicherorte gespeichert ist, wird er wahrscheinlich von einem Drittanbieter-Dienst synchronisiert:

- **Windows**: `C:\Benutzer\Benutzername\Desktop` oder `C:\Benutzer\Benutzername\Dokumente`
- **macOS**: `/benutzer/benutzername/Desktop` oder `/benutzer/benutzername/Dokumente`
- **iOS**: Das **iCloud**-Verzeichnis in der App *Dateien*
- **Andere**: Jeder Ordner unter einem Synchronisierungsdienst, wie bspw. `Drive/mein-vault`, `Dropbox/mein-vault`, `pSync/mein-vault`

Obwohl Android und Linux damit in der Regel weniger Probleme haben, schadet es nicht, den Speicherort deines Vaults auf diesen Geräten zu überprüfen.

> [!tip] Wenn dein lokaler Vault mit einem Remote-Vault verbunden ist, versucht Obsidian zu erkennen, ob sich dein Vault in einem Synchronisierungsverzeichnis befindet. Ist dies der Fall, wird oben in den Sync-Einstellungen eine Meldung angezeigt.

Um Konflikte mit anderen Synchronisierungsdiensten zu vermeiden, empfehlen wir einen der folgenden Speicherorte für deinen Vault:

- **Windows**: in dieser Reihenfolge empfohlene Ordner:
    1. `D:\` bzw. jedes andere Laufwerk, außer dem Systemlaufwerk oder Netzlaufwerken
    2. `C:\Vaults` (wenn du Schreibberechtigungen auf dem C-Laufwerk hast)
    3. `C:\Benutzer\Benutzername\Vaults` (falls dein Vault in `C:\Benutzer\Benutzername` verbleiben muss, stelle sicher, dass OneDrive keine Dateien löscht. OneDrive verhält sich außerhalb der Ordner `Desktop` und `Dokumente` weniger aggressiv)
- **macOS**: `/benutzer/benutzername/vaults`
- **Linux**: Keine spezifische Empfehlung. Stelle sicher, dass Obsidian volle Lese- und Schreibrechte hat und der Ordner nicht von einem anderen Synchronisierungsdienst verwaltet wird.
- **iOS/iPadOS**: Speichere den Vault auf dem **iPhone**-Speicher bzw. **Auf dem Gerät**.
- **Android**: Verwende den Ordner `Dokumente/` auf dem Gerät.

## Vault mit Obsidian verschieben in der Desktop-Anwendung

![[Vaults verwalten#Vault in einen anderen Ordner verschieben]]

## Vault mit Obsidian Mobile verschieben

Auf Mobilgeräten läuft Obsidian in einer Sandbox-Umgebung, so dass du Vaults nicht auf dieselbe Weise aus der App heraus verschieben kannst, wie in der Desktop-Anwendung.

### Android

Android-Dateisysteme variieren stark, je nach Gerät, aber im Allgemeinen erfordern sie dieselben Schritte, die notwendig sind, um einen Vault manuell zu verschieben. Stelle in jedem Fall sicher, deinen Vault aus allen Synchronisierungsdiensten auf deinem Gerät zu entfernen.

### iOS und iPadOS

Um einen vorhandenen iCloud-Vault auf dein Gerät zu verschieben:

> [!note] Wenn du die Daten bereits auf einem anderen Gerät hast und mit Obsidian Sync synchronisierst, empfehlen wir, einen [[Obsidian Sync einrichten#Remote-Vault auf anderem Gerät synchronisieren|neuen lokalen Vault aus dem Remote-Vault zu erstellen]], anstatt den bestehenden Vault zu verschieben.

- [[Sichere deinen Vault]].
- Erstelle einen neuen Vault auf deinem Gerät und stelle sicher, dass **In iCloud speichern** deaktiviert ist.
- Beende Obsidian auf allen Geräten, um Obsidian Sync anzuhalten.
- Öffne die App **Dateien** auf deinem iOS/iPadOS-Gerät.
- Halte den Vault-Ordner in **iCloud → Obsidian** lange gedrückt und wähle **Verschieben**.
- Verschiebe den Vault nach **Auf dem iPhone/Gerät → Obsidian** und prüfe, ob er nun dort angezeigt wird.
- Tippe **Kopieren**.
- Kehre zurück zum **iCloud Drive → Obsidian** und lösche den alten Vault-Ordner.

Sobald du Obsidian erneut startest, sollte der Vault mit einem Vault-Symbol (anstelle des Cloud-Symbols) angezeigt werden. Obsidian Sync sollte nun auch in den Sync-Einstellungen keine Warnmeldung mehr anzeigen.

## Nächste Schritte

- Mit der Synchronisierung beginnen? [[Obsidian Sync einrichten]]
- Benötigst du weitere Hilfe? [[Obsidian Sync/Fehlerbehandlung]]
