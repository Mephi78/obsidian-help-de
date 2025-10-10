---
permalink: bases/sichten/landkarte
---

Die Landkarten-Sicht zeigt Dateien in einer [[Einführung in Bases|Base]] als interaktive Karte mit Stecknadel-Markierungen für jede Datei und einer Vorschau mit den Eigenschaften dieser Datei.

![[bases-map-places.png#interface]]

> [!info] Erfordert Obsidian 1.10 und das *Maps* Plugin
> Das [Maps Plugin](https://github.com/obsidianmd/obsidian-maps) ist eine offizielle [[Externe Erweiterungen|Community-Erweiterung]], die du separat installieren musst.

## Anwendungsfall

Erstelle zunächst eine Notiz mit dem Namen **Eiffelturm** und kopiere folgende Eigenschaften hinein:

```yaml
---
koordinaten:
  - "48.85837"
  - "2.294481"
icon: "landmark"
farbe: "red"
tags:
  - orte
---
```

| Eigenschaft   | Wert                     | Beschreibung                                                                                                                                                                            |
| ------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `koordinaten` | `48.85837`<br>`2.294481` | Koordinaten werden im Format `breitengrad, längengrad` gespeichert. Mit Rechtsklick auf die Karte und **Copy coordinates** kannst du die Koordinaten von einem bestimmten Ort erhalten. |
| `icon`        | `landmark`               | Name eines Icons aus der [Lucide Bibliothek](https://lucide.dev/).                                                                                                                      |
| `farbe`       | `red`                    | Gültiger CSS-Farbwert: Hex, RGB, Farbname etc.                                                                                                                                          |
| `tags`        | `orte`                   | Diesen Tag verwenden wir, um Kartenmarker in unseren Notizen zu finden.                                                                                                                 |

Erstelle nun eine Landkarten-Sicht mit einem Filter für den Tag `orte` und setze Koordinaten, Icon und Farbe auf die Eigenschaften wie im Beispiel oben.

Du kannst auch diese [Beispieldateien](https://github.com/obsidianmd/obsidian-maps/tree/master/examples) in Obsidian öffnen, um eine lauffähige Landkarten-Sicht mit bereits vorkonfigurierten Koordinaten, Icons und Farben zu sehen.

## Einstellungen

Die Landkarten-Sicht kann über die [[Sichten#Sicht-Einstellungen|Sicht-Einstellungen]] konfiguriert werden.

### Markierungen

#### Koordinaten

Um Stecknadel-Markierungen auf der Landkarte anzuzeigen, öffne die [[Sichten#Sicht-Einstellungen|Sicht-Einstellungen]] und wähle eine Eigenschaft für die **marker coordinates** aus. Die Eigenschaft muss Breiten- und Längengrad bereitstellen. Du kannst zwischen zwei Formaten wählen:

```yaml
# Text-Eigenschaft
coordinates: "breite, länge"

# Listen-Eigenschaft
coordinates:
  - "breite"
  - "länge"
```

Falls du die Koordinaten als separate Eigenschaften `breite` und `länge` gespeichert hast, kannst du sie in einer [[Bases Syntax#Formeln|Formel]] kombinieren (`[breite, länge]`) und diese als Eigenschaft für die Markierungen verwenden.

#### Icons

Definiere eine Eigenschaft für **marker icons**, um der Markierung als Icon anzuzeigen. Bspw. kannst du deinen Notizen eine Eigenschaft `icon` hinzufügen, die als Wert `landmark` oder `utensils` oder einen anderen gültigen Namen für ein [Lucide Icon](https://lucide.dev/icons/) enthält.

##### Formel für Icons verwenden

Wenn du bspw. möchtest, dass alle Restaurants auf der Karte mit demselben Symbol markiert sind:

1. Erstelle eine Notiz **Restaurants** und füge eine Eigenschaft `icon` mit dem Wert `utensils` hinzu. 
2. Gibt Restaurant-Notizen eine Eigenschaft `kategorie` mit dem Wert `[[Restaurants]]` note.
3. Füge deiner Base eine Formel-Eigenschaft `kategorie icon` und den folgenden Code:
	```js
	list(kategorie)[0].asFile().properties.icon
	```
4. Wähle `kategorie icon` als Marker in den Sicht-Einstellungen.

Voilà! Nun sind in deiner Karte alle Orte mit einem Symbol für die *kategorie* markiert, nicht für den Ort selbst.

#### Farben

Du kannst die Farbe der Marker definieren mit RGB-Werten `rgb(0,0,0)`, HEX-Werten `#000` oder CSS-Variablen, wie `var(--color-blue)`. Du kannst auch hierfür eine Formel-Eigenschaft verwenden, wie im Beispiel oben.

### Hintergrund

#### Kartenkacheln

Kartenkacheln sind eine gängige Methode, um digitale Karten anzuzeigen. Es gibt verschiedene Dienste, die du verwenden kannst, um Karten mit deinen eigenen Stilen, Farben und Schriftarten anzupassen. *Maps* unterstützt Raster- und Vektor-Dateien und akzeptiert die meisten Kachel-URLs, auch TileJSON URLs.

[OpenFreeMap](https://openfreemap.org/) bietet einige Stile, die du kostenlos verwenden kannst. Versuche einmal, eine der folgenden URLs in der **Map tiles**-Einstellung zu verwenden:

| Name     | URL                                              |
| -------- | ------------------------------------------------ |
| Dark     | `https://tiles.openfreemap.org/styles/dark`      |
| Positron | `https://tiles.openfreemap.org/styles/positron`  |
| Liberty  | `https://tiles.openfreemap.org/styles/liberty` |

#### Ressourcen

- [Maputnik](https://maputnik.github.io/) zum Anpassen von Kartenkacheln.
- [Protomaps](https://protomaps.com/) zum Selbst-Hosten von Kartenkacheln.
- Weitere kostenlose Dienste sind [MapTiler](https://www.maptiler.com/) und [Mapbox](https://www.mapbox.com/).