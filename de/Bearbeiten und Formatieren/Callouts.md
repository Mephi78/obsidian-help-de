---
aliases:
  - Gewusst wie/Callouts verwenden
  - Infokasten
description: Erfahre, wie du mit Hilfe von Callouts Zusatzinformationen in deine Notizen einfügen kannst, ohne den Lesefluss zu unterbrechen.
mobile: true
permalink: callouts
publish: true
---

Verwende *Callouts*, um deine Notizen mit Randinformationen zu versehen, ohne den Lesefluss zu unterbrechen oder um Informationen besonders hervorzuheben.

Um bspw.  einen Infokasten zu erstellen, beginne einen [[Formatierungsgrundlagen#Zitate|Zitatblock]] mit `[!info]`, wobei `info` den *Callout-Typ* bezeichnet. Der Callout-Typ bestimmt den Stil des Kastens. Eine Übersicht der verfügbaren Typen findest du unter [[#Unterstützte Typen]]. Auch [[Obsidian Publish/Einführung|Obsidian Publish]] verfügt über eine native Unterstützung von Callouts.

```markdown
> [!info] Das ist der Callout-Titel
> Und das ein Callout-Block.
> Du kannst **Markdown**, [[Internal link|Wiki-Links]] und [[Embed files|Einbettungen]] verwenden!
> ![[Engelbart.jpg]]
```

> [!info] Das ist der Callout-Titel
> Und das ein Callout-Block.
> Du kannst **Markdown**, [[Interne Links|Wiki-Links]] und [[Dateien einbetten|Einbettungen]] verwenden!
> ![[Engelbart.jpg]]

Du kannst deiner Notiz im Bearbeitungsmodus ein Standard-Callout vom Typ `![note]` hinzufügen über den [[Command palette|Befehl]] **Callout einfügen**. Der Cursor positioniert sich automatisch im Feld für den Callout-Typ, so dass du diesen ändern kannst, bevor du den Inhalt des Callouts bearbeitest.

Wenn du bereits bestehenden Inhalt in ein Callout umwandeln möchtest, markiere den Text (einschließlich Listen, Quelltext-Blöcke etc.) und wähle den Befehl **Callout einfügen**. Der ausgewählte Inhalt wird automatisch als Callout formatiert. Außer über die Befehlspalette ist diese Funktion auch über das Kontextmenü (Rechtsklick auf den ausgewählten Inhalt → **Einfügen → Callout**) verfügbar.

In der [[Ansichten und Modi#Live-Vorschau|Live-Vorschau]] kannst du mit Rechtsklick auf das gerenderte Callout den Callout-Typ ändern. Die Auswahl **Ohne** entfernt die Callout-Formatierung komplett.

### Titel anpassen

Standardmäßig entspricht der Titel eines Callouts dem Callout-Typ in Groß-/Kleinschreibung. Du kannst den Titel ändern, indem du einen eigenen Text hinter der Typ-Bezeichnung hinzufügst:

```markdown
> [!tip] Mein eigener Callout-Titel
> Hübsch, oder?
```

> [!tip] Mein eigener Callout-Titel
> Hübsch, oder?

Du kannst den Textteil auch weglassen, um ein nur ein reines Titel-Callout zu erstellen::

```markdown
> [!tip] Reines Titel-Callout
```

> [!tip] Reines Titel-Callout

### Callouts einklappen

Erstelle einklappbare Callouts mit einem Plus (`+`) oder Minus (`-`) direkt hinter dem Bezeichner.

Ein Plus sorgt dafür, dass das Callout standardmäßig ausgeklappt ist, ein Minus hingegen klappt es ein.

```markdown
> [!faq]- Kann man Callouts einklappen?
> Ja! Wenn du ein Callout einklappst, wird der Textteil versteckt.
```

> [!faq]- Kann man Callouts einklappen?
> Ja! Wenn du ein Callout einklappst, wird der Textteil versteckt.

### Verschachtelte Callouts

Du kannst Callouts über mehrere Ebenen verschachteln.

```markdown
> [!question] Lassen sich Callouts verschachteln?
> > [!todo] Ja, na klar!
> > > [!example]  Du kannst sogar mehrere Verschachtelungsebenen verwenden.
```

> [!question] Lassen sich Callouts verschachteln?
> > [!todo] Ja, na klar!
> > > [!example]  Du kannst sogar mehrere Verschachtelungsebenen verwenden.

### Benutzerdefinierte Callouts

[[CSS-Bausteine]] und [[Externe Erweiterungen]] ermöglichen die Erstellung von eigenen Callout-Typen. Du kannst damit auch das Aussehen der [[#Unterstützte Typen|Standard-Typen]] ändern.

Um deinen eigenen Callout-Typ zu definieren, erstelle den folgenden CSS-Block:

```css
.callout[data-callout="mein-callout"] {
    --callout-color: 0, 0, 0;
    --callout-icon: lucide-alert-circle;
}
```

Mit dem Wert des Attributes `data-callout` bestimmst du den Typ-Bezeichner, den du verwenden möchtest, z.B. `[!mein-callout]`.

- `--callout-color` legt die Hintergrundfarbe fest, hier im Beispiel in RGB-Notation (Zahlen von 0 bis 255 jeweils für Rot, Grün und Blau).
- `--callout-icon` kann die Symbol-ID eines [lucide.dev](https://lucide.dev)-Icons sein oder ein SVG-Element. 

> [!warning] Hinweis zu Lucide-Icons
> Obsidian aktualisiert Lucide-Icons regelmäßig. Die in der aktuellen Obsidian-Version verfügbare Version der Lucide-Symbole siehst du unten. Du kannst Symbole aus dieser oder früheren Versionen für benutzerdefinierte Callouts verwenden.
> 
> ![[Danksagung#^lucide]]

> [!tip] SVG-Symbole
> Anstelle von Lucide-Symbolen kannst du auch SVG-Elemente als Callout-Icon verwenden.
>
> ```css
> --callout-icon: '<svg>...mein eigenes svg...</svg>';
> ```

### Unterstützte Typen

Du kannst unterschiedliche Callout-Typen und Aliasse verwenden. Jeder Typ hat seine eigene Hintergrundfarbe und ein spezifisches Icon.

Um diese Standard-Typen zu verwenden, ersetze den Typ-Bezeichner in den obigen Beispielen mit einem beliebigen der hier aufgelisteten Typen, wie bspw. `[!tip]` oder `[!warning]`. Du kannst den Callout-Typ in der Live-Vorschau auch ändern mit Rechtsklick auf das Callout.

Sofern du keine [[#Benutzerdefinierte Callouts|benutzerdefinierten Callouts]] verwendest, wird jeder nicht unterstützte Typ standardmäßig als `note`-Typ angezeigt. Die Groß-/Kleinschreibung spielt beim Typ-Bezeichner keine Rolle.

> [!note]
> ```md
> > [!note]
> > Lorem ipsum dolor sit amet
> ```

---

> [!abstract]-
> ```md
> > [!abstract]
> > Lorem ipsum dolor sit amet
> ```

Alias: `summary`, `tldr`

---

> [!info]-
> ```md
> > [!info]
> > Lorem ipsum dolor sit amet
> ```

---

> [!todo]-
> ```md
> > [!todo]
> > Lorem ipsum dolor sit amet
> ```

---

> [!tip]-
> ```md
> > [!tip]
> > Lorem ipsum dolor sit amet
> ```

Alias: `hint`, `important`

---

> [!success]-
> ```md
> > [!success]
> > Lorem ipsum dolor sit amet
> ```

Alias: `check`, `done`

---

> [!question]-
> ```md
> > [!question]
> > Lorem ipsum dolor sit amet
> ```

Alias: `help`, `faq`

---

> [!warning]-
>  ```md
> > [!warning]
> > Lorem ipsum dolor sit amet
> ```

Alias: `caution`, `attention`

---

> [!failure]-
> ```md
> > [!failure]
> > Lorem ipsum dolor sit amet
> ```

Alias: `fail`, `missing`

---

> [!danger]-
> ```md
> > [!danger]
> > Lorem ipsum dolor sit amet
> ```

Alias: `error`

---

> [!bug]-
> ```md
> > [!bug]
> > Lorem ipsum dolor sit amet
> ```

---

> [!example]-
> ```md
> > [!example]
> > Lorem ipsum dolor sit amet
> ```

---

> [!quote]-
> ```md
> > [!quote]
> > Lorem ipsum dolor sit amet
> ```

Alias: `cite`
