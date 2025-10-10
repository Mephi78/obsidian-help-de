---
permalink: plugins/suche
---

Die *Suche* ist eine [[Standarderweiterungen|Standarderweiterung]], mit der du Daten in deinem Vault finden kannst, indem du Suchbegriffe und Operatoren verwendest, um die Ergebnisse einzugrenzen.

Standardmäßig findest du die *Suche* ( ![[lucide-search.svg#icon]] ) in der linken Seitenleiste. Du kannst sie mit dem Tastenkürzel `Strg + Umschalt + F` (oder `Cmd + Umschalt + F` unter macOS) aufrufen.

- **Suche nach selektiertem Text**: Selektiere Text im Editor und öffne dann die Suche über das Tastenkürzel, um nach der Auswahl zu suchen.
- **Kürzlich verwendete Suchbegriffe**: Wird die Suche ohne Suchbegriff geöffnet, erscheint eine Liste mit den kürzlich verwendeten Suchbegriffen, die du anklicken kannst, um die Ergebnisliste erneut anzuzeigen.

## Suchbegriffe

Ein Suchbegriff ist das Wort oder die Wortgruppe, die du im Suchfeld eingibst. Wenn du lernst, effektive Suchbegriffe zu formulieren, kannst du selbst in großen Vaults schneller fündig werden. Obsidian durchsucht nur den Inhalt von Notizen und Canvas-Dateien.

> [!tip] Dateinamen und -pfade
> Standardmäßig durchsucht Obsidian nur die Dateinamen und -pfade von Notizen und Canvas-Dateien. Um nach anderen Dateitypen in deinem Vault zu suchen, verwende die Operatoren `path` oder `file`.

Die *Suche* findet alle Einzelübereinstimmungen mit den Wörtern im Suchfeld. Möchtest du eine zusammenhängende Wortgruppe finden, schreibe diese in Anführungszeichen, z.B. `"Star Wars"`. Enthält dein Suchbegriff selbst Anführungsstriche, kannst du diese _escapen_ mit einem Backslash (`\`), z. B. `"sie sagten \"Hallo\" zueinander"`.

Du kannst festlegen, ob du Dateien finden möchtest, die *alle* oder *wenigstens eines* der Wörter des Suchterms enthalten:

- `Besprechung Arbeit` listet Dateien auf, die beide Begriffe, `Besprechung` und `Arbeit`, enthalten.
- `Besprechung OR Arbeit` listet Dateien auf, die `Besprechung` oder `Arbeit` enthalten.

Du kannst beides auch in einem Suchterm kombinieren:

- `Besprechung Arbeit OR Treffen persönlich` listet Dateien zu Arbeitsbesprechungen und persönlichen Treffen auf.

Verwende Klammern, um die Priorität zu steuern:

- `Besprechung (Arbeit OR Treffen) persönlich` listet Dateien auf, die `Besprechung`, `persönlich` und entweder `Arbeit` oder `Treffen` enthalten.

Um das Vorkommen eines Wortes in den Suchergebnissen auszuschließen, setze ein Minus (`-`) davor:

- `Besprechung -Arbeit` listet Dateien auf, die `Besprechung` enthalten, aber nicht `Arbeit`.

Du kannst mehrere Wörter ausschließen:

- `Besprechung -Arbeit -Treffen` listet Dateien auf, die `Besprechung`, aber weder `Arbeit` noch `Treffen` enthalten.

Verwende Klammern, um Wortkombinationen auszuschließen:

- `Besprechung -(Arbeit Treffen)` listet Dateien auf, die `Besprechung`, aber nicht gleichzeitig `Arbeit` und `Treffen` enthalten.

> [!tip] Suchbegriff erklären
> Wenn du einen komplexen Suchterm verstehen möchtest, aktiviere **Suchbegriff erklären** in den Sucheinstellungen ( ![[lucide-sliders-horizontal.svg#icon]] ) für eine Erklärung deiner Eingabe im Suchfeld.

## Suchoperatoren

Suchoperatoren ermöglichen detailliertere Suchbegriffe, um die Suchergebnisse noch besser zu filtern.

Einige Operatoren erlauben das Hinzufügen von verschachtelten Suchbegriffen in Klammern, bspw. `task:(Anruf OR Mail)`.

| Suchoperator   | Beschreibung                                                                                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `file:`        | Sucht Text im Dateinamen. Gilt für jede Datei im Vault. <p/>z.B. `file:.jpg` oder `file:202209`.                                                                                                                                                                                                                                      |
| `path:`        | Sucht Text im Dateipfad. Gilt für jede Datei im Vault.<p/>z.B. `path:"Tagebuch/2022-07"`.                                                                                                                                                                                                                                             |
| `content:`     | Sucht Text im Dateiinhalt.<p/>z.B. `content:"Geburstag"`.                                                                                                                                                                                                                                                                             |
| `match-case:`  | Case-sensitive Suche.<p/>z.B. `match-case:GmbH`.                                                                                                                                                                                                                                                                                      |
| `ignore-case:` | Case-insensitive Suche.<p/>z.B. `ignore-case:gmbh`.                                                                                                                                                                                                                                                                                   |
| `tag:`         | Sucht Tag in einer Datei.<p/>z.B. `tag:#aufgabe`.<p/>Beachte, dass die Suche nach `tag:#aufgabe` keine Ergebnisse für `#arbeit/aufgabe` findet.<br /><br />**Hinweis**: Da `tag:` Quellcode-Blöcke und nicht-Markdown-Inhalte ignoriert, ist dieser Suchoperator meist schneller und genauer, als eine Volltextsuche nach `#aufgabe`. |
| `line:`        | Sucht Dateien, in denen mindestens eine Zeile mit dem Suchbegriff übereinstimmt.<p/>z.B. `line:(dokumentiere Quellcode)`.<p/><br>**Hinweis:** `-line` negiert die Suche, so dass nur Dateien gelistet werden, in denen keine Zeile mit dem Suchbegriff übereinstimmt.                                                                 |
| `block:`       | Sucht Übereinstimmungen im selben Block.<p/>z.B. `block:(Hund Katze)`.<p/>**Hinweis**: `block:` bewirkt, dass die *Suche* jede Markdown-Datei parst, weshalb die Verwendung dieses Operators zu längeren Wartezeiten führen kann.                                                                                                     |
| `section:`     | Sucht Übereinstimmungen im selben Absatz (Text zwischen zwei Überschriften).<p/>z.B. `section:(Hund Katze)`.                                                                                                                                                                                                                          |
| `task:`        | Sucht Übereinstimmungen in [[Formatierungsgrundlagen#Aufgabenlisten\|Aufgaben]] mittels blockweiser Verarbeitung.<p/>z.B. `task:anrufen`.                                                                                                                                                                                             |
| `task-todo:`   | Sucht Übereinstimmungen in *offenen* [[Formatierungsgrundlagen#Aufgabenlisten\|Aufgaben]] mittels blockweiser Verarbeitung.<p/>z.B. `task-todo:anrufen`.                                                                                                                                                                              |
| `task-done:`   | Sucht Übereinstimmungen in *abgeschlossenen* [[Formatierungsgrundlagen#Aufgabenlisten\|Aufgaben]] mittels blockweiser Verarbeitung.<p/>z.B. `task-done:anrufen`.                                                                                                                                                                      |

## Suche nach Eigenschaften

Du kannst in [[Eigenschaften]] gespeicherte Daten im Suchterm verwenden.

Schreibe den Eigenschaftsnamen in eckige Klammern `[eigenschaft]`, um Dateien zu finden, die diese Eigenschaft enthalten:

- `[aliases]` listet Dateien, die die Eigenschaft `aliases` enthalten
  
Verwende eckige Klammern und einen Doppelpunkt `[eigenschaft:wert]`, um nach bestimmten Eigenschaftswerten zu suchen:

- `[aliases:Name]` listet Dateien, deren `aliases`-Eigenschaft auf `Name` gesetzt ist

Eigenschaft, wie auch Wert erlauben die Verwendung von Unterabfragen. Verwende Klammern zum Gruppieren, den `OR`-Operator, Anführungsstriche für exakte Übereinstimmungen oder reguläre Ausdrücke.

- `[status:Entwurf OR Veröffentlicht]` findet z.B. Dateien, deren `status`-Eigenschaft entweder auf `Entwurf` oder `Veröffentlicht` gesetzt ist

## Case-Sensitivity ändern

Standardmäßig arbeitet die *Suche* case-insensitiv. Wenn die Ergebnisliste Groß-/Kleinschreibung berücksichtigen soll, klicke auf **Großschreibung beachten** ( ![[obsidian-icon-upper-lowercase.svg#icon]] ) rechts im Suchfeld.

Diese Einstellung kann umgeschaltet werden. Wenn das **Großschreibung beachten**-Symbol farblich hervorgehoben ist, wird eine case-sensitive Suche durchgeführt.

## Sortierung der Ergebnisse ändern

1. Gib einen [[#Suchbegriffe|Suchbegriff]] ein.
2. Klicke unter dem Suchfeld auf das das Dropdown-Menü rechts.
3. Wähle die Regel aus, nach der die Ergebnisliste sortiert werden soll. Standardmäßig wird nach "Dateiname (A - Z)" sortiert.

Folgende Sortieroptionen sind verfügbar:

- Dateiname (A - Z)
- Dateiname (Z - A)
- Letzte Bearbeitung (neu - alt)
- Letzte Bearbeitung (alt - neu)
- Erstellungszeitpunkt (neu - alt)
- Erstellungszeitpunkt (alt - neu)

## Suchergebnisse kopieren

1. Gib einen [[#Suchbegriffe|Suchbegriff]] ein.
2. Klicke unter dem Suchfeld auf das Drei-Punkte-Symbol neben der Anzahl der Ergebnisse.
3. Wähle **Suchergebnisse kopieren**.

## Reguläre Ausdrücke verwenden

Ein regulärer Ausdruck besteht aus einer Reihe von Zeichen, die ein Textmuster beschreiben. Um reguläre Ausdrücke im Suchbegriff zu verwenden, umschließe den Ausdruck mit Schrägstrichen (`/`).

- `/\d{4}-\d{2}-\d{2}/` findet Übereinstimmungen mit einem ISO 8601 Datum, bspw. 2022-01-01.

Du kannst reguläre Ausdrücke mit Suchoperatoren kombinieren:

- `path:/\d{4}-\d{2}-\d{2}/` findet Dateien mit einem Datum im Dateipfad.

Mehr Informationen über reguläre Ausdrücke findest du in FreeCodeCamp's [Practical Regex Guide](https://www.freecodecamp.org/news/practical-regex-guide-with-real-life-examples/) oder in [Reguläre Ausdrücke](https://developer.mozilla.org/de/docs/Web/JavaScript/Guide/Regular_expressions) von Mozilla.

> [!note] Hinweis
> Reguläre Ausdrücke gibt es in verschiedenen Varianten, die sich voneinander unterscheiden können. Obsidian verwendet den JavaScript-Stil für reguläre Ausdrücke.

## Suche konfigurieren

Um die Suche zu konfigurieren, klicke neben dem Suchfeld auf **Sucheinstellungen** ( ![[lucide-sliders-horizontal.svg#icon]] ).

| Einstellung               | Beschreibung                                                                                       |
| ------------------------- | -------------------------------------------------------------------------------------------------- |
| **Ergebnisse einklappen** | Suchkontext ein-/ausklappen.                                                                       |
| **Mehr Kontext anzeigen** | Erweitert die Suchergebnisse, so dass mehr Text um übereinstimmende Begriffe herum angezeigt wird. |
| **Suchbegriff erklären**  | Zerlegt die Suchbegriffe und erklärt sie in einfacher Sprache.                                     |

## Suchergebnisse in Notiz einbinden

Um Suchergebnisse in eine Notiz einzubinden, füge einen `query`-Block ein:

````
```query
embed OR search
```
````

[[Einführung in Obsidian Publish|Obsidian Publish]] unterstützt keine eingebetteten [[Publish limitations#Search|Suchergebnisse]].

Um ein zur Laufzeit gerendertes Beispiel zu sehen, füge testweise den obigen Quellcode-Block in deinem Vault ein.

![[search-query-rendered.png#]]
