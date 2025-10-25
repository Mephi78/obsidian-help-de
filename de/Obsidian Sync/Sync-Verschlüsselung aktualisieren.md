---
cssclasses:
  - soft-embed
description: Verschiebe deinen Vault in eine andere Region und aktualisiere die Verschlüsselung.
mobile: true
permalink: sync/verschluesselung
publish: true
aliases:
  - Migrationsassistent
---

Standartmäßig verwendet Obsidian Sync eine [[Obsidian Sync/Sicherheit und Datenschutz#Verschlüsselung|Ende-zu-Ende-Verschlüsselung]] für deine gesamten Daten. Damit wird garantiert, dass niemand - nicht einmal das Obsidian-Team - Zugriff auf deine Notizen erhält.

Obsidian aktualisiert die Verschlüsselung regelmäßig, um die höchsten [[Obsidian Sync/Sicherheit und Datenschutz|Sicherheitsstandards]] zu gewährleisten. Wenn eine Verschlüsselungsaktualisierung verfügbar ist, wird dir die Option **Vault-Verschlüsselung aktualisieren** angezeigt in **Einstellungen → Sync**. Auf diesem Zusammenhang kannst du auch deine [[Sync-Regionen|Sync-Region]] ändern.

## Verschlüsselungsversionen

Jeder neue Vault verwendet automatisch die aktuellste Verschlüsselung. Bestehende Vaults können aktualisiert werden mit dem Migrationsassistenten. Beachte, dass alle verbundenen Geräte eine Obsidian-Version verwenden müssen, die dieselbe Sync-Verschlüsselungsversion unterstützt, auf die du den Remote-Vault aktualisieren möchtest.

| Release-Datum                                                           | Sync Version | Obsidian Mindestversion |
| ----------------------------------------------------------------------- | ------------ | ----------------------- |
| [2025-08-22](https://obsidian.md/changelog/2025-08-22-sync/)            | 3            | 1.8.3                   |
| [2020-12-07](https://obsidian.md/changelog/2020-12-07-desktop-v0.9.21/) | 0            | 0.9.21                  |

## Verschlüsselung mit dem Migrationsassistenten aktualisieren

Bevor du fortfährst, [[Sichere deinen Vault]], um mögliche Datenverluste zu vermeiden. Dieses Verfahren wird alle Daten in deinem Remote-Vault mit der alten Verschlüsselung endgültig löschen, auch den Versionsverlauf.

> [!danger] Migrationen sind destruktiv
> 
> **[[Sichere deinen Vault]] immer, bevor du mit der Migration fortfährst.**
> 
> Wenn du einen Remote-Vault migrierst, werden deine Daten ersetzt. Das bedeutet:
> 
> 1. Remote-Daten werden vom Obsidian-Server gelöscht und dein lokaler Vault wird an seiner Stelle neu hochgeladen.
> 2. [[Versionsverlauf]] für diesen Vault wird endgültig gelöscht.

1. Öffne **Einstellungen** → **Sync**.
2. Wähle **Vault aktualisieren**. Diese Option wird nur angezeigt, wenn eine Aktualisierung für deinen Remote-Vault verfügbar ist.
3. Überprüfe noch einmal dein Backup und klicke dann auf **Fortsetzen**.
4. Gib in **Vault-Name** den Namen des zu aktualisierenden Remote-Vaults ein.
5. Wähle unter **Region** deine [[#Regional sync servers|Server-Region]] für den aktualisierten Remote-Vault. ==An dieser Stelle kannst du bei Bedarf von der vorherigen auf eine neue Region wechseln.== 
6. Gib in **Passwort für Verschlüsselung** ein neues Verschlüsselungspasswort für deinen Vault ein. Damit wird die Ende-zu-Ende-Verschlüsselung für den Vault aktiviert. Das Verschlüsselungspasswort ist unabhängig von deinem Obsidian-Nutzerkonto und kann für jeden Vault unterschiedlich sein. Für mehr Informationen, siehe [[Obsidian Sync/Sicherheit und Datenschutz]].
7. Nachdem der Migrationsassistent deinen Remote-Vault aktualisiert und deine Daten mit der neuen Verschlüsselung versehen hat, verbinde dich auf allen anderen Geräten neu mit dem Remote-Vault.