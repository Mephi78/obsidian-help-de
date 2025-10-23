---
aliases:
  - Obsidian Publish/Umleitung alter Notizen
permalink: publish/permalinks
publish: true
---

Du kannst die URL für deine Notizen umbenennen mit *Permalinks*.

Bspw. kannst du diesen Link umwandeln:

```
https://publish.obsidian.md/benutzer/Unternehmen/%C3%9Cber+uns
```

...in diesen:

```
https://publish.obsidian.md/benutzer/ueber
```

Um einen Permalink für eine Notiz zu erstellen, füge die [[Eigenschaften|Eigenschaft]] `permalink` hinzu.

```yaml
---
permalink: ueber
---
```

Wenn jemand die Seite über die ursprüngliche URL aufruft, wird er automatisch umgeleitet auf den Permalink.

## Alte Notizen umleiten

Das Umbenennen und Entfernen von Notizen ist natürlicher Bestandteil der Pflege eines aktiven Vaults. Doch während Obsidian interne Links automatisch aktualisiert, wenn du eine Notiz innerhalb deines Vaults verschiebst, können andere Webseiten weiterhin auf deine alten [[Einführung in Obsidian Publish|veröffentlichten]] Notizen verweisen. Du kannst deine Leser von einer Notiz auf eine andere umleiten.

Stell dir vor, du möchtest eine Notiz von einem Ordner in einen anderen verschieben:

- **Anleitungen**
  - ~~Freunde finden.md~~ (gelöscht)
- **Tutorials**
  - *Wie man Freunde findet.md* (hinzugefügt)

Wenn du die Notiz verschiebst, aktualisiert Obsidian automatisch alle Links in deinem Vault. Wenn du die Änderung veröffentlichst, werden jedoch alle Links nach `/Anleitungen/Freunde+finden` einen 404-Fehler erzeugen.

Um deine Leser von `/Anleitungen/Freunde+finden` nach `/Tutorials/Wie+man+Freunde+findet` umzuleiten, musst du der Notiz `Wie man Freunde findet.md`, auf die du umleiten möchtest, einen [[Aliasse|Alias]] hinzufügen.

```md
---
alias: Anleitungen/Freunde finden
---

# Wie man Freunde findet
```

> [!important] Wichtig
> Stelle sicher, dass du den vollständigen Pfad zur alten Notiz im Alias angibst. Die Kurzschreibweise ohne den Ordner-Pfad funktioniert nur innerhalb deines lokalen Vaults, Obsidian Publish benötigt für eine erfolgreiche Weiterleitung den vollständigen Pfad.

Du kannst mehrere alte Pfade auf die neue Notiz umleiten, indem du für jede einen Alias hinzufügst.

```md
---
aliases: 
  - Anleitungen/Freunde finden
  - Freundschaften entwickeln
---

# Wie man Freunde findet
```