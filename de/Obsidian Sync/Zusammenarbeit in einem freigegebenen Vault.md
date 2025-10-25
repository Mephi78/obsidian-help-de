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
#WIP
[[Einführung in Obsidian Sync|Obsidian Sync]] ermöglicht die Zusammenarbeit mit deinem Team in einem freigegebenen Vault.

Alle Mitwirkenden müssen ein aktives Sync-Abo besitzen, um auf einen freigegebenen Vault zugreifen zu können. Die Mitarbeit an von anderen Nutzern freigegeben Vaults wird nicht auf dein [[Frequently asked questions#How many remote vaults can I have?|Vault-Limit]] angerechnet.

Wenn der Remote-Vault [[Obsidian Sync/Sicherheit und Datenschutz|verschlüsselt]] ist, müssen Mitwirkende das Passwort für die Verschlüsselung eingeben, wenn sie den Vault lokal einrichten.

## Manage users

### Add users

To invite a user to share a remote vault:

1. Open **Settings**.
2. In the side menu, select **Sync**.
3. Next to **Remote vault**, select **Manage**.
4. Next to the remote vault you want to share, select **Manage sharing** ( ![[lucide-users.svg#icon]] ).
5. In **Invite user**, enter the email of the user you want to invite.
6. Select **Add**.

### Remove users

1. Open **Settings**.
2. In the side menu, select **Sync**.
3. Next to **Remote vault**, select **Manage**.
4. Next to the user you want to remove access from, select **Remove user** ( ![[lucide-x.svg#icon]] ).

## Collaborate with your team

### Permissions

Fine-grained permissions are not supported yet. All collaborators receive the same permissions as the vault owner, with one exception: only the vault owner can invite collaborators.

### Live editing

Shared vaults allow teams to work together on a set of files, however Obsidian does not yet support collaborative live editing on the same file. You will not see the other user's cursor, and their edits will only appear once the changes are synced.

If multiple users are editing the same file at the same time, [[Obsidian Sync/Fehlerbehandlung#Conflict resolution|changes will be merged]] during the syncing process. Changes can be viewed and restored using [[Versionsverlauf]].

![[version-history-collaboration.png]]^version-history-image

## Limitations

Be aware that Obsidian Sync has [[Frequently asked questions|Limitations]] that may affect your team:

- The maximum number of collaborators on a shared vault is 20 users.
- The maximum file size for attachments depends on the [[Tarife und Speicherkapazität|plan]] of your remote vault host, with 5 MB for the Standard Plan and 200 MB for the Plus Plan.

Learn more about [[Synchronisierung für Teams]].
