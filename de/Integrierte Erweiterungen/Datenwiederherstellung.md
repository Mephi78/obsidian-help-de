---
aliases: 
description: Datenwiederherstellung schützt deine Arbeit vor unbeabsichtigtem Datenverlust mit regelmäßigen automatischen Snapshots.
mobile: true
permalink: plugins/datenwiederherstellung
publish: true 
---

Die [[Übersicht|Standarderweiterung]] *Datenwiederherstellung* schützt deine Arbeit vor versehentlichem Löschen, Dateibeschädigungen oder unerwünschten Änderungen, indem sie in regelmäßigen Abständen automatisch vollständige Snapshots deiner Notizen speichert. Die Dateiwiederherstellung ist keine vollständige Backup-Lösung, daher empfehlen wir, deine Obsidian-Dateien [[Sichere deinen Vault|zusätzlich separat zu sichern]].

Um nicht zu viel [[#Speicher und Leistung|Speicherplatz]] zu beanspruchen, werden die Snapshots nur für eine bestimmte Anzahl an Tagen gespeichert und dann gelöscht. Snapshots enthalten den gesamten Inhalt deines Vaults, nicht nur die Änderungen, damit du jede vorherige Version wiederherstellen kannst.

> [!note] Standardmäßig werden Snapshots in einem Mindestabstand von fünf Minuten gespeichert und sieben Tage aufbewahrt. Beide Intervalle kannst du in den Einstellungen ändern unter **Obsidian-Erweiterungen → Datenwiederherstellung**.

Snapshots werden in den [[Datenspeicherung#Globale Einstellungen|Globalen Einstellungen]] außerhalb deines Vaults gespeichert, um Datenverlust im Zusammenhang mit dem Vault zu berücksichtigen. Hierbei wird jeweils der absolute Pfad zur Notiz verwendet. Wenn du also deinen Vault kürzlich im Dateisystem verschoben hast und Daten von einem Zeitpunkt vor dem Verschieben wiederherstellen möchtest, ist es notwendig, den Vault zunächst wieder an den vorherigen Speicherort zu bewegen.

> [!tip] Bei der Verwendung von [[Obsidian Sync/Einführung|Obsidian Sync]] oder [[Synchronisiere Notizen zwischen Geräten|anderen Synchronisationsdiensten]] werden Snapshots für die Datenwiederherstellung nicht synchronisiert. Snapshots sind gerätespezifisch und verbleiben lokal auf jedem Gerät.

## Snapshot wiederherstellen

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Obsidian-Erweiterungen → Datenwiederherstellung**.
3. Klicke neben **Sicherungskopien** auf **View**.
4. Gib den Titel einer Notiz ein, die du wiederherstellen möchtest, und es wird eine Liste mit Vorschlägen angezeigt.
5. Wenn du eine Datei auswählst, wird eine Liste der verfügbaren Sicherungskopien angezeigt.
6. Wähle den Snapshot aus, den du wiederherstellen möchtest.
    1. Du kannst über die Schaltfläche **Kopieren** den Inhalt kopieren, um ihn in eine neue Notiz einzufügen.
    2. Oder die Datei komplett wiederherstellen über die Schaltfläche **Diese Version wiederherstellen**.
7. Optional kannst du dir die **Unterschiede anzeigen** lassen, um zu sehen, welche Inhalte hinzugefügt, entfernt oder geändert wurden zwischen den Snapshot-Versionen.

## Snapshot-Verlauf löschen

> [!danger] Beim Leeren des Snapshot-Archivs werden alle Sicherungskopien für deinen Vault unwiderruflich gelöscht.

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Obsidian-Erweiterungen → Datenwiederherstellung**.
3. Klicke neben **Archiv leeren** auf **Leeren**.
4. Bestätige die Sicherheitsabfrage mit **Leeren**.

## Speicher und Leistung

Die Sicherungskopien für die Datenwiederherstellung benötigen in der Regel wenig Speicherplatz, da nur geänderte Dateien gespeichert werden. In Vaults mit vielen großen Dateien oder häufigen Änderungen können sich die Sicherungskopien jedoch aufsummieren. Beobachte deine Speichernutzung und passe bei Bedarf die Aufbewahrungsfrist an.

## Einschränkungen

- **Apple Blockierungsmodus**: Die Funktion ist auf Apple-Geräten mit aktiviertem [Blockierungsmodus](https://support.apple.com/en-us/105120) nicht verfügbar, wenn Obsidian davon nicht ausgenommen ist.
- **Dateitypen**: Mit der Datenwiederherstellung können nur `.md` und `.canvas` Dateien wiederhergestellt werden.
- **Vault-Speicherort**: Wenn du deinen Vault ohne Verwendung der [[Vaults verwalten#Vault in einen anderen Ordner verschieben|Vault-Verwaltung]] verschiebst, sind vorhandene Snapshots möglicherweise nicht mehr zugänglich.

