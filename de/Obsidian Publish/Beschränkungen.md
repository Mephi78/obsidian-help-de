---
permalink: publish/beschraenkungen
publish: true
---

> [!tip] Unsere großartige Community hat zu einigen hier benannten Einschränkungen Umgehungslösungen entwickelt. Erfahre mehr darüber im unserem Forum unter [Publish Resources](https://forum.obsidian.md/t/obsidian-publish-resources/74582).

## Community-Erweiterungen

Obsidian Publish unterstützt in einem gewissen Maße auch [[Externe Erweiterungen]]. 

Erweiterungen, die reines Markdown erzeugen - bspw. das *Waypoint*-Plugin - sind mit Obsidian Publish kompatibel, da das Plugin selbst zum Rendern der Daten nicht benötigt wird.

Erweiterungen hingegen, die zum Rendern spezifische Plugin-Codeblöcke benötigen - *Dataview* oder *Fantasy Statblocks* zum Beispiel - funktionieren nicht standardmäßig in Obsidian Publish.

## Graph-Ansicht

Publish unterstützt benutzerdefinierte Farben für die Graph-Ansicht über CSS. Du kannst die Farben der Knoten in der Datei `publish.css` anpassen über die [CSS-Variablen für die Graph-Ansicht](https://docs.obsidian.md/Reference/CSS+variables/Plugins/Graph).

Beachte, dass der veröffentlichte Graph die umfassenden Sortier- und Anzeigeoptionen der [[Graph-Ansicht]], die dir in der Grundanwendung zur Verfügung stehen, nicht unterstützt.

## Mediendateien

Obsidian Publish ist nicht für Video-Streaming oder große Audiodateien ausgelegt. Erfahre mehr über den optimalen Umgang mit Medien in deinen Notizen im Abschnitt [[Mediendateien]]. 

Für das beste Benutzererlebnis empfehlen wir stattdessen die Verwendung von Video-Hosting-Diensten, wie Youtube oder Vimeo.

Mit Obsidian Publish kannst du Dateien mit einer Größe von **bis zu 50 MB** hochladen. ^publish-media-limit

## PDFs

Auf Mobilgeräten, Tablets oder Computern mit kleinen Bildschirmen kann es vorkommen, dass eingebettete PDFs nicht geladen werden oder nur die erste Seite angezeigt wird. Dies hängt mit den Einschränkungen des PDF-Renderers auf Mobilgeräten zusammen.

Für Inhalte, die auf Mobil-Anwender ausgerichtet sind, empfehlen wir die Verwendung von Links zu extern gehosteten PDFs oder von internen Links, über die das PDF direkt heruntergeladen werden kann.

## Suche

Obsidian bietet grundlegende Unterstützung für die reine Text-Suche in deiner Publish-Webseite.
Die Suchergebnisse berücksichtigen dabei bevorzugt folgende Elemente:

- Dateinamen
- Aliasse
- Überschriften

Nachrangig werden die Textinhalte der veröffentlichten Notizen durchsucht.

Daher kannst du die Durchsuchbarkeit deiner mit Publish veröffentlichten Webseite optimieren, indem du beschreibende Dateinamen, mehrere Aliasse und Überschriften verwendest, die treffend den Inhalt widerspiegeln.

[[Suche#Suchergebnisse in Notiz einbinden|Eingebettete Suchergebnisse]] werden von Obsidian Publish derzeit nicht unterstützt.

