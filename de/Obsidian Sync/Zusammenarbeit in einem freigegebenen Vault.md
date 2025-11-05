---
aliases:
  - Remote-Vaults freigeben
  - Zusammenarbeit
  - Kollaboration
  - Obsidian Sync/Remote-Vaults teilen
description: Erfahre mehr über die Zusammenarbeit mit anderen Obsidan Sync-Nutzern.
mobile: true
permalink: sync/zusammenarbeit
publish: true
---

[[Einführung in Obsidian Sync|Obsidian Sync]] ermöglicht die Zusammenarbeit mit deinem Team in einem freigegebenen Vault.

Alle Mitwirkenden müssen ein aktives Sync-Abo besitzen, um auf einen freigegebenen Vault zugreifen zu können. Die Mitarbeit an von anderen Nutzern freigegeben Vaults wird nicht auf dein [[Häufig gestellte Fragen#Wie viele Remote-Vaults stehen mir zur Verfügung?|Vault-Limit]] angerechnet.

Wenn der Remote-Vault [[Obsidian Sync/Sicherheit und Datenschutz|verschlüsselt]] ist, müssen Mitwirkende das Passwort für die Verschlüsselung eingeben, wenn sie den Vault lokal einrichten.

## Nutzerverwaltung

### Nutzer hinzufügen

So lädst du andere zur Zusammenarbeit ein:

1. Öffne die **Einstellungen** → **Sync**.
2. Neben **Remote-Vault** wähle **Verwalten**.
3. Neben dem Remote-Vault, den du freigeben möchtest, wähle **Freigabe verwalten** ( ![[lucide-users.svg#icon]] ).
4. Gib in **Nutzer einladen** die Mailadresse des Nutzers ein, den du einladen möchtest.
5. Bestätige mit **Hinzufügen**.

### Nutzer entfernen

1. Öffne die **Einstellungen** → **Sync**.
2. Neben **Remote-Vault** wähle **Verwalten**.
3. Klicke neben dem Nutzer, dem du die Berechtigung entziehen möchtest, auf **Nutzer entfernen** ( ![[lucide-x.svg#icon]] ).

## Zusammenarbeit mit deinem Team

### Berechtigungen

Fein abgestufte Berechtigungen werden noch nicht unterstützt. Alle Mitwirkenden erhalten dieselben Berechtigungen wie der Vault-Eigentümer, mit einer Ausnahme: Nur der Eigentümer kann Nutzer einladen.

### Live-Bearbeitung

Freigegebene Vaults ermöglichen die Zusammenarbeit an einer Reihe von Dateien. Obsidian unterstützt jedoch noch keine Live-Bearbeitung derselben Datei. Du siehst den Cursor der anderen Nutzer nicht und Änderungen erscheinen erst, wenn diese synchronisiert wurden.

Wenn mehrere Nutzer dieselbe Datei zur selben Zeit bearbeiten, werden bei der Synchronisierung die [[Obsidian Sync/Fehlerbehandlung#Auflösen von Konflikten|Änderungen zusammengeführt]]. Änderungen können über den [[Versionsverlauf]] angezeigt und zurückgesetzt werden.

![[version-history-collaboration.png]]^version-history-image

## Einschränkungen

Beachte die [[Häufig gestellte Fragen|Einschränkungen]] von Obsidian Sync, die sich auf dein Team auswirken können:

- An einem freigegebenen Vault können maximal 20 Nutzer mitwirken.
- Die maximale Dateigröße für Anhänge ist abhängig vom [[Tarife und Speicherkapazität|Tarif]], der für den Remote-Vault gilt (5 MB im Standard-Tarif und 200 MB im Plus-Tarif).

Siehe auch [[Synchronisierung für Teams]].
