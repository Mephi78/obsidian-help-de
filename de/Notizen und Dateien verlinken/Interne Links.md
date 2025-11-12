---
aliases:
  - Gewusst wie/Interner Link
  - Gewusst wie/Blöcke verlinken
cssclasses:
  - soft-embed
description: Erfahre, wie du deine Notizen mit anderen Notizen, Anhängen und weiteren Dateien verknüpfen kannst mit Hilfe von internen Links.
mobile: true
permalink: links
publish: true
---

Erfahre, wie du mit Hilfe von *internen Links* in deinen Notizen Verknüpfungen zu anderen Notizen, Anhängen und weiteren Dateien erstellen kannst. Auf diese Weise lässt sich aus deinen Notizen ein Wissensnetzwerk aufbauen. ^b15695

Obsidian kann interne Links automatisch aktualisieren, wenn du eine Datei umbenennst. Standardmäßig erhältst du beim Ändern von Dateinamen eine Bestätigungsaufforderung, bevor interne Links aktualisiert werden. Wähle über den Bestätigungsdialog das bevorzugte Verhalten oder ändere es in den **Einstellungen** ( ![[lucide-settings.svg#icon]] ) unter **Dateien & Links → Interne Links automatisch aktualisieren**.

## Unterstützte Formate für interne Links

Obsidian unterstützt die folgenden Link-Formate:

- Wiki-Link: `[[Grundgesetze der Bewegung]]` oder `[[Grundgesetze der Bewegung.md]]`
- Markdown: `[Grundgesetze der Bewegung](Grundgesetze%20der%20Bewegung)` oder `[Grundgesetze der Bewegung](Grundgesetze%20der%20Bewegung.md)`

Beide Links im Beispiel oben sind gleichwertig — sie werden auf die gleiche Weise dargestellt und verweisen auf dieselbe Notiz.

> [!note] Hinweis
> Links im Markdown-Format erfordern ein [URL-Encoding](https://de.wikipedia.org/wiki/URL-Encoding) der Zieladresse. Leerzeichen bspw. müssen durch `%20`ersetzt werden.

Standardmäßig generiert Obsidian Verknüpfungen im kompakteren Wiki-Link-Format. Wenn dir Interoperabilität wichtig ist, kannst du Wiki-Links deaktivieren und stattdessen das Markdown-Format verwenden.

Um Markdown-Links zu verwenden:

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Dateien & Links** deaktiviere **\[\[Wiki-Links\]\] verwenden**.

Auch wenn du Wiki-Links deaktiviert hast, kannst du zwei eckige geöffnete Klammern `[[` eingeben, um Autovervollständigen auszulösen. Wählst du dann eine Datei aus der Liste, erzeugt Obsidian stattdessen einen Markdown-Link.

> [!note] Ungültige Zeichen
> Eine Zeichenfolge, die eines der folgenden Zeichen enthält, funktioniert möglicherweise nicht als Link: `# | ^ : %% [[ ]]`. 
> 
> Wir empfehlen, diese Zeichen zu vermeiden und [sichere Dateinamen](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names) zu verwenden. 

## Dateien verlinken

Der Bearbeitungsmodus bietet folgende Möglichkeiten zum Erstellen von Links:

- Gib `[[` ein und wähle dann die Datei aus, die du verlinken möchtest.
- Oder wähle einen Textabschnitt in deiner Notiz aus und dann gib `[[` ein.
- Oder öffne die [[Befehlspalette|Befehlspalette]] und wähle **Internen Link hinzufügen**.

![[Schnellauswahl#^search-autocomplete-large]]

Du kannst jede [[Dateitypen|unterstützte Datei]] verlinken, jedoch musst du bei allen Dateien, die keine Markdown-Dateien sind, die Dateiendung mit angeben, bspw. `[[Abbildung 1.png]]`.

> [!tip] Setzt du ein Ausrufezeichen (!) vor einen Link, wird der Inhalt der verlinkten Datei direkt [[Dateien einbetten|eingebettet]].

## Sprungmarken erstellen

Du kannst Links auf bestimmte Überschriften in deiner Notiz erstellen, sogenannte *Sprungmarken* oder Seitenanker.

**Überschrift in derselben Notiz verlinken**

Um eine Überschrift innerhalb derselben Notiz zu erstellen, bspw. für ein interaktives Inhaltsverzeichnis, gib `[[#` ein und wähle aus der Liste der verfügbaren Überschriften diejenige aus, die du verlinken möchtest.

`[[#Vorschau für eine verlinkte Datei]]` erzeugt bspw. einen Link zur Überschrift [[#Vorschau für eine verlinkte Datei]].

**Überschrift in einer anderen Notiz verlinken**

Um eine Überschrift aus einer anderen Notiz zu erstellen, erstelle zunächst einen Link zu der anderen Notiz und gib am Ende einen Hash `#` ein, um eine Liste der verfügbaren Überschriften zu erhalten.

`[[Obsidian#Links sind das A und O]]` erzeugt bspw. einen Link nach [[Obsidian#Links sind das A und O]].

**Unterüberschriften verlinken**

Du kannst mehrere Hash-Symbole verwenden, um Unterüberschriften zu verlinken.

`[[Hilfe und Kontakt#Fragen und Empfehlungen#### Fehler melden oder neue Funktionen anfragen]]` erzeugt dann einen Link nach [[Hilfe und Kontakt#Fragen und Empfehlungen#### Fehler melden oder neue Funktionen anfragen]].

**Überschriften im gesamten Vault suchen**

Du kannst auch zwei Hash-Symbole verwenden (`[[## Überschrift]]`), um nach einer Überschrift im gesamten Vault zu suchen, um diese zu verlinken.

Mit `[[##` sucht allgemein nach Überschriften im gesamten Vault, während `[[## Team]]` die Suchergebnisse filtert nach Überschriften, die das Wort *Team* enthalten.

> [!info]- Abbildung: Sprungmarken zu Überschriften suchen
>
> ![[internal-links-header.png#interface]]

## Block in einer Notiz verlinken

Ein Block ist eine Texteinheit in einer Notiz, wie ein Absatz, Zitatblock oder Listenelement.

Einen Block kannst du verlinken, indem du ans Ende eines Links auf eine Notiz einen Hashtag gefolgt von einem Hochzeichen (`#^`) und einem eindeutigen Bezeichner anhängst, bspw. `[[2023-01-01#^37066d]]`. Sobald du das Hochzeichen (`^`) eingibst, erscheint eine Liste zur Auswahl von verfügbaren Blöcken.

Setze bei *einfachen Absätzen* den Blockbezeichner mit vorangestelltem Leerzeichen ans Zeilenende:

```md
Der flinke violette Edelstein flitzt mit rasender Geschwindigkeit durch den Absatz. Mit einem Stift in der einen Hand und einer Büroklammer in der anderen arbeitet Gemmy daran, die Welt des Notizen-Schreibens zu einem glücklicheren Ort zu machen. ^37066d
```

Bei *strukturierten Blöcken* (Listen, Zitate, Callouts, Tabellen) sollte der Blockbezeichner in einer separaten Zeile unterhalb und vom Block durch eine Leerzeile getrennt platziert werden:

```md
> Der flinke violette Edelstein flitzt mit rasender Geschwindigkeit durch den Absatz. Mit einem Stift in der einen Hand und einer Büroklammer in der anderen arbeitet Gemmy daran, die Welt des Notizen-Schreibens zu einem glücklicheren Ort zu machen.

^37066f

Dies ist die Geschichte von Gemmy, dem nicht hilfreichen Assistenten.  
```

Bei *spezifischen Zeilen innerhalb einer Liste* kann der Blockbezeichner direkt am Anstrich notiert werden:

```mathjax
- Gemmy
    $$Büroklammer / Stift$$ 
    ^37006f
- Nicht hilfreicher Assistent
```

> [!warning] Links zu spezifischen Teilen von Zitaten, Beschriftungen oder Tabellen werden nicht unterstützt.

**Blöcke im gesamten Vault suchen**

Um im gesamten Vault nach einem Block zu suchen, den du verlinken möchtest, kannst du zwei Hochzeichen `[[^^` eingeben. Allerdings dürfte die Ergebnisliste sehr viel länger sein, als bei der Suche nach [[#Sprungmarken erstellen|verlinkbaren Überschriften]], daher empfiehlt sich auch hier die Eingabe eines Suchbegriffs nach den Hochzeichen.

> [!info]- Abbildung: Sprungmarken zu Blöcken suchen
> ![[link-block-heading.png#interface]]

Du kannst auch menschenlesbare Blockbezeichner erstellen, indem du ein Hochzeichen (`^`), gefolgt von dem Bezeichner eingibst. Blockbezeichner können nur aus lateinischen Buchstaben, Zahlen und Bindestrichen bestehen.

Hänge bspw. `^zitat-des-tages` ans Ende eines Blockes:

```md
"Du steigst nicht auf das Niveau deiner Ziele auf. Du fällst auf das Niveau deiner Systeme." —James Clear ^zitat-des-tages
```

Diesen Block kannst du nun verlinken mit `[[2023-01-01#^zitat-des-tages]]`.

> [!hint] Hinweis
> Achte darauf, dem `^blockbezeichner` immer ein Leerzeichen voranzustellen, wenn du diesen direkt am Ende einer Zeile anhängst.

> [!warning] Interoperabilität
> Blockreferenzen sind spezifisch für Obsidian und gehören nicht zum Markdown-Standard. Links, die Blockreferenzen enthalten, funktionieren außerhalb von Obsidian nicht.

## Anzeigetext für einen Link ändern

Standardmäßig zeigt Obsidian Linktexte wie folgt an:  
- `[[Beispiel]]` wird angezeigt als [[Beispiel]]  
- `[[Beispiel#Details]]` wird zu [[Beispiel#Details]]

Du kannst den Anzeigetext eines Links ändern:

**Wiki-Link**:  
Verwende einen vertikalen Strich (`|`), um den Anzeigetext zu ändern.

- `[[Beispiel|Mein Text]]` wird dargestellt als [[Beispiel|Mein Text]]  
- `[[Beispiel#Details|Detailabschnitt]]` wird zu [[Beispiel#Details|Detailabschnitt]]

**Markdown-Link**:  
Verwende `[Anzeigetext](Link URL)`, um den Linktext anzupassen.

- `[Mein Text](Beispiel.md)` wird angezeigt als [Mein Text](Beispiel.md)  
- `[Detailabschnitt](Beispiel.md#Details)` wird zu [Detailabschnitt](Beispiel.md#Details)

Diese Methode ist hilfreich, wenn du einmalig die Darstellung eines Links kontextbezogen ändern möchtest. Wenn du einen wiederverwendbaren, alternativen Anzeigetext benötigst, empfiehlt sich dagegen die Verwendung eines [[Aliasse|Alias]].

Wenn du bspw. häufig auf die `[[Grundgesetze der Bewegung]]` als `[[Newtonsche Gesetze]]` verweisen möchtest, kannst du "Newtonsche Gesetze" einfach als Alias hinzufügen und ein benutzerdefinierter Anzeigetext ist nicht mehr nötig.

> [!tip] TL;DR
> Verwende einen [[#Anzeigetext für einen Link ändern|Anzeigetext]], wenn du die Darstellung eines Links *in einem spezifischen Kontext* anpassen möchtest.
> 
> Verwende [[Aliasse|Aliasse]], wenn du in deinem Vault wiederholt auf dieselbe Notiz mit *unterschiedlichen Bezeichnungen* verweisen möchtest.
^callout-internal-links-link-text

## Vorschau für eine verlinkte Datei

> [!note] Hinweis
> Um eine Vorschau für verknüpfte Dateien zu erhalten, musst du die [[Seitenvorschau|Seitenvorschau]] aktivieren.

Um die Vorschau für eine Datei zu sehen, bewege den Mauszeiger über einen internen Link. Im Bearbeitungsmodus musst du zusätzlich `Strg` (oder `Cmd` unter macOS) gedrückt halten, während du über den Link fährst. Eine Vorschau des Dateiinhaltes erscheint neben dem Mauszeiger.

