---
aliases:
  - Gewusst wie/Arbeiten mit Tags
permalink: tags
---

Tags sind Stichwörter oder Themen, mit denen du Notizen schneller finden kannst.

## Notiz mit einem Tag versehen

Um einen Tag zu erstellen, gib im Bearbeitungsmodus an einer beliebigen Stelle in deiner Notiz ein Hash-Symbol (`#`) ein, gefolgt von einem Stichwort (z.B. `#wichtig`).

Du kannst Tags auch über die vordefinierte [[Eigenschaften|Eigenschaft]] `tags` hinzufügen. Achte hierbei darauf, das Hash-Symbol wegzulassen. Tags im YAML-Block sollten immer als Liste formatiert sein:

```yaml
---
tags:
  - wichtig
  - termin
---
```

## Notizen über Tags finden

Um Notizen über die [[Search|Suchfunktion]] zu finden, kannst du den [[Search#Search operators|Suchoperator]] `tag` in deiner Suchanfrage verwenden (z.B. `tag:wichtig`).

Du kannst auch alle Notizen mit einem bestimmten Tag finden, indem du auf diesen Tag klickst in einer deiner Notizen.

Um Notizen anhand der [[Tags view|Tag-Übersicht]] zu finden, wähle **Tags: Tag-Übersicht anzeigen** aus der [[Befehlspalette|Befehlspalette]]. Klicke anschließend in der Tag-Übersicht auf den Tag, nach dem du suchen möchtest.

## Verschachtelte Tags

Verschachtelte Tags definieren Tag-Hierarchien, die eine Suche oder das Filtern nach verwandten Tags vereinfachen.

Erstelle verschachtelte Tags, indem du Tag-Ebenen mit einem Schrägstrich (`/`) voneinander trennst, bspw. `#posteingang/ungelesen` und `#posteingang/in_bearbeitung`.

Sowohl die [[Search|Suchfunktion]], als auch die [[Tags view|Tag-Übersicht]] unterstützen verschachtelte Tags.

## Regeln für Tag-Namen

Folgende Zeichen kannst du in Tag-Namen verwenden:

- Buchstaben
- Zahlen
- Unterstrich (`_`)
- Bindestrich (`-`)
- Schrägstrich (`/`) für [[#Verschachtelte Tags]]

Tag-Namen müssen mindestens ein nicht numerisches Zeichen enthalten. #1984 ist bspw. kein gültiger Tag, #j1984 hingegen schon.

Die Groß-/Kleinschreibung spielt bei Tags keine Rolle. Beispielsweise werden #tag und #TAG als identisch angesehen.

> [!note] Hinweis
> Tags werden in der [[Tags view|Tag-Übersicht]] mit der Schreibweise angezeigt, die du verwendet hast bei der ersten Erstellung eines Tags. Wurde z.B. zuerst #Tag und danach noch #TAG verwendet, werden beide Vorkommen als #Tag angezeigt.

Tag-Namen können keine Leerzeichen enthalten. Um Tags aus mehreren Wörtern besser lesbar zu gestalten, kannst du stattdessen eines der folgenden Formate verwenden:

- #camelCase
- #PascalCase
- #snake_case
- #kebab-case
