---
permalink: plugins/canvas
---

Mit der [[Standarderweiterungen|Standarderweiterung]] *Canvas* kannst du Schaubilder erstellen. Das Plugin stellt dir eine unendliche Leinwand zur Verfügung, auf der du deine Notizen, Anhänge oder auch Webseiten ausbreiten und miteinander verbinden kannst.

Diese visuelle Methode kann dabei helfen, deine Aufzeichnungen besser zu verstehen, indem du sie in einem 2-dimensionalen Raum anordnest. Du kannst sie mit Linien verbinden oder verwandte Notizen gruppieren, um Beziehungen und Zusammenhänge zwischen ihnen zu erkennen und darzustellen.

> [!note]  Dateiendung .canvas
> Wenn du in Obsidian einen Canvas erstellst, wird dieser in einer `.canvas` Datei im offenen Dateiformat [JSON Canvas](https://jsoncanvas.org/) gespeichert.

## Neuen Canvas erstellen

Um *Canvas* zu verwenden, musst du als erstes eine Datei erstellen, in der deine Zeichenfläche gespeichert wird. Du kannst einen neuen Canvas wie folgt erstellen:

**Befehlspalette:**

1. Öffne die [[Befehlspalette]] ( ![[lucide-terminal.svg#icon]] ).
2. Wähle **Canvas: Neuen Canvas erstellen**, um einen Canvas im selben Ordner zu erstellen wie die aktive Notiz.

**Dateiexplorer:**

- Im [[Dateiexplorer|Dateiexplorer]] öffne mit Rechtsklick auf den Ordner, in dem du den Canvas speichern möchtest, das Kontextmenü.
- Wähle **Neuer Canvas**.

**Werkzeugleiste:**

- Wähle in der Werkzeugleiste **Neuen Canvas erstellen** ( ![[lucide-layout-dashboard.svg#icon]] ), um einen Canvas im selben Ordner zu erstellen wie die aktive Notiz.

## Karten hinzufügen

Du kannst Dateien aus Obsidian oder anderen Anwendungen auf deine Zeichenfläche ziehen, wie bspw. Markdown-Dateien, Bilder, Audiodateien, PDFs oder sogar nicht erkannte Dateitypen.

### Textkarten hinzufügen

Du kannst auch reine Textkarten zur Zeichenfläche hinzufügen, die keine Datei referenzieren. Im Text kannst du Markdown, Links oder Quellcode-Blöcke verwenden, ganz genau so wie in einer Notiz.

Um eine neue Textkarte hinzuzufügen:

- Klicke auf das Symbol für "leere Datei" am unteren Rand der Zeichenfläche.
- Oder ziehe dieses Symbol auf die Zeichenfläche.
- Oder führe einen Doppelklick auf der Zeichenfläche aus.

Um eine Textkarte in eine Datei umzuwandeln:

1. Öffne mit Rechtsklick auf die Karte das Kontextmenü.
2. Wähle **In Datei umwandeln...**.
3. Gib einen Titel für die Notiz ein und klicke **Speichern**.

> [!note] Hinweis
> Textkarten erscheinen nicht in der [[Rückverweise|Rückverweise-Ansicht]], dazu musst du sie in eine Datei umwandeln.

### Notiz als Karte hinzufügen

Um eine Notiz hinzuzufügen:

1. Klicke das Dokument-Symbol.
   Oder ziehe das Dokument-Symbol vom unteren Canvas-Rand auf die Zeichenfläche.
   Oder öffne mit Rechtsklick auf die Zeichenfläche das Kontextmenü und wähle **Notiz aus Vault hinzufügen**.
2. Wähle die Notiz, die du hinzufügen möchtest.

Du kannst eine Notiz auch direkt aus dem [[Dateiexplorer|Dateiexplorer]] auf die Zeichenfläche ziehen.

### Medien als Karte hinzufügen

Um Medien hinzuzufügen:

1. Klicke das Bild-Symbol.
   Oder ziehe das Bild-Symbol vom unteren Canvas-Rand auf die Zeichenfläche.
   Oder öffne mit Rechtsklick auf die Zeichenfläche das Kontextmenü und wähle **Medien aus Vault hinzufügen**.
2. Wähle die Mediendatei, die du hinzufügen möchtest.

Du kannst Mediendateien auch direkt aus dem [[Dateiexplorer|Dateiexplorer]] auf die Zeichenfläche ziehen.

### Webseiten als Karte hinzufügen

Um eine Webseite in den Canvas einzubetten:

1. Öffne mit Rechtsklick auf die Zeichenfläche das Kontextmenü und wähle **Webseite hinzufügen**.
2. Gib die URL der Webseite ein, die du hinzufügen möchtest und klicke **Speichern**.

Du kannst auch in deinem Browser eine URL auswählen und auf die Zeichenfläche ziehen, um sie in eine Karte einzubetten.

Um die Webseite in deinem Browser zu öffnen, drücke `Strg` (oder `Cmd` unter macOS) und klicke auf die Kartenbeschriftung. Oder öffne mit Rechtsklick das Kontextmenü und wähle **Im Browser öffnen**.

### Ordner-Inhalte als Karten hinzufügen

Ziehe einen Ordner aus dem Dateiexplorer auf die Zeichenfläche, um alle Dateien in diesem Order dem Canvas hinzuzufügen.

### Karten bearbeiten

Mit Doppelklick auf eine Karte wechselst du in den Bearbeitungsmodus. Klicke auf eine freie Fläche im Canvas oder drücke `Escape`, um die Bearbeitung zu beenden.

Du kannst auch mit Rechtsklick das Kontextmenü öffnen und **Bearbeiten** wählen.

### Karten löschen

- Wähle eine oder mehrere Karten aus und klicke **Entfernen** ( ![[lucide-trash-2.svg#icon]] ) in den Auswahlwerkzeugen oberhalb der Auswahl.
- Oder öffne mit Rechtsklick auf die Auswahl das Kontextmenü und wähle **Löschen**.
- Oder wähle eine oder mehrere Karten aus und drücke die `Rücktaste` bzw. `Entf`.

### Karten tauschen

Du kannst eine Notiz- oder Medienkarte gegen eine andere Karte vom selben Typ tauschen.

Um eine Karte zu tauschen:

1. Öffne das Kontextmenü mit Rechtsklick auf die Karte, die du ersetzen möchtest.
2. Wähle **Datei tauschen...**.
3. Wähle die Notiz bzw. Mediendatei, die du stattdessen einfügen möchtest.

## Karten auswählen

Wähle einzelne Karten aus, indem du sie anklickst. Wähle mehrere Karten aus, indem du einen Auswahlrahmen darum ziehst.

Du kannst einzelne Karten der Auswahl hinzufügen oder aus der Auswahl entfernen, indem du `Umschalt` gedrückt hältst und die Karte anklickst.

Drücke `Strg + A` (oder `Cmd + A` unter macOS), um alle Karten auszuwählen.

Um in einer Karte zu scrollen, musst du sie erst auswählen.

### Karten anordnen

Ziehe eine ausgewählte Karte, um sie zu verschieben.

Drücke `Alt` und ziehe, um eine Auswahl zu duplizieren.

Wenn du beim Ziehen `Umschalt` gedrückt hältst, kannst du die Auswahl nur in eine Richtung verschieben.

Drücke die `Leertaste` beim Verschieben, um das Einrasten temporär zu deaktivieren.

Durch Auswahl einer Karte wird diese in den Vordergrund verschoben.

### Kartengröße ändern

Ziehe eine der Kanten einer Karte, um ihre Größe zu ändern.

Drücke die `Leertaste` beim Ändern der Größe, um das Einrasten zu deaktivieren.

Drücke `Umschalt` beim Ändern der Größe, um das Seitenverhältnis beizubehalten.

## Karten verbinden

Zeichne Linien zwischen Karten, um Beziehungen zwischen ihnen herzustellen. Verwende Farben und Beschriftungen, um die Beziehungen zu beschreiben.

### Zwei Karten verbinden

Um zwei Karten mit einer direkten gerichteten Linie zu verbinden:

1. Bewege den Mauszeiger über eine der Kanten einer Karte, bis ein ausgefüllter Kreis erscheint.
2. Ziehe den Kreis zur Kante einer anderen Karte, um beide zu verbinden.

> [!tip] Tipp
> Wenn du die Linie nicht bis zu einer anderen Karte ziehst, erscheint ein Kontextmenü, über das du eine Karte oder Notiz für die Verbindung auswählen kannst.

### Verbindung zwischen zwei Karten aufheben

Um eine Verbindung zwischen zwei Karten zu lösen:

- Ziehe die Verbindungslinie von der Karte weg, ohne sie mit einer anderen zu verbinden.
- Oder rufe mit Rechtsklick auf eine Verbindungslinie das Kontextmenü auf und wähle **Entfernen**.
- Oder klicke die Linie an, um sie auszuwählen und drücke die `Rücktaste` bzw. `Entf`.

### Verbindung bearbeiten

Um eine Verbindungslinie zu bearbeiten, ziehe eine Ende der Verbindung auf ein neues Verbindungsziel.

### Über Verbindungen navigieren

Liegen zwei verbundene Karten weit voneinander entfernt, kannst du zur Quelle oder zum Ziel der Verbindung navigieren, indem du mit Rechtsklick auf die Verbindung das Kontextmenü öffnest und **Verbindung folgen** wählst.

### Verbindungen beschriften

Du kannst einer Verbindungslinie eine Beschriftung hinzufügen, um die Beziehung zwischen zwei Karten zu beschreiben.

Um eine Beschriftung hinzuzufügen oder zu bearbeiten:

- Doppelklicke auf eine Linie.
- Oder öffne mit Rechtsklick auf die Linie das Kontextmenü und wähle **Beschriftung bearbeiten**.
- Oder wähle eine Linie aus und klicke in den Auswahlwerkzeugen auf **Beschriftung bearbeiten**.

Gib einen Text ein und klicke auf einen freien Teil der Zeichenfläche, um die Bearbeitung abzuschließen.

### Farbe von Karten oder Verbindungen ändern

1. Wähle die Karte oder Verbindung, die du färben möchtest.
2. Klicke in den Auswahlwerkzeugen auf **Farbe wählen** ( ![[lucide-palette.svg#icon]] ).
3. Wähle eine Farbe.

## Karten gruppieren

Um eine leere Gruppe zu erstellen, öffne mit Rechtsklick auf die Zeichenfläche das Kontextmenü und wähle **Gruppe erstellen**.

Du kannst einer Gruppe einen Titel hinzufügen. Um den Titel zu ändern, klicke ihn doppelt an und bearbeite den Text. Drücke die `Eingabetaste` oder klicke irgendwo auf die Zeichenfläche, um die Bearbeitung abzuschließen.

### Ausgewählte Karten gruppieren

Um verwandte Karten zu gruppieren:

1. Wähle die Karten aus.
2. Öffne mit Rechtsklick auf die Auswahl das Kontextmenü und wähle **Gruppe erstellen**.

## Navigation auf dem Canvas

Ab einer gewissen Menge an Karten und Verbindungen ergibt sich gewiss die Notwendigkeit, einen bestimmten Ausschnitt der Zeichenfläche näher betrachten zu können. Erfahre, wie du den Bildausschnitt vergrößern, verkleinern und verschieben kannst.

### Canvas verschieben

Um die Zeichenfläche zu verschieben:

- Halte die `Leertaste` gedrückt, um die Zeichenfläche mit der Maus frei zu verschieben.
- Oder verschiebe die Zeichenfläche bei gedrückter mittlerer Maustaste.
- Oder scrolle mit dem Mausrad zum vertikalen Verschieben bzw. halte `Umschalt` gedrückt und scrolle zum horizontalen Verschieben.

### Ansichtsvergrößerung einstellen

Um die Ansicht zu zoomen:
- Halte die `Leertaste` bzw. `Strg` (oder `Cmd` unter macOS) und scrolle mit dem  Mausrad.
- Oder wähle **Vergrößern** ( ![[lucide-plus.svg#icon]] ) bzw. **Verkleinern** ( ![[lucide-minus.svg#icon]] ) aus der Werkzeugleiste rechts oben.

#### Ansicht einpassen

Um alle Elemente in den Bildausschnitt einzupassen, wähle **Vergrößerung anpassen** ( ![[lucide-maximize.svg#icon]] ) aus der Werkzeugleiste rechts oben. Oder verwende das Tastenkürzel `Umschalt + 1`.

#### Auswahl einpassen

Um alle ausgewählten Elemente in den Bildausschnitt einzupassen, wähle aus den Auswahlwerkzeugen bzw. aus dem Kontextmenü **Auf Auswahl zoomen**. Oder verwende das Tastenkürzel `Umschalt + 2`.

#### Ansicht zurücksetzen

Um die Vergrößerung auf den Standardwert zurückzusetzen, wähle **Vergrößerung zurücksetzen** aus der Werkzeugleiste rechts oben.

## Tipps für Fortgeschrittene

Für weitere, fortgeschrittene Anwendungsfälle haben wir ein paar kurze Videos erstellt.

Schau dir hier [alle 72 Tipps](https://obsidian.md/canvas#protips) an. Bitte beachte, dass die Videos nur auf dem Desktop angezeigt werden.
