---
permalink: bases/base-erstellen
publish: true
---

Mit [[Einführung in Bases|Bases]] kannst du datenbankähnliche Sichten auf deine Notizen erstellen. Erfahre hier, wie du eine Base erzeugst und in eine Notiz einbindest. Jede Base kann eine oder mehrere [[Sichten|Sichten]] beinhalten, um Informationen auf unterschiedliche Weise darzustellen.

## Neue Base erstellen

**Befehlspalette:**

1. Öffne die **Befehlspalette**.
2. Wähle
	- **Bases: Neue Base erstellen**, um eine Base im selben Ordner zu erstellen wie die aktive Datei.
	- **Bases: Neue Base einfügen**, um eine Base zu erstellen und in die aktive Notiz einzubetten.

**Dateiexplorer:**

- Öffne mit Rechtsklick auf den Ordner, in dem du die Base erstellen möchtest, das Kontextmenü und wähle **Neue Base**.

**Werkzeugleiste:**

- Wähle **Neue Base erstellen** aus der Werkzeugleiste, um eine Base im selben Ordner zu erstellen wie die aktive Datei.

## Base einbetten

### Base-Datei einbetten

Du kannst Base-Dateien mit Hilfe der bekannten Syntax `![[Datei.base]]` [[Dateien einbetten|in Notizen einbetten]]. Das Standard-Layout definierst du über einen Anchor Tag `![[Datei.base#Layout]]`.

### Base als Quelltext-Block einbetten

Bases können auch direkt in Notizen eingebettet werden, indem du einen `base` Quelltext-Block und die [[Bases Syntax|Bases Syntax]] verwendest. 

~~~yaml
```base
filters:
  and:
    - file.hasTag("buch")
views:
  - type: table
    name: Bücher
```
~~~

