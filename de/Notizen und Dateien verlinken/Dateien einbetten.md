---
aliases:
  - Gewusst wie/Dateien einbetten
cssclasses:
  - soft-embed
permalink: einbetten
---

Erfahre, wie du andere Notizen oder Medien in deine Notizen einbetten kannst. Das Einbetten von Dateien in deine Notizen macht Inhalte über den gesamten Vault hinweg wiederverwendbar.

Um eine Datei einzubetten, setze einem [[Interne Links|internen Link]] ein Ausrufezeichen (`!`) voran. Du kannst Dateien in jedem [[Dateiformate|unterstützten Format]] einbetten.

> [!tip] Einbetten mittels Drag & Drop
> Auf dem ![[lucide-monitor-check.svg#icon]] Desktop kannst du unterstützte Dateien auch per Drag & Drop direkt in deine Notiz ziehen, um sie automatisch einzubetten.

## Andere Notiz einbetten

So bettest du eine Notiz ein:

```md
![[Interne Links]]
```

Du kannst auch nur einen Abschnitt einer Notiz einbetten, indem du als Link-Ziel eine [[Interne Links#Sprungmarken erstellen|Überschrift]] oder einen [[Interne Links#Block in einer Notiz verlinken|Block]] wählst.

```md
![[Intere Links#^b15695]]
```

Hier ein Beispiel für einen eingebetteten Block:

![[Interne Links#^b15695]]

## Bilder einbetten

Ein Bild kannst du so einbetten:

```md
![[Engelbart.jpg]]
```

![[Engelbart.jpg#outline]]

Die Bildgröße änderst du mit dem Zusatz `|640x480` im Link. Dabei ist 640 die Breite und 480 die Höhe.

```md
![[Engelbart.jpg|100x145]]
```

Wenn du nur die Breite angibst, wird das Bild entsprechend im richtigen Verhältnis skaliert, z.B. `![[Engelbart.jpg|100]]`.

![[Engelbart.jpg#outline|100]]

Du kannst auch ein extern gehostetes Bild einbinden mit Hilfe eines Markdown-Links. Die Bildgröße lässt sich dabei auf dieselbe Weise kontrolieren wie beim Wiki-Link.

```md
![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)
```

![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)

## Audiodateien einbetten

Bette eine Audiodatei wie folgt ein:

```md
![[Excerpt from Mother of All Demos (1968).ogg]]
```

![[Excerpt from Mother of All Demos (1968).ogg]]

## PDFs einbetten

PDFs lassen sich so einbetten:

```md
![[Document.pdf]]
```

Du kannst auch eine bestimmte Seite in der PDF-Datei öffnen, indem du `#page=N` an den Ziel-Link anhängst, wobei `N` durch die Seitenzahl zu ersetzen ist:

```md
![[Document.pdf#page=3]]
```

Und du kannst die Höhe in Pixel festlegen für den eingebetteten PDF-Viewer mit `#height=N` :

```md
![[Document.pdf#height=400]]
```

## Listen einbetten

Um eine Liste aus einer anderen Notiz einzubetten, füge der Liste zunächst einen [[Interne Links#Block in einer Notiz verlinken|Blockbezeichner]] hinzu:

```md

- list item 1
- list item 2

^meine-listen-id
```

Anschließend kannst du die Liste über ihren Blockbezeichner verlinken:

```md
![[Meine Notiz#^meine-listen-id]]
```

## Suchergebnisse einbetten

![[Suche#Suchergebnisse in Notiz einbinden]]
