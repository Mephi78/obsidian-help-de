---
permalink: web-clipper/variablen
publish: true
---

[[Obsidian Web Clipper/Vorlagen|Web Clipper-Vorlagen]] verwenden Variablen, um Daten von einer Webseite automatisch in eine Notiz einzufügen. Variablen können für den **Notiznamen**, **Notiz-Speicherort**, **Eigenschaften** sowie den **Notiz-Inhalt** verwendet werden. Variablen können mit Hilfe von [[Filter|Filtern]] auch verändert werden.

Über die Option **Seitenvariablen anzeigen** (`...`) in der [[Einführung in Obsidian Web Clipper|Browsererweiterung]] findest du eine Liste aller Variablen der aktiven Webseite, die du in einer Vorlage verwenden kannst.

Es gibt fünf Typen von Variablen:

- [[#Voreingestellte Variablen]]
- [[#Prompt-Variablen]]
- [[#Meta-Variablen]]
- [[#Selektor-Variablen]]
- [[#Schema.org-Variablen]]

## Voreingestellte Variablen

Voreingestellte Variablen werden basierend auf dem Seiteninhalt automatisch generiert. Sie funktionieren in der Regel für die meisten Webseiten.

Die hauptsächliche Variable für den Seiteninhalt ist `{{content}}`. Sie enthält den Inhalt des Artikels, die [[Webseiten markieren|Markierungen]] oder die Auswahl, falls auf der Webseite Elemente ausgewählt wurden. Beachte, dass `{{content}}` versucht, den Hauptinhalt der Webseite zu extrahieren, was möglicherweise nicht immer von dir gewünscht ist. In diesem Fall kannst du andere voreingestellte oder Selektor-Variablen verwenden, um den von dir gewünschten Inhalt zu extrahieren.

| Variable            | Beschreibung                                                                         |
| ------------------- | ------------------------------------------------------------------------------------ |
| `{{author}}`        | Autor der Webseite                                                                   |
| `{{content}}`       | Artikelinhalt, [[Webseiten markieren\|Markierungen]] oder Auswahl im Markdown-Format |
| `{{contentHtml}}`   | Artikelinhalt, [[Webseiten markieren\|Markierungen]] oder Auswahl im HTML-Format     |
| `{{date}}`          | Aktuelles Datum (Formatierung mittels `date`-Filter möglich)                         |
| `{{description}}`   | Beschreibung oder Auszug                                                             |
| `{{domain}}`        | Domäne                                                                               |
| `{{favicon}}`       | Favicon-URL                                                                          |
| `{{fullHtml}}`      | Unbearbeiteter HTML-Inhalt der gesamten Seite                                        |
| `{{highlights}}`    | [[Webseiten markieren\|Markierungen]] mit Text und Zeitstempel                       |
| `{{image}}`         | URL für Social-Media-Vorschau-Bild                                                   |
| `{{published}}`     | Veröffentlichungsdatum (Formatierung mittels `date`-Filter möglich)                  |
| `{{selection}}`     | Auswahl im Markdown-Format                                                           |
| `{{selectionHtml}}` | Auswahl im HTML-Format                                                               |
| `{{site}}`          | Name der Webseite oder Herausgeber                                                   |
| `{{title}}`         | Titel der Webseite                                                                   |
| `{{time}}`          | Aktuelles Datum und Uhrzeit                                                          |
| `{{url}}`           | Aktuelle URL                                                                         |
| `{{words}}`         | Anzahl der Wörter                                                                    |

## Prompt-Variablen

Prompt-Variablen nutzen Sprachmodelle, um Daten mittels natürlicher Sprache zu extrahieren und zu ändern. Für deren Verwendung muss die [[Webseiten interpretieren|Interpreter]]-Funktion aktiviert und konfiguriert sein.

Prompt-Variablen verwenden die Syntax `{{"eine Zusammenfassung der Seite"}}`. Die doppelten Anführungsstriche um den Prompt-Text sind wichtig, sie dienen der Unterscheidung von Prompts und voreingestellten Variablen. Prompt-Antworten können mit [[Filter|Filtern]] nachbearbeitet werden, z.B. `{{"eine Zusammenfassung der Seite"|blockquote}}`.

### Verwendung von Prompt-Variablen

Prompt-Variablen haben den Vorteil, dass sie einfach zu schreiben und äußerst flexibel sind, dennoch gibt es auch einige Nachteile: Ihre Ausführung dauert länger und sie können je nach von dir gewähltem [[Webseiten interpretieren#Modelle|Anbieter]] Kosten verursachen oder den Datenschutz beeinträchtigen.

Im Gegensatz zu anderen Variablentypen müssen Prompt-Variablen durch ein externes Sprachmodell verarbeitet werden, so dass sie erst nach Ausführung der [[Webseiten interpretieren|Interpreter]]-Funktion ersetzt werden.

Es ist empfohlen, auf die Verwendung von Prompt-Variablen zu verzichten, wenn die zu extrahierenden Daten in einem konsistenten Format vorliegen, das mit einem der anderen Variablentypen erfasst werden kann.

Prompt-Variablen können andererseits nützlich sein, wenn die zu extrahierenden Daten auf verschiedenen Webseiten ein uneinheitliches Format haben. Du kannst dir bspw. eine [[Obsidian Web Clipper/Vorlagen|Vorlage]] erstellen, die Notizen zu Büchern unabhängig von der Quell-Webseite in einem einheitlichen Format speichert. Prompt-Variablen wie `{{"Autor des Buches"}}` dürften auf jeder Buchwebseite funktionieren, während spezielle Selektor-Variablen in der Regel nur für bestimmte Webseiten funktionieren.

### Beispiele

Prompts können fast jede Abfrage in natürlicher Sprache verwenden. In Abhängigkeit vom verwendeten Sprachmodell können Prompts Daten in verschiedenen Sprachen abfragen oder übersetzen.

- `{{"eine Zusammenfassung in drei Stichpunkten, übersetzt ins Französische"}}` extrahiert Stichpunkte zu einer Webseite und übersetzt diese auf Französisch.
- `{{"un resumé de la page en trois points"}}` extrahiert eine Webseite mittels Prompt in französischer Sprache.

Prompts können Seiteninhalte in JSON konvertieren, das wiederum mit [[Filter|Filtern]] manipuliert werden kann. Ein Beispiel:

%% A.d.Ü.: wie wird das Image-Array verarbeitet? %%

```
{{"erzeuge ein JSON-Objekt für jeden Tweet, das den Autor, Tweet-Text, das Datum im Format YYYY-MM-DD und ein Array mit Bildern (falls vorhanden) enthält"|map:tweet => ({text: tweet.Tweet-Text, autor: tweet.Autor, datum: tweet.Datum})|template:"${text}\n— [[@${autor}]], [[${datum}]]\n"}}
```


## Meta-Variablen

Mit Meta-Variablen kannst du [Metadaten](https://developer.mozilla.org/de/docs/Web/HTML/Reference/Elements/meta) aus einer Webseite extrahieren, einschließlich [Open Graph](https://ogp.me/)-Daten zur Erstellung einer Social-Media-Vorschau.

- `{{meta:name}}` gibt den `content`-Wert für den entsprechenden Metadatennamen zurück, z.B. `{{meta:name:description}}` für die Meta-Beschreibung.
- `{{meta:property}}` gibt den `content`-Wert für die entsprechende Open Graph Meta-Eigenschaft zurück, bspw. `{{meta:property:og:title}}` für den Meta-Tag `og:title`.

## Selektor-Variablen

Mit Selektor-Variablen kannst du über [CSS-Selektoren](https://developer.mozilla.org/de/docs/Web/CSS/Guides/Selectors/Selectors_and_combinators) Textinhalte aus einer Webseite extrahieren.

Die Syntax lautet `{{selector:cssSelector?attribute}}`, `?attribute` ist optional. Ist kein Attribut angegeben, wird der Textinhalt des Elements extrahiert. Du kannst `{{selectorHtml:cssSelector}}` auch verwenden, um den HTML-Inhalt eines Elements auszulesen. Selektor-Variablen funktionieren in der Regel am besten auf spezifischen Webseiten mit einer einheitlichen HTML-Struktur.

- `{{selector:h1}}` extrahiert den Text aller `h1`-Überschriften der Webseite.
- `{{selector:.autor}}` extrahiert den Textinhalt von `.autor`-Elementen.
- `{{selector:img.held?src}}` extrahiert das `src`-Attribut für Bilder mit der Klasse `held`.
- `{{selector:a.main-link?href}}` extrahiert das `href`-Attribut eines Link-Elementes mit der Klasse `main-link`.
- `{{selectorHtml:body|markdown}}` extrahiert das gesamte HTML-`body`-Element und konvertiert es ins Markdown-Format mit dem `markdown`-[[Filter#HTML-Verarbeitung|Filter]].
- Für spezifischere Abfragen werden auch verschachtelte CSS-Selektoren und Kombinatoren unterstützt.
- Wenn mehrere Elemente mit dem Selektor übereinstimmen, wird ein Array zurückgegeben, den du mit [[Filter#Arrays und Objekte|Array- und Objektfiltern]] wie `join` oder `map` verarbeiten kannst.

## Schema.org-Variablen

Mit Schema-Variablen kannst du mit [Schema.org](https://schema.org/) JSON-LD annotierte Daten aus einer Webseite extrahieren. Schema.org-Daten können auch verwendet werden, um eine [[Obsidian Web Clipper/Vorlagen#Verwendung von Schema.org|Vorlage automatisch auszulösen]].

- `{{schema:@Type:key}}` extrahiert den Schlüsselwert eines Schemas.
- `{{schema:@Type:parent.child}}` extrahiert den Wert einer verschachtelten Eigenschaft.
- `{{schema:@Type:arrayKey}}` extrahiert das erste Element eines Arrays.
- `{{schema:@Type:arrayKey[index].property}}` extrahiert das Array-Element am spezifizierten Index eines Arrays.
- `{{schema:@Type:arrayKey[*].property}}` extrahiert eine bestimmte Eigenschaft aus allen Elementen eines Arrays.

Du kannst auch die Kurzschreibweise verwenden, ohne den Schematyp zu spezifizieren:

- `{{schema:autor}}` findet die erste Eigenschaft `autor` in einem beliebigen Schematyp.
- `{{schema:name}}` findet die erste Eigenschaft `name` in einem beliebigen Schematyp.

Die Kurzschreibweise eignet sich, wenn du nach einer bestimmten Eigenschaft suchst, aber den Schematyp nicht kennst bzw. dieser egal ist.

Verschachtelte Eigenschaften und Array-Zugriff funktionieren beide mit und ohne spezifiziertem Schema-`@Type`:

- `{{schema:autor.name}}` findet die erste Eigenschaft `autor` und greift auf deren Untereigenschaft `name` zu.
- `{{schema:autor[0].name}}` findet die Eigenschaft `name` vom ersten `autor` in einem Array mit Autoren.
- `{{schema:autor[*].name}}` extrahiert einen Array mit Autoren-Namen.

