---
aliases:
  - Gewusst wie/Notizen formatieren
  - Markdown
mobile: true
permalink: syntax
publish: true
---

Erfahre, wie du deine Notizen einfach formatieren kannst mit [Markdown](https://daringfireball.net/projects/markdown/). Für fortgeschrittene Formatierungstechniken, siehe [[Erweiterte Formatierung|Erweiterte Formatierung]].

## Absätze

Um in Markdown Absätze zu erzeugen, trenne Textblöcke mit einer **Leerzeile**. Jeder Textblock, der mit einer Leerzeile vom weiteren Text getrennt ist, wird als eigener Absatz behandelt.

```md
Das ist ein Absatz.

Das ist ein weiterer Absatz.
```

> Das ist ein Absatz.
>
> Das ist ein weiterer Absatz.

Eine Leerzeile im Text erzeugt standardmäßig einen Absatz in Markdown.

> [!tip] Mehrere Leerzeichen
> Mehrere aufeinanderfolgende Leerzeichen innerhalb oder zwischen Absätzen werden in der [[Ansichten und Modi#Leseansicht|Leseansicht]] oder der [[Obsidian Publish/Einführung|veröffentlichten Webseite]] zu einem einzigen Leerzeichen zusammengefasst. Dasselbe gilt für mehrere Leerzeilen.
> 
> ```md
> Mehrere          aufeinanderfolgende          Leerzeichen
> 
> 
> 
> und mehrere Leerzeilen zwischen Absätzen.
> ```
> 
> > Mehrere          aufeinanderfolgende          Leerzeichen
> > 
> > 
> > 
> > und mehrere Leerzeilen zwischen Absätzen.
> 
> Du kannst Leerräume erzwingen mittels HTML-Syntax - `&nbsp;` für Leerzeichen oder `<br>` für Leerzeilen.

## Zeilenumbrüche

Standardmäßig wird Obsidian bei einmaligem Drücken der Eingabetaste einen Zeilenumbruch erzeugen, der jedoch gemäß Markdown-Vorschrift als *Fortsetzung* desselben Absatzes interpretiert wird in der gerenderten Ausgabe. Um *innerhalb* eines Absatzes einen Zeilenumbruch zu erzwingen, ohne einen neuen Absatz zu erzeugen, hast du zwei Möglichkeiten:

- Füge am Ende der Zeile **zwei Leerzeichen** hinzu, bevor du die `Eingabetaste` drückst oder
- Verwende das Tastenkürzel `Umschalt + Eingabetaste`, um direkt eine Zeilenumbruch einzufügen.

> [!question]- Warum erzeugt das mehrmalige Drücken der Eingabetaste nicht mehrere Zeilenumbrüche in der Leseansicht?
> Markdown ignoriert einzelne Zeilenumbrüche und mehrere aufeinanderfolgende Zeilenumbrüche werden zusammengefasst und führen so zu nur einem neuen Absatz. Diese sogenannte Soft-Wrap-Regel stellt das Standardverhalten von Markdown dar, welches sicherstellt, dass Absätze natürlich fließen, ohne unerwartete Umbrüche.

Obsidian verfügt über eine Einstellung für **Strenge Zeilenumbrüche**, wodurch Obsidian der Standard-Markdown-Spezifikation für Zeilenumbrüche folgt.

Um diese Einstellung zu aktivieren:

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Editor → Anzeige** aktiviere **Strenge Zeilenumbrüche**.

Wenn **Strenge Zeilenumbrüche** aktiviert ist, reagiert Obsidian auf Zeilenumbrüche je nach Art der Zeilentrennung unterschiedlich, und zwar wie folgt:

**Einfacher Zeilenumbruch ohne Leerzeichen**: Bei einmaligem Drücken der Eingabetaste ohne zusätzliche Leerzeichen am Zeilenende werden beide Zeilen in der gerenderten Ausgabe zu einer einzigen kombiniert.

```md
Zeile eins
Zeile zwei
```

> Zeile eins Zeile zwei

**Einfacher Zeilenumbruch mit zwei angehängten Leerzeichen**: Wenn du am Ende der ersten Zeile zwei oder mehr Leerzeichen hinzufügst, bevor du die Eingabetaste drückst, bleiben die beiden Zeilen Bestandteil desselben Absatzes, werden jedoch durch einen Zeilenumbruch getrennt (entspricht dem HTML-Element `<br>`). Im Beispiel unten deuten die beiden Unterstriche die Leerzeichen an.

```md
Zeile drei__  
Zeile vier
```

> Zeile drei<br>Zeile vier

**Doppelter Zeilenumbruch (mit oder ohne angehängte Leerzeichen)**: Drückst du die Eingabetaste nach einer Zeile zweimal (oder öfter), wird ein neuer Absatz erzeugt (entspricht dem HTML-Element `<p>`), unabhängig von der Anzahl der Leerzeichen am Ende dieser Zeile.

```md
Zeile fünf 

Zeile sechs
```

> <p>Zeile fünf</p><p>Zeile sechs</p>

## Überschriften

Um eine Überschrift zu erzeugen, kannst du bis  zu sechs Hash-Symbole (`#`) vor dem Überschriftentext einfügen. Die Anzahl der Hash-Symbole bestimmt die Größe der Überschrift.

```md
# This is a heading 1
## This is a heading 2
### This is a heading 3
#### This is a heading 4
##### This is a heading 5
###### This is a heading 6
```

%% These headings use HTML to avoid cluttering the Outline/Table of contents %%
> <h1>This is a heading 1</h1>
> <h2>This is a heading 2</h2>
> <h3>This is a heading 3</h3>
> <h4>This is a heading 4</h4>
> <h5>This is a heading 5</h5>
> <h6>This is a heading 6</h6>

## Betonungen

Du kannst Text auch mit Hilfe von  [[Tastenkürzel zum Bearbeiten|Editor-Shortcuts]] formatieren.

| Stil                          | Syntax                   | Beispiel                                        | Ausgabe                                       |
| ----------------------------- | ------------------------ | ----------------------------------------------- | --------------------------------------------- |
| Fett                          | `** **` oder `__ __`     | `**Fetter Text**`                               | **Fetter Text**                               |
| Kursiv                        | `* *` oder `_ _`         | `*Kursiver Text*`                               | *Kursiver Text*                               |
| Durchgestrichen               | `~~ ~~`                  | `~~Durchgestrichener Text~~`                    | ~~Durchgestrichener Text~~                    |
| Hervorgehoben                 | `== ==`                  | `==Hervorgehobener Text==`                      | ==Hervorgehobener Text==                      |
| Fett und kursiv verschachtelt | `** **` und `_ _`        | `**Fetter und _verschachelter kursiver_ Text**` | **Fetter und _verschachelter kursiver_ Text** |
| Fett und kursiv               | `*** ***` oder `___ ___` | `***Fetter, kursiver Text***`                   | ***Fetter, kursiver Text***                   |

Erfahre unter [[#Escape-Zeichen]], wie du die Anzeige der speziellen Formatierungszeichen erzwingen kannst, ohne dass die Formatierungsfunktion ausgelöst wird.

## Interne Links

Obsidian unterstützt zwei Formate für [[Interne Links|Interne Links]] zwischen Notizen:

- Wiki-Links: `[[Grundgesetze der Bewegung]]`
- Markdown: `[Grundgesetze der Bewegung](Grundgesetze%20der%20Bewegung.md)`

## Externe Links

Wenn du auf eine externe URL verweisen möchtest, kannst du einen Inline-Link erstellen, indem du dem Linktext in eckige Klammern (`[]`) und die URL in runde Klammern (`()`) setzt.

```md
[Obsidian Hilfe](https://help.obsidian.md)
```

> [Obsidian Hilfe](https://help.obsidian.md)

Du kannst auch Verweise auf Notizen in einem anderen Vault erstellen, indem du eine [[Obsidian URI|Obsidian URI]] verlinkst.

```md
[Notiz](obsidian://open?vault=AndererVault&file=Notiz.md)
```

### Leerzeichen in Links maskieren

Enthält deine URL Leerzeichen, musst du diese maskieren, indem du jedes Leerzeichen mit `%20` ersetzt.

```md
[Meine Notiz](obsidian://open?vault=AndererVault&file=Meine%20Notiz.md)
```

Du kannst eine URL auch maskieren, indem du sie in spitze Klammern (`< >`) setzt.

```md
[Meine Notiz](<obsidian://open?vault=AndererVault&file=Meine Notiz.md>)
```

## Externe Bilder

Mittels externer URLs kannst du auch Bilder hinzufügen, indem du ein Ausrufezeichen (`!`) vor einen [[#Externe Links|externen Link]] setzt.

```md
![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

> ![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)

Du kannst die Maße des Bildes anpassen, indem du z.B. `|640x480` an den Linktext anhängst, wobei die erste Zahl die Breite und die zweite die Höhe bestimmt.

```md
![Engelbart|100x145](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

Wenn du nur die Breite angibst, wird das Bild entsprechend seinem ursprünglichen Seitenverhältnis skaliert.

```md
![Engelbart|100](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

> [!TIP] Tipp
> Du kannst auch Bilder aus deinem lokalen Vault anzeigen, siehe [[Dateien einbetten#Bilder einbetten|Bild in eine Notiz einbetten]].

## Zitate

Du kannst Text zitieren, indem du eine schließende spitze Klammer (`>`) vor den Text stellst.

```md
> Human beings face ever more complex and urgent problems, and their effectiveness in dealing with these problems is a matter that is critical to the stability and continued progress of society.

\- Doug Engelbart, 1961
```

>> Human beings face ever more complex and urgent problems, and their effectiveness in dealing with these problems is a matter that is critical to the stability and continued progress of society.
>
>\- Doug Engelbart, 1961

> [!TIP] Tipp
> Um dein Zitat in ein [[Callouts|Callout]] zu verwandeln, stelle `[!info]` als erste Zeile vor das Zitat.

## Listen

Eine ungeordnete Liste erzeugst du, indem du Listeneinträgen ein `-`, `*`, oder `+` voranstellst.

```md
- Erster Listeneintrag
- Zweiter Listeneintrag
- Dritter Listeneintrag
```

> - Erster Listeneintrag
> - Zweiter Listeneintrag
> - Dritter Listeneintrag

Für eine geordnete Liste beginne jede Zeile mit einer Zahl gefolgt von einem Punkt (`.`) oder einer schließenden runden Klammer (`)`).

```md
1. Erster Listeneintrag
2. Zweiter Listeneintrag
3. Dritter Listeneintrag
```

> 1. Erster Listeneintrag
> 2. Zweiter Listeneintrag
> 3. Dritter Listeneintrag

```md
1) Erster Listeneintrag
2) Zweiter Listeneintrag
3) Dritter Listeneintrag
```

> 1) Erster Listeneintrag
> 2) Zweiter Listeneintrag
> 3) Dritter Listeneintrag

%% Stand 2025-07-24: Wird ohne Zeilenumbruch gerendert; `Umschalt + Eingabetaste` erzeugt eine neue Zeile mit zwei Leerzeichen, der Cursor bleibt in dieser Zeile stehen. %%
%%Verwende `Umschalt + Eingabetaste`, um einen [[#Zeilenumbrüche|Zeilenumbruch]] innerhalb der Liste zu erzeugen, ohne die Nummerierung zu unterbrechen.

```md
1. First list item
   
2. Second list item
3. Third list item
   
4. Fourth list item
5. Fifth list item
6. Sixth list item
```
%%

### Aufgabenlisten

Um eine Aufgabenliste zu erzeugen, beginne jeden Listeneintrag mit einem Bindestrich gefolgt von einem Leerzeichen und einem eckigen Klammerpaar, das ein Leerzeichen umschließt (`- [ ]`).

```md
- [x] Erledigte Aufgabe.
- [ ] Noch zu erledigende Aufgabe.
```

> - [x] Erledigte Aufgabe.
> - [ ] Noch zu erledigende Aufgabe.

In der Leseansicht kannst du den Status einer Aufgabe ändern, indem du das Ankreuzfeld anklickst.

> [!tip] Tipp
> Du kannst innerhalb der Klammern ein beliebiges Zeichen verwenden, um eine Aufgabe als erledigt zu kennzeichnen.
>
> ```md
> - [x] Milch
> - [?] Eier
> - [-] Mehl
> ```
>
>> - [x] Milch
>> - [?] Eier
>> - [-] Mehl

### Verschachtelte Listen

Jede Art von Liste, ob geordnet oder ungeordnet, kann wiederum unter jeder Art von Liste verschachtelt werden.

Um eine verschachtelte Liste zu erzeugen, rücke einen oder mehrere Listeneinträge mit mindestens vier Leerzeichen bzw. einem Tab ein. Innerhalb einer verschachtelten Liste können Listenarten gemischt werden.

```md
1. Erster Listeneintrag
    1. Geordneter verschachtelter Listeneintrag
2. Zweiter Listeneintrag
    - Ungeordneter verschachtelter Listeneintrag
```

> 1. Erster Listeneintrag
>     1. Geordneter verschachtelter Listeneintrag
> 2. Zweiter Listeneintrag
>     - Ungeordneter verschachtelter Listeneintrag

Auf dieselbe Weise kannst du auch eine verschachtelte Aufgabenliste erzeugen.

```md
- [ ] Aufgabe 1
	- [ ] Teilaufgabe 1
- [ ] Aufgabe 2
	- [ ] Teilaufgabe 1
```

> - [ ] Aufgabe 1
> 	- [ ] Teilaufgabe 1
> - [ ] Aufgabe 2
> 	- [ ] Teilaufgabe 1

Verwende `Tab` oder `Umschalt + Tab`, um ausgewählte Listeneinträge einzurücken bzw. die Einrückung rückgängig zu machen und so die Einträge auf einfache Weise zu organisieren.

## Horizontale Linien

Du kannst drei oder mehr Sternchen `***`, Bindestriche `---` oder Unterstriche `___` in einer separaten Zeile verwenden, um eine horizontale Linie zu erzeugen. Die einzelnen Zeichen können auch mit Leerzeichen getrennt sein.

```md
***
****
* * *
---
----
- - -
___
____
_ _ _
```

***

## Quelltext

Du kannst Text als Quelltext innerhalb eines Absatzes oder als separaten Quelltext-Block formatieren.

### Quelltext innerhalb Absatz

Innerhalb eines Satzes formatierst du Quelltext, indem du ihn in einfache Backticks (Accent grave) einschließt.

```md
Text innerhalb `Backticks` in einer Zeile wird als Quelltext formatiert.
```

> Text innerhalb `Backticks` in einer Zeile wird als Quelltext formatiert.

> [!TIP] Tipp
> Wenn du Quelltext stattdessen mit **doppelten** Backticks umschließt, erhältst du ``Quelltext, der einen Backtick ` enthält``.

### Quelltext-Blöcke

Um Quelltext als Block zu formatieren, schließe ihn in dreifache Backticks (`` ` ``) oder Tilden (`~`) ein.

~~~
```
cd ~/Desktop
```
~~~

```
~~~
cd ~/Desktop
~~~
```

> ```md
> cd ~/Desktop
> ```

Du kannst Quelltext auch durch Einrückung mit einem `Tab` oder vier Leerzeichen erzeugen.

```md
    cd ~/Desktop
```

Syntax-Highlighting für einen Quelltext-Block wird erzeugt, indem du nach den einleitenden Backticks den entsprechenden Sprachcode hinzufügst.

~~~md
```js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
~~~

```js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

Obsidian verwendet Prism für die Syntaxhervorhebung. Für mehr Informationen siehe [Unterstützte Sprachen](https://prismjs.com/#supported-languages).

> [!note] Hinweis
> PrismJS wird in der [[Ansichten und Modi#Quellcode-Ansicht|Quellcode-Ansicht]] und der [[Ansichten und Modi#Live-Vorschau|Live-Vorschau]] nicht unterstützt. Dort werden Quelltext-Blöcke unter Umständen anders dargestellt.

## Fußnoten

Du kannst deinen Notizen Fußnoten[^footnote] hinzufügen wie folgt:

[^footnote]: Das ist eine Fußnote.

```md
Das ist eine einfache Fußnote[^1].

[^1]: Das ist der referenzierte Text.
[^2]: Beginne jede neue Zeile mit zwei Leerzeichen.
  Auf diese Weise erzeugst du mehrzeilige Fußnoten.
[^note]: Benannte Fußnoten erscheinen im Text weiterhin als Zahlen, können aber die Identifizierung und Verknüpfung von Referenzen erleichtern.
```

Du kannst Fußnoten auch direkt innerhalb eines Satzes einfügen. Beachte, dass das Hochzeichen (`^`) außerhalb der eckigen Klammern steht.

```md
Fußnoten können innerhalb eines Satzes eingefügt werden. ^[Inline-Fußnote]
```

> [!note] Hinweis
> Inline-Fußnoten funktionieren nur in der Leseansicht, nicht in der Live-Vorschau.

## Kommentare

Du kannst Kommentare erzeugen, indem du Text mit doppelten Prozentzeichen `%%` umschließt. Kommentare sind nur im Bearbeitungsmodus sichtbar.

```md
Das ist ein %%Inline-%% Kommentar.

%%
Das ist ein Kommentarblock.

Kommentarblöcke können mehrzeilig sein.
%%
```

## Escape-Zeichen

Möglicherweise musst du manchmal Sonderzeichen darstellen, die in Markdown eine spezielle Bedeutung haben, wie bspw. `*`, `_`, oder `#`. Stelle diesen Zeichen einen Backslash (`\`) voran, um sie anzuzeigen, ohne die Formatierungsfunktion auszulösen.

> [!example] Beispiele
> 
> - Sternchen: `\*`
> - Unterstrich: `\_`
> - Hash-Symbol: `\#`
> - Accent grave: `` \` ``
> - Pipe-Symbol: `\|`
> - Tilde: `\~`

```md
\*Dieser Text wird nicht kursiv dargestellt.\*
```

\*Dieser Text wird nicht kursiv dargestellt.\*

Bei der Arbeit mit nummerierten Texten möchtest du möglicherweise die Listenformatierung verhindern. Setze den Backslash vor den Punkt, **nicht** vor die Zahl.

```md
1\. Das ist kein Listeneintrag.
```

> 1\. Das ist kein Listeneintrag.

## Erfahre mehr

Weitere Informationen zu fortgeschrittenen Formatierungstechniken, z.B. für Tabellen, Diagramme und mathematische Ausdrücke, findest du unter [[Erweiterte Formatierung|Erweiterte Formatierung]].

Um mehr darüber zu erfahren, wie Markdown-Parsing in Obsidian funktioniert, lies weiter unter [[Obsidian Flavored Markdown]].
