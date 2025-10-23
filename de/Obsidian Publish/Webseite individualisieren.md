---
aliases:
  - Obsidian Publish/Webseite anpassen
description: Erfahre, wie du das Aussehen deiner Obsidian Publish-Webseite anpassen kannst.
permalink: publish/individualisieren
publish: true
---

Individualisiere deine [[Einführung in Obsidian Publish|Obsidian Publish]]-Webseite, indem du die Darstellung anpasst.

## Statische Assets

Gestalte deine Webseite, indem du folgende Dateien [[Inhalte veröffentlichen#Notizen veröffentlichen|veröffentlichst]]:

- `publish.css` für benutzerdefiniertes CSS
- `publish.js` für eigenes JavaScript
- `favicon-32x32.png` um ein Favicon zu definieren

**Hinweise:**

- CSS-Variablen für Publish findest du in der [Entwickler-Dokumentation](https://docs.obsidian.md/Reference/CSS+variables/Publish/Publish)
- Um die CSS- und JavaScript-Dateien zu bearbeiten, benötigst du eine andere Anwendung, da Obsidian diese Dateiformate nicht unterstützt.
- Sowohl `publish.css`, als auch `publish.js` müssen im Stammordner (`/`) deines Vaults gespeichert werden.
- Standardmäßig werden `publish.css` und `publish.js` im Dateiexplorer nicht angezeigt, dennoch kannst du sie über den **Publish**-Dialog veröffentlichen.
- Um JavaScript über `publish.js` zu verwenden, benötigst du eine [[Eigene Domain]].

Obsidian erwartet folgende Namenskonventionen für Favicons, wobei `32` die Icon-Größe in Pixel angibt:

- `favicon-32.png`
- `favicon-32x32.png`
- `favicon.ico`

Wir empfehlen, ein oder mehrere der folgenden Formate bereitzustellen:

- `favicon-32x32.png`
- `favicon-128x128.png`
- `favicon-152x152.png`
- `favicon-167x167.png`
- `favicon-180x180.png`
- `favicon-192x192.png`
- `favicon-196x196.png`

Du kannst die Favicons unter einem beliebigen Pfad in deinem Vault speichern, sie müssen lediglich mit veröffentlicht werden.

## Community-Thema anwenden

Um eines der [[Themen|Community-Themen]] für deine Webseite zu verwenden:

1. Öffne deinen Vault im Dateiexplorer deines Betriebssystems.
2. Im Konfigurationsordner (standardmäßig `.obsidian`) öffne den Ordner `themes`.
3. Kopiere die Datei `theme.css` aus dem Thema, das du für deine Webseite verwenden möchtest ins Stammverzeichnis deines Vaults.
4. Benenne die Datei um in `publish.css`.
5. [[Inhalte veröffentlichen#Notizen veröffentlichen|Veröffentliche]] `publish.css`.

**Hinweise:**

- Falls der Stil nicht innerhalb weniger Minuten aktualisiert wird, versuche den Browser-Cache zu leeren.
- Du kannst zwischen hellem und dunklem Modus umschalten in den [[Webseiten verwalten#Webseiten-Einstellungen|Seiteneinstellungen]].
- Viele Community-Themen verwenden das **Style Settings**-Plugin für benutzerdefinierte Anpassungen, allerdings funktionieren diese nicht in Obsidian Publish.

> [!tip] Themen entwickeln
> Du findest kein passendes Thema für deine Webseite? Erfahre, wie du selbst ein [Thema erstellen](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/Build+a+Publish+theme) kannst.

## UI-Funktionen aktivieren

Du kannst verschiedene UI-Funktionen für deine Webseite aktivieren, wie die Graph-Ansicht oder die Gliederung.

Eine Liste aller verfügbaren UI-Funktionen findest du im Abschnitt [[Webseiten verwalten#Lese-Erlebnis|Seiteneinstellungen]].

### Navigation anpassen

In Obsidian Publish kannst du die Anzeigereihenfolge von Dateien und Ordnern im Publish-[[Dateiexplorer]] anpassen. Navigationselemente werden standardmäßig in der Reihenfolge ihrer Veröffentlichung aufgelistet. Nicht veröffentlichte Notizen werden in diesem Fenster nicht angezeigt.

#### Zugriff auf Navigations-Optionen

1. Wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ) aus der [[Werkzeugleiste]] oder über die [[Befehlspalette]].
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. In den **Komponenten**-Einstellungen neben **Navigation anpassen** wähle **Verwalten**, um den Dialog **Navigation** zu öffnen.

#### Navigationselemente anpassen

Im Abschnitt **Navigationsvorschau** kannst du die Anzeigereihenfolge deiner veröffentlichten Inhalte bearbeiten.

1. Wähle den Ordner oder die Notiz, die du anpassen möchtest.
2. Ziehe den Ordner bzw. die Notiz an die gewünschte Stelle.
3. Rechts unten im **Navigation**-Dialog wähle **Fertig**. 

Obsidian Publish wird deine Webseite entsprechend aktualisieren. 

#### Navigationselemente ein-/ausblenden

Falls du Ordner oder Notizen veröffentlicht hast, die nicht in der Navigation angezeigt werden sollen, kannst du diese ausblenden.

1. Wähle den Ordner oder die Notiz, die du anpassen möchtest.
2. Öffne mit Rechtsklick das Kontextmenü und wähle **In Navigation ausblenden**. Das Element sollte aus der **Navigationsvorschau** verschwinden.
3. Rechts unten im **Navigation**-Dialog wähle **Fertig**. 

Obsidian Publish wird deine Webseite entsprechend aktualisieren.  

> [!tip] Über die Checkbox rechts oben im **Navigation**-Dialog kannst du **Ausgeblendete** Elemente **anzeigen** lassen.

## Häufig gestellte Fragen

**Kann ich in der Navigation Dateien von einem Ordner in einen anderen verschieben?**

Nein. Die Zugehörigkeit von Elementen zu Ordnern muss beibehalten werden. Du kannst die Anzeigereihenfolge von Elementen - Notizen wie Ordner - innerhalb eines Ordners (einschließlich Stammordner) anpassen.

**Kann ich die Reihenfolge mehrerer Notizen und Ordner in einem Bearbeitungsvorgang ändern?**

Ja.

**Wie kann ich die Änderungen rückgängig machen?**

- **Anzeigereihenfolge**: Wähle **Standard wiederherstellen** ( ![[lucide-rotate-ccw.svg#icon]] ) neben **Reihenfolge der angezeigten Navigationselemente**, um die alphabetische Reihenfolge wiederherzustellen.
- **Anzeigestatus**: Wähle **Standard wiederherstellen** ( ![[lucide-rotate-ccw.svg#icon]] ) neben **Blende Seiten oder Ordner in der Navigation aus**, um alle Elemente wieder einzublenden.
