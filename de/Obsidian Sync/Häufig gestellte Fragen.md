---
aliases:
  - Einschränkungen
  - Sync-Einschränkungen
  - Sync FAQ
  - Obsidian Sync/Sync-Einschränkungen
description: Finde Antworten auf häufig gestellte Fragen zu Obsidian Sync und dessen Einschränkungen.
mobile: true
permalink: sync/faq
publish: true
---

Hier erläutern wir einige häufig gestellte Fragen zu [[Einführung in Obsidian Sync|Obsidian Sync]] und dessen Einschränkungen.

## Allgemein

### Welche Betriebssysteme werden von Obsidian Sync unterstützt?

Obsidian Sync unterstützt jede Plattform, auf der auch die Obsidian-Anwendung läuft. Derzeit sind das Windows, macOS, Linux, Android und iOS.

### Funktioniert Obsidian mit dem Apple-Blockierungsmodus?

Obsidian kann im [Blockierungsmodus](https://support.apple.com/de-de/105120) verwendet werden, solange Obsidian von den Auswirkungen ausgeschlossen wird.

### Welche Arten von Daten werden synchronisiert?

Standardmäßig werden deine Notizen, Bilder und der Obsidian-[[Konfigurationsordner]] synchronisiert. 

Zusätzlich kannst du die Synchronisation von PDFs, Audios, Videos und anderen Dateien [[Konfiguration und selektive Synchronisierung|konfigurieren]].

### Wie viel Speicherplatz steht mir zur Verfügung?

Die Speicherbeschränkung hängt von deinem Obsidian [[Tarife und Speicherkapazität#Tarifübersicht|Sync-Tarif]] ab. Du kannst maximal 100 GB Speicherplatz erwerben. Der [[Versionsverlauf]] wird auf deinen Speicherlimit angerechnet. 

In den **Einstellungen → Sync** kannst du unter **Größe des Vaults** deinen aktuellen Speicherverbrauch einsehen.

### Wie viele Remote-Vaults stehen mir zur Verfügung?

Die Anzahl der verfügbaren Remote-Vaults ist abhängig von deinem Obsidian [[Tarife und Speicherkapazität#Tarifübersicht|Sync-Tarif]]. Im *Standard-Tarif* ist ein Vault inbegriffen, mit dem *Plus-Tarif* kannst du 10 Remote-Vaults verwalten. Die von anderen mit dir geteilten Vaults werden nicht auf dein Limit angerechnet.

### Wie groß kann jeder Remote-Vault sein?

Das Speicherlimit ist an dein Benutzerkonto gebunden. Es gibt keine Maximal-Größe je Vault, solange das Gesamt-Speicherlimit nicht überschritten wird.

### Mit wie vielen Mitwirkenden kann ich einen Remote-Vault teilen?

Du kannst einen Remote-Vault mit bis zu 20 Mitwirkenden [[Zusammenarbeit in einem freigegebenen Vault|teilen]].

### Was ist die Maximalgröße für eine einzelne Datei?

Die Maximalgröße für Dateien ist abhängig von deinem Obsidian [[Tarife und Speicherkapazität|Sync-Tarif]]. Im *Standard-Tarif* kann eine Datei maximal 5 MB groß sein. Das Limit für den *Plus-Tarif* liegt bei 200 MB je Datei.

### Werden meine Daten im Hintergrund synchronisiert?

Nein, Dateien werden nur synchronisiert, während Obsidian läuft.

### Werden synchronisierte Einstellungen im laufenden Betrieb aktualisiert?

Obsidian Sync kann bestimmte Einstellungen automatisch aktualisieren, aber es gibt einige Einschränkungen. Für mehr Informationen, siehe [[Konfiguration und selektive Synchronisierung#Neuladen der Einstellungen|Aktualisieren von Einstellungen]].

### Kann ich einen Drittanbieter-Synchronisierungsdienst mit Obsidian Sync verwenden?

Wir raten davon ab, einen Drittanbieter-Synchronisierungsdienst zusammen mit Obsidian Sync einzusetzen. Die gleichzeitige Verwendung eines Drittanbieterdienstes und Obsidian Sync auf mehreren Geräten kann zu Konflikten führen, die möglicherweise doppelte oder beschädigte Dateien zur Folge haben.

Cloud-Speicher-Dienste wie OneDrive oder Dropbox bieten die Funktionen "Files On-Demand" oder "Online-Only", mit denen Dateien nur bei Bedarf heruntergeladen und lokal gelöscht werden, um Speicherplatz zu sparen. Da diese Dateien nicht immer lokal verfügbar sind, interpretiert Obsidian Sync sie als gelöscht, was dazu führt, dass sie auf dem Remote-Vault gelöscht werden.
 
Um solche Probleme zu vermeiden, solltest du On-Demand-Downloads deaktivieren, wenn du Obsidian Sync mit Diensten wie OneDrive oder Dropbox verwendest. Du musst sicherstellen, dass der Drittanbieterdienst so konfiguriert ist, dass Dateien immer auf deinem Gerät verfügbar sind.

## Datenspeicherung

Dies sind einige häufig gestellte Fragen zur Datenspeicherung in Obsidian. Ausführlichere Informationen findest du im Abschnitt [[Obsidian Sync/Sicherheit und Datenschutz|Sicherheit und Datenschutz]].

### Wie lange wird der Versionsverlauf aufbewahrt?

Die Aufbewahrungszeit für den [[Versionsverlauf]] ist abhängig von deinem Obsidian [[Tarife und Speicherkapazität|Sync-Tarif]]. Im *Standard-Tarif* wird der Verlauf einen Monat lang gespeichert. Im *Plus-Tarif* sind es 12 Monate. Nach Ablauf dieses Zeitraums werden ältere Versionen gelöscht.

Ältere Versionen von [[Anhänge|Anhängen]] werden zwei Wochen lang vorgehalten.

### Wie lange werden meine Daten nach Ablauf meines Abos gespeichert?

Daten in deinem Remote-Vault, einschließlich Versionsverlauf, werden nach Ablauf deines Abos noch einen Monat lang gespeichert, bevor wir sie löschen. Die Daten in deinen lokalen Vaults bleiben davon unberührt.

Solange du dein Abo innerhalb eines Monats verlängerst, sind deine Daten sicher. Wenn du das Abo erst nach Ablauf des Monats verlängerst, nachdem deine Remote-Vaults gelöscht wurden, kannst du einen [[Obsidian Sync einrichten|neuen Remote-Vault erstellen]] und deinen lokalen Vault damit verbinden.

### Bleiben meine Daten gespeichert, wenn ich mein Abo kündige?

Nein. Deine Daten werden sofort von den Obsidian Sync-Servern gelöscht, wenn du dein Abo kündigst. Daten in deinem [[Lokale und Remote-Vaults|lokalen Vault]] sind davon nicht betroffen.
