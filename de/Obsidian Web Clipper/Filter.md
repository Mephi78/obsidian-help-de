---
permalink: web-clipper/filter
publish: true
---

Mit Filtern kannst du [[Variablen]] in [[Obsidian Web Clipper/Vorlagen|Web Clipper-Vorlagen]] verändern. Filter werden auf Variablen angewendet mit der Pipe-Syntax `{{variable|filter}}`.

- Filter funktionieren für beliebige [[Variablen|Variablen]] (`prompt`, `meta`, `selector` und `schema`).
- Filter können verkettet werden, z.B. `{{variable|filter1|filter2}}`. Sie werden in der Reihenfolge angewendet, in der sie notiert sind.

## Datumsangaben

Datumsangaben umrechnen und formatieren.

### `date`

Konvertiert ein Datum in ein anderes Format, siehe [Referenz](https://day.js.org/docs/en/display/format).

- `{{date|date:"YYYY-MM-DD"}}` konvertiert das aktuelle Datum ins Format "YYYY-MM-DD".
- Verwende `date:("ausgabeFormat", "eingabeFormat")`, um das Eingabeformat zu bestimmen, z.B. `"1.12.2024"|date:("YYYY-MM-DD", "D.M.YYYY")` wandelt "1.12.2024" in `"2024-12-01"` um.

### `date_modify` 

Ändert ein Datum durch Hinzufügen oder Abziehen einer definierten Zeitspanne, siehe [Referenz](https://day.js.org/docs/en/manipulate/add).

- `"2024-12-01"|date_modify:"+1 year"` wird zu `"2025-12-01"`
- `"2024-12-01"|date_modify:"- 2 months"` wird zu `"2024-10-01"`

### `duration`

Konvertiert eine Zeitspanne im Format ISO 8601 oder eine Angabe in Sekunden in ein definiertes Format. Verwende folgende Token: `HH` (Stunden mit vorangestellter Null), `H` (Stunden), `mm` (Minuten mit vorangestellter Null), `m` (Minuten), `ss` (Sekunden mit vorangestellter Null), `s` (Sekunden).

- `"PT1H30M"|duration:"HH:mm:ss"` wird zu `"01:30:00"`
- `"3665"|duration:"H:mm:ss"` wird zu `"1:01:05"`
- `duration` ohne Parameter verwendet für eine Zeitdauer bis zu einer Stunde standardmäßig das Format `mm:ss`und für größere Zeitspannen `HH:mm:ss`.
- Unterstützt sowohl ISO 8601-Angaben (z.B. `PT6702S`, `PT1H30M`) als auch einfache Sekundenangaben.

## Textumwandlung und Groß-/Kleinschreibung

Konvertiert Text-Zeichenfolgen von einem Format in ein anderes.

### `camel`

Konvertiert Text nach `camelCase`.

### `capitalize`

Wandelt jeweils den ersten Buchstaben eines Wortes in einen Großbuchstaben und den Rest in Kleinbuchstaben um, z.B. `"hALLO wELT"|capitalize` wird zu `"Hallo Welt"`.

### `kebab`

Konvertiert Text nach `kebab-case`.

### `lower`

Konvertiert Text in `kleinbuchstaben`.

### `pascal`

Konvertiert Text nach `PascalCase`.

### `replace`

Ersetzt Vorkommen eines bestimmten Textes:

- Einfache Ersetzung: `"hallo, Welt!"|replace:",":""` entfernt alle Kommas.
- Mehrfache Ersetzung: `"Es werde Licht!"|replace:("L":"N","i":"a")` wird zu `"Es werde Nacht!"`.
- Ersetzungen erfolgen in der Reihenfolge, in der sie angegeben sind.
- Um eine bestimmte Zeichenfolge zu entfernen, ersetze sie mit `""`.
- Sonderzeichen wie `: | { } ( ) ' "` im Suchbegriff müssen mit Backslash escaped werden, verwende z.B. `\:`, um nach einem Doppelpunkt zu suchen.

Unterstützt reguläre Ausdrücke in JavaScript Syntax:

- Alle Vokale ersetzen: `"hallo welt"|replace:"/[aeiou]/g":"*"` → `"h*ll* w*lt".`
- Case-insensitiv: `"HALLO welt"|replace:"/hallo/i":"hi"` → `"hi welt".`
- Mehrere reguläre Ausdrücke: `"hallo welt"|replace:("/[aeiou]/g":"*","/\s+/":"-")` → `"h*ll*-w*lt"`.
- Verfügbare Flags: `g` (global), `i` (case-insensitive), `m` (multiline), `s` (dotAll), `u` (unicode), `y` (sticky).

### `safe_name`

Konvertiert Text in einen sicheren Dateinamen.

- Standardmäßig wendet `safe_name` die gebräuchlichsten Bereinigungsregeln an.
- Betriebssystemspezifische Regeln können mit `safe_name:os` angewendet werden, wobei `os` die Werte `windows`, `mac` oder `linux` annehmen kann.

### `snake`

Konvertiert Text nach `snake_case`.

### `title`

Konvertiert Text nach `Title Case`, z.B. `"hallo welt"|title` wird zu `"Hallo Welt"`.

### `trim`

Entfernt alle Leerzeichen am Anfang und Ende der Zeichenfolge.

- `"  hallo welt  "|trim` wird zu `"hallo welt"`.

### `uncamel`

Konvertiert camelCase oder PascalCase in eine Zeichenfolge, in der Wörter mit einem Leerzeichen getrennt sind und die weiter formatiert werden kann mit anderen Filtern, wie `title` oder `capitalize`.

- `"camelCase"|uncamel` returns `"camel case"`.
- `"PascalCase"|uncamel` returns `"pascal case"`.

### `upper`

Konvertiert Text in Großbuchstaben, z.B. `"hallo welt"|upper` wird zu `"HALLO WELT"`.

## Textformatierung

Du kannst auch [[Formatierungsgrundlagen|Einfaches Markdown]] und [[Erweiterte Formatierung]] auf Text anwenden.

### `blockquote` 

Fügt jeder Zeile des Eingabetextes die Markdown-Syntax für Zitate (`> `) hinzu.

### `callout`

Erzeugt ein [[Callouts|Callout]] mit optionalen Parametern: `{{variable|callout:("typ", "titel", eingeklappt)}}`

- `typ` ist der Callout-Typ (Standard: "info")
- `titel` ist der Callout-Titel, and defaults to empty
- `eingeklappt` ist ein Boolean-Wert, der festlegt, ob das Callout eingeklappt (`true`), ausgeklappt (`false`) oder nicht einklappbar (`null`) sein soll

### `footnote`

Konvertiert ein Array oder Objekt in eine Markdown-Fußnoten-Liste.

- Array: `["erstes Element","zweites Element"]|footnote` wird zu `[^1]: erstes Element` usw.
- Objekt: `{"Erste Note": "Inhalt 1", "Zweite Note": "Inhalt 2"}|footnote` wird zu `[^erste-note]: Inhalt 1` usw.

### `fragment_link`

Konvertiert Zeichenfolgen und Arrays in [Textfragment](https://developer.mozilla.org/de/docs/Web/URI/Reference/Fragment/Text_fragments)-Links. Als Linktext wird standardmäßig "link" verwendet.

- `highlights|fragment_link` wird zu `Markierter Inhalt [link](text-fragment-url)`
- `highlights|fragment_link:"Eigener Linktext"` wird zu `Markierter Inhalt [Eigener Linktext](text-fragment-url)`

### `image` 

Konvertiert Zeichenfolgen, Arrays und Objekte in Markdown-Syntax für Bilder.

- Zeichenfolge: `"bild.jpg"|image:"alt text"` wird zu `![alt text](bild.jpg)`.
- Array: `["bild1.jpg","bild2.jpg"]|image:"alt text"` erzeugt ein Array mit Bildeinträgen im Markdown-Format mit demselben alternativen Text für alle Bilder.
- Objekt: `{"bild1.jpg": "Alt 1", "bild2.jpg": "Alt 2"}|image` erzeugt Bildeinträge im Markdown-Format mit den entsprechenden Alternativtexten für jedes Bild.

### `link`

Konvertiert Zeichenfolgen, Arrays und Objekte in Markdown-Links (nicht zu verwechseln mit [[Filter#`wikilink`|Wikilinks]]).

- Zeichenfolge: `"url"|link:"autor"` wird zu `[autor](url)`.
- Array: `["url1","url2"]|link:"autor"` erzeugt ein Array mit Markdown-Links mit demselben Linktext für alle Links.
- Objekt: `{"url1": "Author 1", "url2": "Author 2"}|link` erzeugt Markdown-Links mit dem jeweiligen Schlüsselwert als Linktext.

### `list`

Konvertiert ein Array in eine Markdown-Liste.

- `list` erzeugt eine einfache, ungeordnete Liste.
- `list:task` erzeugt eine Aufgabenliste.
- `list:numbered` erzeugt eine nummerierte Liste.
- `list:numbered-task` erzeugt eine nummerierte Aufgabenliste.

### `table`

Konvertiert ein Array in eine [[Erweiterte Formatierung#Tabellen|Markdown-Tabelle]]:

- Array mit Objekten: die Objektschlüssel werden als Spaltenüberschrift verwendet.
- Array mit Arrays: erzeugt eine Tabelle mit den verschachtelten Arrays als Zeilen.
- Einfaches Array: erzeugt eine einspaltige Tabelle mit "Value" als Spaltenüberschrift.
- So legst du benutzerdefinierte Spaltenüberschriften fest: `table:("Spalte 1", "Spalte 2", "Spalte 3")`. Bei Verwendung mit einem einfachen Array werden die Daten automatisch gemäß der angegebenen Spaltenanzahl in Zeilen aufgeteilt.

### `wikilink`

Konvertiert Zeichenfolgen, Arrays und Objekte in Obsidian-[[Verlinke Notizen|Wikilinks]].

- Zeichenfolge: `"seite"|wikilink` wird zu `[[seite]]`.
- Zeichenfolge mit Alias: `"seite"|wikilink:"alias"` wird zu `[[seite|alias]]`.
- Array: `["seite1","seite2"]|wikilink` erzeugt ein Array mit Wikilinks ohne Alias.
- Array mit Alias: `["seite1","seite2"]|wikilink:"alias"` erzeugt ein Array mit Wikilinks, alle mit demselben Alias.
- Objekt: `{"seite1": "alias1", "seite2": "alias2"}|wikilink` erzeugt Wikilinks mit den Schlüsselwerten als Alias.

## Zahlen

### `calc`

Wendet einfache arithmetische Operationen auf Zahlenwerte an.

- Unterstützte Operatoren: `+`, `-`, `*`, `/`, `**` (bzw. `^`) für Potenzierung.
- Beispiel: `5|calc:"+10"` ergibt `15`.
- Beispiel: `2|calc:"**3"` ergibt `8` (Kubikrechnung).
- Wenn der Eingabewert kein Zahlenwert ist, wird die ursprüngliche Zeichenfolge unverändert zurückgegeben.

### `length`

Gibt die Länge von Zeichenfolgen und Arrays bzw. die Anzahl der Schlüssel in Objekten zurück.

- Zeichenfolge: `"hallo"|length` ergibt `5`.
- Array: `["a","b","c"]|length` ergibt `3`.
- Objekt: `{"a":1,"b":2}|length` ergibt `2`.

### `round`

Rundet eine Zahl auf die nächste Ganzzahl bzw. den Zahlenwert mit der definierten Anzahl an Nachkommastellen.

- Ohne Parameter: `3.7|round` ergibt `4`.
- Anzahl der Nachkommastellen als Parameter: `3.14159|round:2` ergibt `3.14`.

## HTML-Verarbeitung

Du kannst HTML-Inhalte verarbeiten und in Markdown umwandeln. Beachte, dass deine Eingabe-[[Variablen|Variable]] HTML enthalten muss, bspw. indem du Variablen wie `{{fullHtml}}`, `{{contentHtml}}` oder `{{selectorHtml:}}` verwendest.

### `markdown` 

Konvertiert eine Zeichenfolge in [[Obsidian Flavored Markdown]].

- Hilfreich in Kombination mit Variablen wie `{{contentHtml}}`, `{{fullHtml}}` oder Selektor-Variablen, z.B. `{{selectorHtml:cssSelector}}`.

### `remove_attr` 

Entfernt nur die angegebenen Attribute aus HTML-Elementen.

- Beispiel: `"<div class="test" id="beispiel">Inhalt</div>"|remove_attr:"class"` wird zu `<div id="beispiel">Inhalt</div>`.
- Mehrere Attribute: `{{fullHtml|remove_attr:("class,style,id")}}`

### `remove_html`

Entfernt die angegebenen HTML-Elemente und deren Inhalt aus einer Zeichenfolge.

- Unterstützt Element-Bezeichner, Klasse oder ID, z.B. `{{fullHtml|remove_html:("img,.class-name,#element-id")}}`
- Um nur HTML-Tags oder Attribute zu entfernen, aber den Inhalt beizubehalten, kannst du die Filter `strip_tags` bzw. `strip_attr` verwenden.

### `remove_tags` 

Entfernt nur die angegebenen HTML-Tags, behält aber den Inhalt bei.

- Beispiel: `"<p>Hallo <b>Welt</b>!</p>"|remove_tags:"b"` wird zu `"<p>Hallo Welt!</p>"`.
- Mehrere Tags: `{{fullHtml|remove_tags:("a,em,strong")}}`

### `replace_tags`

Ersetzt HTML-Tags und behält dabei den Inhalt sowie die Attribute bei.

- `{{fullHtml|replace_tags:"strong":"h2"}}` ersetzt alle `<strong>`-Tags mit `<h2>`.

### `strip_attr`

Entfernt **alle** HTML-Attribute aus einer Zeichenfolge.

- Verwende den Filter mit Parametern, bspw. `strip_attr:("class, id")`, um  bestimmte Attribute zu behalten.
- Beispiel: `"<div class="test" id="beispiel">Inhalt</div>"|strip_attr:("class")` wird zu `<div id="beispiel">Inhalt</div>`.

### `strip_md`

Entfernt Markdown-Formatierung **vollständig** und gibt Klartext zurück, z.B. wird `**text**` zu `text`.

- Wandelt formatierten in unformatierten Klartext um, einschließlich Fettdruck, Kursivschrift, Hervorhebungen, Überschriften, Quellcode, Blockzitate, Tabellen, Aufgabenlisten und Wikilinks.
- Entfernt Tabellen, Fußnoten, Bilder und HTML-Elemente vollständig.

### `strip_tags`

Entfernt **alle** HTML-Tags aus einer Zeichenfolge, wobei der Inhalt beibehalten wird.

- Verwende den Filter mit Parametern, z.B. `strip_tags:("p,strong,em")`, um bestimmte Tags beizubehalten.
- Beispiel: `"<p>Hallo <b>Welt</b>!</p>"|strip_tags:("b")` wird  zu `Hallo <b>Welt</b>!`.

## Arrays und Objekte

Du kannst Arrays und Objekte verarbeiten.

### `first` 

Gibt das erste Element eines Arrays als Zeichenfolge zurück.

- `["a","b","c"]|first` wird zu `"a"`.
- Wurde kein Array übergeben, wird die Eingabe unverändert zurückgegeben.

### `join`

Kombiniert Elemente eines Arrays zu einer Zeichenfolge.

- `["a","b","c"]|join` wird zu `"a,b,c"`.
- Mit definiertem Trennzeichen: `["a","b","c"]|join:" "` wird zu `"a b c"`. Verwende `join:"\n"`, um Elemente durch einen Zeilenumbruch zu trennen.
- Beispiel mit vorangegangenem `split` und `slice`: `"a,b,c,d"|split:","|slice:1,3|join:" "` wird zu `"b c"`.

### `last`

Gibt das letzte Element eines Arrays als Zeichenfolge zurück.

- `["a","b","c"]|last` wird zu `"c"`.
- Wurde kein Array übergeben, wird die Eingabe unverändert zurückgegeben.

### `map`

Wendet eine Transformation auf jedes Element eines Arrays an, wobei folgende Syntax verwendet wird: `map:item => item.property` bzw. `map:item => item.nested.property` für verschachtelte Eigenschaften.

- `[{juwel: "Obsidian", farbe: "schwarz"}, {juwel: "Amethyst", farbe: "violett"}]|map:item => item.juwel` wird zu `["Obsidian", "Amethyst"]`.
- Verwende Klammern für Objektliterale und komplexe Ausdrücke: `map:item => ({key: value})`
- Beispiel:`[{juwel: "Obsidian", farbe: "schwarz"}, {juwel: "Amethyst", farbe: "violett"}]|map:item => ({name: item.juwel, farbe: item.farbe})`  wird  zu `[{name: "Obsidian", farbe: "schwarz"}, {name: "Amethyst", farbe: "violett"}]`.

Unterstützt String-Literale und wandelt diese automatisch in ein Objekt mit der Eigenschaft `str`. Die Eigenschaft `str` wird verwendet, um das Ergebnis der Transformation von String-Literalen zu speichern, z.B. `["rock", "pop"]|map:item => "genres/${item}"` returns `[{str: "genres/rock"}, {str: "genres/pop"}]`.

Du kannst `map` mit dem Filter `template` kombinieren, z.B. `map:item => ({name: ${item.gem}, farbe: item.farbe})|template:"- ${name} ist ${farbe}\n"`.

### `merge`

Fügt einem Array neue Werte hinzu.

- Array: `["a","b"]|merge:("c","d")` wird zu `["a","b","c","d"]`.
- Einzelwert: `["a","b"]|merge:"c"` wird zu `["a","b","c"]`.
- Wurde kein Array übergeben, wird ein neuer Array erzeugt: `"a"|merge:("b","c")` wird zu `["a","b","c"]`.
- Verwendung von Anführungszeichen: `["a"]|merge:('b,"c,d",e')` wird zu `["a","b","c,d","e"]`.

### `nth`

Behält die n-ten Elemente in einem Array unter Verwendung von CSS-Syntax "nth-child" und Gruppenmustern. Positionen sind 1-basiert, das heißt, das erste Element ist an Position 1.

- `array|nth:3` behält nur das 3. Element bei.
- `array|nth:3n` behält jedes 3. Element bei (3, 6, 9 usw.).
- `array|nth:n+3` behält alle Elemente ab einschließlich dem 3. bei.

Gruppenmuster für sich wiederholende Strukturen:

- `array|nth:1,2,3:5` behält die Positionen 1, 2, 3 aus jeder Gruppe von 5 Elementen.
- Beispiel: `[1,2,3,4,5,6,7,8,9,10]|nth:1,2,3:5` wird zu `[1,2,3,6,7,8]`.

### `object`

Manipuliert Daten in Objekten.

- `object:array` konvertiert ein Objekt in ein Array mit Schlüssel-Wert-Paaren.
- `object:keys` erzeugt ein Array aus den Objekt-Schlüsseln.
- `object:values` erzeugt ein Array aus den Objekt-Werten.
- Beispiel: `{"a":1,"b":2}|object:array` wird zu `[["a",1],["b",2]]`.

### `slice`

Extrahiert einen Teil einer Zeichenfolge oder eines Arrays.

- Zeichenfolge: `"hallo"|slice:1,4` wird  zu `"all"`.
- Array: `["a","b","c","d"]|slice:1,3` wird zu `["b","c"]`.
- Wurde nur ein Parameter übergeben, wird von diesem Null-basierten Index bis zum Ende ausgeschnitten: `"hallo"|slice:2` wird zu `"llo"`.
- Negative Indizes zählen vom Ende aus: `"hello"|slice:-3` wird zu `"llo"`.
- Der zweite Parameter ist exklusiv, das heißt, der Ausschnitt endet vor diesem Index: `"hallo"|slice:1,4` beinhaltet die Zeichen am Index 1, 2 und 3, siehe oben.
- Ein negativer zweiter Parameter schließt die Anzahl der Zeichen vom Ende an aus: `"hallo"|slice:0,-2` wird zu `"hal"`.

### `split`

Teilt eine Zeichenfolge in ein Array von Teilzeichenfolgen auf.

- `"a,b,c"|split:","` wird zu `["a","b","c"]`.
- `"hallo welt"|split:" "` wird zu `["hallo","welt"]`.
- Wurde kein Trennzeichen angegeben, wird die Zeichenfolge in einzelne Zeichen aufgeteilt: `"hallo"|split` wird zu `["h","a","l","l","o"]`.
- Als Trennzeichen können auch reguläre Ausdrücke verwendet werden: `"a1b2c3"|split:[0-9]` wird zu `["a","b","c"]`.

### `template`

Wendet eine Vorlagenzeichenfolge auf ein Objekt oder ein Array mit Objekten an unter Verwendung der Syntax `object|template:"Vorlage mit ${variable}"`.

- Verschachtelte Eigenschaften: `{"juwel":{"name":"Obsidian"}}|template:"${juwel.name}"` wird zu `"Obsidian"`.
- Objekt: `{"juwel":"Obsidian","haerte":5}|template:"${juwel} hat eine Härte von ${haerte}"` wird zu `"Obsidian hat eine Härte von 5"`.
- Array: `[{"juwel":"Obsidian","haerte":5},{"juwel":"Amethyst","haerte":7}]|template:"- ${juwel} hat eine Härte von ${haerte}\n"` erzeugt eine formatierte Liste.

Funktioniert mit String-Literalen aus `map`, indem auf die Eigenschaft `str` zugegriffen wird:

- Beispiel: `["rock", "pop"]|map:item => "genres/${item}"|template:"${str}"` wird zu `"genres/rock\ngenres/pop"`.
- Die Eigenschaft `str` wird standardmäßig verwendet, wenn `template` auf Objekte angewendet wird, die mit `map` und String-Literalen erstellt wurden.

### `unique`

Entfernt doppelte Werte aus Arrays bzw. Objekten.

- einfaches Array: `[1,2,2,3,3]|unique` wird zu `[1,2,3]`.
- Array mit Objekten: `[{"a":1},{"b":2},{"a":1}]|unique` wird zu `[{"a":1},{"b":2}]`.
- Bei Objekten werden Einträge mit doppelten Werten entfernt, wobei der Schlüssel des letzten Vorkommens beibehalten wird.
- Zeichenfolgen werden unverändert zurückgegeben.