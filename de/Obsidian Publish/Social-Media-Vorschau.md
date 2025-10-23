---
permalink: publish/social-media
publish: true
---

Viele soziale Netzwerke unterstützen eine umfangreiche Seitenvorschau, wenn jemand einen Link zu einer Webseite teilt. Mithilfe von [[Eigenschaften]] kannst du bestimmen, wie deine Webseite in dieser Seitenvorschau angezeigt wird..

> [!warning] Achtung
> Die in diesem Abschnitt beschriebenen Tags sind **nur** für Webcrawler sichtbar. Normale Webbrowser erhalten zur Optimierung der Leistung die unveränderte Seite.

## Beschreibung

Obsidian generiert automatisch eine Beschreibung basierend auf dem Inhalt der Notiz, aber du kannst eine eigene Beschreibung bereitstellen über die Eigenschaft `description`.

```yaml
---
description: Einführung in unser Sonnensystem.
---
```

> [!note] Meta-Tags
> `description` überschreibt die automatisch generierte Beschreibung in `<meta name="description" content="...">` und desgleichen in `og:description` sowie `twitter:description`.

## Bild

Du kannst ein eigenes Bild für die Seitenvorschau festlegen, indem du der Eigenschaft `image` oder `cover` den Pfad zu einer Bilddatei zuweist. Das Bild muss mit Publish hochgeladen werden. 

Der Pfad kann ein absoluter Pfad vom Stammverzeichnis deines Vaults sein:

```yaml
---
cover: "Anhänge/Titelbild.png"
---
```


Der Pfad zum Bild ist case-sensitiv. Wenn du wie im obigen Beispiel ein Bild mit dem Namen `Titelbild.png` hast, wird der untenstehende Pfad nicht funktionieren, weil die Groß-Kleinschreibung nicht beachtet wurde.

```yaml
---
cover: "Anhänge/titelbild.png"
---
```


Anstelle des absoluten Pfads in deinem Vault kannst du auch eine externe URL verwenden:

```yaml
---
image: "https://example.com/Titelbild.png"
---
```


`image` und `cover` sind aus Sicht von Obsidian Publish identisch. Verwende nur eine der beiden Eigenschaften.

> [!note] Meta-Tags
> `image` bzw. `cover` überschreibt das automatisch generierte Bild in `<meta property="og:image" content="...">`.
