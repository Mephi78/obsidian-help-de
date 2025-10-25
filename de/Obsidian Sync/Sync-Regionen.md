---
cssclasses:
  - soft-embed
description: Erfahre, wie du deinen Remote-Vault in eine andere Region verschiebst.
mobile: true
permalink: sync/region
publish: true
---

Beim Erstellen eines [[Lokale und Remote-Vaults|Remote-Vaults]] mit [[Einführung in Obsidian Sync|Obsidian Sync]] werden deine Daten verschlüsselt und auf einem von Obsidian's regionalen Sync-Servern gespeichert. Hier erfährst du, wie du deinen Remote-Vault auf einen anderen regionalen Server verschieben kannst.

## Verfügbare Regionen

Folgende Regionen sind verfügbar für Obsidian Sync. Wir empfehlen die Region **Automatisch** ermitteln zu lassen oder eine Region in deiner Nähe zu wählen, um die Ladezeiten zu verringern und den Sync-Prozess zu beschleunigen.

![[Obsidian Sync/Sicherheit und Datenschutz#^sync-geo-regions]]

## Sync-Region wechseln

Um die Region für deinen Remote-Vault zu ändern, musst du ihn auf einem anderen Sync-Server neu erstellen. Du kannst die Region übrigens auch mit dem Migrationsassistenten für die [[Sync-Verschlüsselung aktualisieren|Sync-Verschlüsselungsaktualisierung]] ändern, wenn dein Vault auf einem älteren Versionsstand ist.

> [!danger] Migrationen sind destruktiv
> 
> **[[Sichere deinen Vault]] immer, bevor du mit der Migration fortfährst.**
> 
> Wenn du einen Remote-Vault migrierst, werden deine Daten ersetzt. Das bedeutet:
> 
> 1. Remote-Daten werden vom Obsidian-Server gelöscht und dein lokaler Vault wird an seiner Stelle neu hochgeladen.
> 2. [[Versionsverlauf]] für diesen Vault wird endgültig gelöscht.

![[Obsidian Sync einrichten#Verbindung zu Remote-Vault trennen]]

Falls du den [[Tarife und Speicherkapazität|Standard-Tarif]] abonniert hast, musst du vor dem nächsten Schritt auch den [[#Delete a remote vault|Remote-Vault löschen]].

![[Obsidian Sync einrichten#Neuen Remote-Vault erstellen]]

Zudem kannst du den alten [[#Delete a remote vault|Remote-Vault löschen]], sobald du die Umstellung auf den neuen Remote-Vault und die neue Region bestätigt hast.
