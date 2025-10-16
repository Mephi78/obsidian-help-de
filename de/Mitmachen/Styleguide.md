---
aliases:
  - Obsidian Stil-Leitfaden
description: Erfahre mehr über Stilrichtlinien für die Erstellung unserer Dokumentation.
publish: true
mobile: true
permalink: styleguide
---

Die Obsidian-Dokumentation richtet sich nach dem [Google-Dokumentationsleitfaden](https://developers.google.com/style). Für Themen, die du im Google-Leitfaden nicht findest, verwende bitte den [Microsoft Styleguide](https://learn.microsoft.com/en-us/style-guide/).

Im Folgenden sind alle Abweichungen vom Google-Leitfaden sowie besonders hervorzuhebende Begriffe aufgeführt.

> [!tip] Mitmachen
> Ein Großteil unserer Dokumentation existiert bereits länger als der Styleguide. Falls du also Abweichungen davon findest, erstelle gern ein [Issue](https://github.com/obsidianmd/obsidian-docs/issues/new) oder sende einen Pull Request an [obsidianmd/obsidian-docs](https://github.com/obsidianmd/obsidian-docs).

> [!hint] Hinweis
> Bitte lies die [englische Version](https://help.obsidian.md/style-guide) dieser Seite, wenn du an der englischen Obsidian-Dokumentation mitarbeiten möchtest. Hier sind hauptsächlich Hinweise und einige Besonderheiten aufgeführt, die für die deutschsprachige Übersetzung relevant erscheinen.

## Sprachstil

In unserer Englischen Dokumentation bevorzugen wir [Globales Englisch](https://docs.openedx.org/en/latest/documentors/references/doc_english_writing.html), um Obsidian-Anwender aus aller Welt besser anzusprechen.

Für die deutsche Übersetzung verwende bitte Hochdeutsch.

### Begriffe

- Verwende "Obsidian App" für die ![[obsidian-icon-smartphone.svg#icon]] mobile Version und "Obsidian Anwendung", wenn du dich auf die ![[lucide-monitor-check.svg#icon]] Desktop-Variante beziehst.
- Verwende lieber "Maximal-" bzw. "Mindest-", anstatt der Abkürzungen "max." und "min.".

### Produktnamen

Obsidian Produktnamen beginnen mit "Obsidian", z.B. "Obsidian Publish" oder "Obsidian Sync".

Um häufige Wiederholungen innerhalb eines Absatzes zu vermeiden, kannst du in Folgeerwähnungen die Kurzform verwenden.

**Beispiel**: *Um eine gerätespezifische Konfiguration zu ermöglichen, synchronisiert Obsidian Sync seine eigenen Einstellungen nicht. Sync muss daher für jedes Gerät separat konfiguriert werden.*

### Bedienoberfläche und Interaktion

- Verwende **Fettdruck**, um Schaltflächentexte hervorzuheben.
- Verwende "wähle" anstelle von "tippe" oder "klicke".
- Verwende "ausführen" anstelle von "aufrufen", wenn du dich auf Befehle oder Aktionen beziehst.
- Verwende das Symbol → (U+2192), wenn du mehrere Bedien-Interaktionen in einer Sequenz aufzählst, z.B. "**Einstellungen → Externe Erweiterungen**".

### Notizen, Dateien und Ordner

- Verwende "Notiz" für Markdown-Dateien im Vault.
- Verwende "Datei" für Dateien mit anderen Formaten als Markdown.
- Verwende lieber "Notizname" als "Notiztitel".
- Verwende lieber "aktive Notiz" als "aktuelle Notiz".
- Verwende lieber "Ordner" als "Verzeichnis".

### Beispiele

Verwende realistische Beispiele anstelle von unsinnigen Platzhaltern.

**Empfohlen:**

- `task:(Anruf OR Termin)`

**Nicht empfohlen:**

- `task:(foo OR bar)`

### Tastaturbelegung

Wenn du Zeichen auf der Tastatur beschreibst, ergänze das Zeichen in Klammern direkt hinter der Bezeichnung.

**Empfohlen:**

- Setze einen Bindestrich (-) vor das Wort.

**Nicht empfohlen:**

- Setze einen Bindestrich vor das Wort.
- Setze `-` vor das Wort.

### Markdown

Verwende Leerzeilen zwischen Markdown-Blöcken:

**Empfohlen:**

```md
# Überschrift 1

Das ist ein Absatz.

1. Erster Eintrag
2. Zweiter Eintrag
3. Dritter Eintrag
```

**Nicht empfohlen:**

```md
# Überschrift 1
Das ist ein Absatz.
1. Erster Eintrag
2. Zweiter Eintrag
3. Dritter Eintrag
```

### Maßangaben

Verwende "**Breite** x **Höhe** Pixel", um Bild- oder Bildschirmmaße zu beschreiben.

**Beispiel:** *Empfohlene Bildmaße: 1920 x 1080 Pixel.*

## Icons und Bilder

Verwende Icons und Bilder, wenn diese zum besseren Verständnis von Sachverhalten beitragen, die mit Worten schwer zu beschreiben sind. Du kannst Bilder im Ordner `Attachments` speichern.

- Verwende Bilder im Format `.png` oder `.svg`.
- Wenn ein Bild in der Notiz zu groß erscheint, verkleinere es mit einem Bildbearbeitungsprogramm oder passe die Maße an, wie in [[Dateien einbetten#Bilder einbetten|Bilder einbetten]] beschrieben.
- Du kannst besonders große oder komplexe Bilder in einem [[Callouts#Callouts einklappen|eingeklappten Callout]] platzieren, um den Lesefluss nicht zu unterbrechen. 
- Screenshots von Popout-Fenstern oder modalen Dialogen sollten im Hintergrund das gesamte Obsidian-Anwendungsfenster enthalten.

 ![[Style-guide-modal-example.png#interface]]

### Icons

[Lucide](https://lucide.dev/icons/)-Icons und Obsidian-spezifische Symbole können detaillierte Beschreibungen ergänzen, um Anwendungsfunktionen visuell darzustellen.

**Beispiel:** *Wähle in der Werkzeugleiste **Neuen Canvas erstellen** ( ![[lucide-layout-dashboard.svg#icon]] ), um einen Canvas im selben Ordner zu erstellen wie die aktive Notiz.*

**Richtlinien für Icons**

- Speichere Icons im Ordner `Attachments/icons`.
- Setze das Präfix `lucide-` vor den Namen eines Lucide-Icons.
- Setze das Präfix `obsidian-icon-` vor den Namen eines Obsidian-Icons.

**Beispiel:** Das Icon zum Erstellen eines neuen Canvas sollte `lucide-layout-dashboard` benannt werden.

- Verwende die SVG-Versionen von Icons, soweit verfügbar.
- Icons sollten eine Größe von `18 x 18` Pixel und eine Strichstärke von `1.5` haben. Du kannst diese Einstellungen in den SVG-Daten anpassen..

> [!info]- Strichstärke und Größe in einem SVG-Element anpassen
> ```html
> <svg xmlns="http://www.w3.org/2000/svg" width="BREITE" height="HÖHE" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="STRICHSTÄRKE" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-layout-dashboard"><rect width="7" height="9" x="3" y="3" rx="1"/><rect width="7" height="5" x="14" y="3" rx="1"/><rect width="7" height="9" x="14" y="12" rx="1"/><rect width="7" height="5" x="3" y="16" rx="1"/></svg>
>```

- Verwende den Anchor `icon`, um Symbole am Text in der Zeile auszurichten.
- Schließe Icons in Klammern ein: ( ![[lucide-settings.svg#icon]] ).

**Beispiel**: `( ![[lucide-settings.svg#icon]] )`

### Anchor Tags für Bilder

Mit den folgenden Anchor Tags kann die Darstellung eingebetteter Bilder angepasst werden.

> [!warning] Zur Beachtung in der Live-Vorschau
> Die Auswirkung von Anchor Tags wird in der **Live-Vorschau** nicht immer korrekt dargestellt. Überprüfe in der **Leseansicht**, ob die Anpassungen angewendet werden.

**Icon**

`![[lucide-menu.svg#icon]]`

Der Anchor Tag `icon` stellt die korrekte vertikale Ausrichtung von Icons zur Kennzeichnung von Bedienelementen sicher.

Menü-Icon mit `icon` Anchor Tag ( ![[lucide-menu.svg#icon]] ) und ohne ( ![[lucide-menu.svg]] ).

**Interface**

`![[Vault picker.png#interface]]`

Der Anchor Tag `interface` fügt dem Bild einen dekorativen Schlagschatten hinzu.

Bild mit `interface` Anchor Tag.

![[Vault picker.png#interface]]

Dasselbe Bild ohne den Anchor Tag.

![[Vault picker.png]]

**Outline**

`![[Backlinks.png#outline]]`

Der Anchor Tag `outline` fügt einem Bild einen dezenten Rahmen hinzu.

Bild mit `outline` Anchor Tag.

![[Backlinks.png#outline]]

Dasselbe Bild ohne den Anchor Tag.

![[Backlinks.png]]

### Optimierung

Bilder verlängern die Ladezeiten einer Seite und beanspruchen wertvollen [[Einführung in Obsidian Publish|Publish]] Speicherplatz. Bildoptimierung reduziert möglicherweise die Dateigröße bei gleichbleibender Bildqualität.

Sowohl Bilder, als auch Icons sollten optimiert werden.

> [!success] Werkzeuge zur Bildoptimierung
> Einige Programm-Empfehlungen zum Reduzieren der Dateigröße von Bildern:
> - **Windows:** [FileOptimizer](https://sourceforge.net/projects/nikkhokkho/)
> - **macOS:** [ImageOptim](https://imageoptim.com/)
> - **Linux/Unix** [Trimage](https://trimage.org)
> 
> Wir empfehlen eine Optimierungsrate von 65-75%.

## Layout

### Ungültige Links

Bitte überprüfe die Seiten, an denen du arbeitest, auf fehlerhafte Links und korrigiere sie bei Bedarf, bevor du einen Pull Request einreichst. Links können natürlich mit der Zeit ungültig werden und auf diese Weise kannst du helfen, die Qualität der Dokumentation bewahren.

### Meta Beschreibungen

Diese Dokumentation wird auf GitHub gepflegt und online über [[Einführung in Obsidian Publish|Obsidian Publish]] gehostet. Publish erzeugt [[Social-Media-Vorschau#Beschreibung|Meta Beschreibungen]] für Social Cards und andere [[SEO]] Elemente aus der `description`-[[Eigenschaften|Eigenschaft]].

Wenn die Seite, an der du arbeitest, keine `description` beinhaltet, füge bitte eine hinzu. Die Beschreibung sollte in maximal 150 Zeichen eine objektive Zusammenfassung des Seiteninhalts geben.

### Anleitungen

Achte darauf, Arbeitsschritte und Anleitungen immer sowohl für die ![[obsidian-icon-smartphone.svg#icon]] mobile Version, als auch für die ![[lucide-monitor-check.svg#icon]] Desktop-Version zu beschreiben.

Falls du selbst keinen Zugriff auf ein mobiles oder ein Desktop-Gerät hast, erwähne dies bitte in deinem Pull Request.

## Übersetzungen

Übersetze alle Inhalte, das umfasst unter anderem:

- Notiznamen
- Ordnernamen
- Aliasse
- Namen von Anhängen
- Alternative Linktexte
