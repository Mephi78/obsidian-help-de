---
permalink: bases/funktionen
publish: true
---

Funktionen werden in [[Einführung in Bases|Bases]] verwendet, um [[Eigenschaften|Eigenschaftswerte]] in Formeln und Filtern zu manipulieren. Weitere Informationen zur Verwendung von Funktionen findest du in der [[Bases Syntax|Bases Syntaxreferenz]].

Bases unterscheidet [[Funktionen#Global|globale Funktionen]], die eigenständig verwendet werden können und solchen Funktionen, die einen Wert voraussetzen, der einem der hier aufgelisteten [[Eigenschaften#Eigenschaftstypen|Typen]] entspricht und die mittels Punkt-Notation aufgerufen werden in der Form `wert.funktion()`:

- [[Funktionen#Beliebig|Beliebig]]
- [[Funktionen#Datei|Datei]]
- [[Funktionen#Datum|Datum]]
- [[Funktionen#Link|Link]]
- [[Funktionen#Liste|Liste]]
- [[Funktionen#Objekt|Objekt]]
- [[Funktionen#Zahl|Zahl]]
- [[Funktionen#Zeichenfolge|Zeichenfolge]]
- [[Funktionen#Regulärer Ausdruck|Regulärer Ausdruck]]

## Global

Globale Funktionen werden eigenständig, ohne [[Eigenschaften|Eigenschaft]] verwendet — im Gegensatz zu allen weiteren Funktionen, die nur auf bestimmte Eigenschaftswerte angewendet werden können.

### `date()`

`date(date: string): date`

- Wandelt die übergebene Zeichenfolge in ein Datumsobjekt um.
- Erwartet einen Zeitstempel im Format `YYYY-MM-DD HH:mm:ss`.
- Beispiel: `date("2025-10-08 10:30:22")`

### `duration()`

`duration(value: string): duration`

- Wandelt eine Zeichenfolge in eine Zeitdauer um. Siehe auch [[Bases Syntax#Datumsberechnung|Datumsberechnung]].
- In Datumsberechnungen wird die Dauer automatisch geparst (z.B. `now() + '1d'`), allerdings muss eine Dauer explizit umgewandelt werden, bevor arithmetische Operationen darauf angewendet werden (z.B. `now() + (duration('1d') * 2)`).
- Für arithmetische Berechnungen mit einer Zeitdauer und einem Skalarwert muss die Dauer auf der linken Seite des Operators stehen, z.B. `duration('5h') * 2` anstelle von `2 * duration('5h')`.

### `file()`

`file(path: string | file | url): file`

- Erwartet einen Dateinamen, eine URL oder Dateipfad zu einer Datei und gibt die Entsprechung als Datei-Objekt zurück.
- Beispiel: `file(link("[[dateiname]]"))` oder `file("pfad/zur/datei")`.

### `icon()`

`icon(name: string): icon`

- Gibt einen Wert zurück, der in einer Sicht als Icon gerendert wird.
- Erwartet den Namen eines unterstützten [Lucide](https://lucide.dev)-Icons.
- Beispiel: `icon("arrow-right")`.

### `if()`

`if(condition: any, trueResult: any, falseResult?: any): any`

- `condition` ist die zu prüfende Bedingung.
- `trueResult` ist die Ausgabe, wenn die Bedingung erfüllt ist.
- `falseResult` (optional) ist die Ausgabe, wenn die Bedingung nicht erfüllt ist. Wenn nicht angegeben, wird `null` angenommen.
- Gibt `trueResult` zurück, wenn die Bedingung `condition` wahr ist, andernfalls `falseResult`.
- Beispiel: `if(isModified, "Geändert", "Unverändert")`

### `image()`

`image(path: string | file | url): image`

- Gibt ein Bild-Objekt zurück, das in der Sicht als Bild gerendert wird.
- Beispiel: `image(bild-eigenschaft)` oder `image("https://obsidian.md/images/obsidian-logo-gradient.svg")`

### `link()`

`link(path: string | file, display?: value): link`

- Wandelt eine Zeichenfolge `path` in ein Link-Objekt um, das in einer Sicht als Link zum übergebenen Dateipfad gerendert wird.
- `display` (optional) definiert den Anzeigetext des Links.

### `list()`

`list(element: any): list`

- Wenn eine Liste übergeben wurde, wird diese unverändert zurückgegeben.
- Andernfalls wird das übergebene `element` in eine Liste mit einem Listenelement umgewandelt und zurückgegeben.
- Diese Funktion ist möglicherweise hilfreich bei der Verwendung von Eigenschaften, die sowohl Listen, als auch Zeichenfolgen enthalten können.
- Beispiel: `list("value")` gibt `["value"]` zurück.

### `max()`

`max(value1: number, value2: number...): number`

- Gibt die größte der übergebenen Zahlen zurück.

### `min()`

`min(value1: number, value2: number...): number`

- Gibt die kleinste der übergebenen Zahlen zurück.

### `now()`

`now(): date`

- Gibt das aktuelle Datum als Datums-Objekt zurück.

### `number()`

`number(input: any): number`

- Versucht, den übergebenen Wert als Zahl zurückzugeben.
- Datums-Objekte werden in Millisekunden seit der Unix-Epoche umgewandelt.
- Boolean-Werte werden als 1 oder 0 zurückgegeben.
- Zeichenfolgen werden in eine Zahl umgewandelt. Bei einem ungültigen Ergebnis wird ein Fehler ausgegeben.
- Beispiel: `number("3.4")` gibt `3.4` zurück.

### `today()`

`today(): date`

- Gibt das aktuelle Datum als Datums-Objekt zurück, wobei die Uhrzeit auf Null gesetzt ist.

## Beliebig

Diese Funktionen können mittels Punkt-Notation auf Werte von einem beliebigen Typ angewendet werden (`wert.funktion()`). Dazu gehören Zeichenfolgen (z.B. `"hallo"`), Zahlen (z.B. `42`), Listen (z.B. `[1,2,3]`) und Objekte.

### `isTruthy()`

`beliebig.isTruthy(): boolean`

- Gibt einen Booleschen Wert zurück.
- Beispiel: `1.isTruthy()` gibt `true` zurück.

### `toString()`

`beliebig.toString(): string`

- Gibt den aufrufenden Wert `beliebig` als Zeichenfolge zurück.
- Beispiel: `123.toString()` gibt `"123"` zurück.

## Datum

Diese Funktionen kannst du auf Datumsangaben anwenden, wie bspw. `date("2025-05-27")`. Datumsvergleiche können mithilfe von [[Bases Syntax#Datumsberechnung|Datumsberechnungen]] ausgeführt werden.

### Felder

Folgende Felder sind in Datumsangaben verfügbar:

| Feld                | Typ    | Beschreibung         |
| ------------------- | ------ | -------------------- |
| `datum.year`        | `Zahl` | Jahr                 |
| `datum.month`       | `Zahl` | Monat (1–12)         |
| `datum.day`         | `Zahl` | Tag des Monats       |
| `datum.hour`        | `Zahl` | Stunde (0–23)        |
| `datum.minute`      | `Zahl` | Minute (0–59)        |
| `datum.second`      | `Zahl` | Sekunde (0–59)       |
| `datum.millisecond` | `Zahl` | Millisekunde (0–999) |

### `date()`

`datum.date(): date`

- Gibt ein Datums-Objekt zurück, wobei die Uhrzeit auf Null gesetzt ist.
- Beispiel: `now().date().format("YYYY-MM-DD HH:mm:ss")` erzeugt die Zeichenfolge "2025-12-31 00:00:00".

### `format()`

`datum.format(format: string): string`

- `format` definiert die Formatierungsregel (z.B. `"YYYY-MM-DD"`).
- Formatiert das `datum` gemäß der übergebenen [Moment.js](https://momentjs.com/)-Formatzeichenfolge `format`.
- Beispiel: `now().format("YYYY-MM-DD")` gibt `"2025-05-27"` zurück.

### `isEmpty()`

`datum.isEmpty(): boolean`

- Gibt `false` zurück, falls `datum` einem gültigen Datum entspricht.

### `relative()`

`datum.relative(): string`

- Gibt die Zeitdauer zwischen dem aufrufenden `datum` und dem zur Laufzeit aktuellen Datum in menschenlesbarer Form zurück.
- Beispiel: `file.mtime.relative()` gibt z.B. `vor 3 Tagen` aus.

### `time()`

`datum.time(): string`

- Gibt den Uhrzeit-Anteil von `datum` zurück.
- Beispiel: `now().time()` gibt "10:59:30" zurück.

## Zeichenfolge

Diese Funktionen können auf Zeichenfolgen angewendet werden.

### Felder

| Feld                  | Typ    | Beschreibung                           |
| --------------------- | ------ | -------------------------------------- |
| `zeichenfolge.length` | `Zahl` | Anzahl der Zeichen in der Zeichenfolge |

### `contains()`

`zeichenfolge.contains(value: string): boolean`

- `value` ist die Zeichenfolge, nach der innerhalb der aufrufenden `zeichenfolge` gesucht werden soll.
- Gibt `true` zurück, wenn die Zeichenfolge `value` in `zeichenfolge` enthalten ist.
- Beispiel: `"hallo".contains("all")` gibt `true` zurück.

### `containsAll()`

`zeichenfolge.containsAll(...values: string): boolean`

- `values` ist eine kommaseparierte Liste von Zeichenfolgen, nach denen in der aufrufenden `zeichenfolge` gesucht werden soll.
- Gibt `true` zurück, wenn *alle* übergebenen Zeichenfolgen `values` in der `zeichenfolge` enthalten sind.
- Beispiel: `"hallo".containsAll("h", "a")` gibt `true` zurück.

### `containsAny()`

`zeichenfolge.containsAny(...values: string): boolean`

- `values`  ist eine kommaseparierte Liste von Zeichenfolgen, nach denen in der aufrufenden `zeichenfolge` gesucht werden soll.
- Gibt `true` zurück, wenn mindestens eine der Zeichenfolgen aus `values` in der `zeichenfolge` enthalten ist.
- Beispiel: `"hallo".containsAny("x", "y", "a")` gibt `true` zurück.

### `endsWith()`

`zeichenfolge.endsWith(query: string): boolean`

- Gibt `true` zurück, wenn die `zeichenfolge` mit der übergebenen Zeichenfolge `query` endet.
- Beispiel: `"hallo".endsWith("lo")` gibt `true` zurück.

### `isEmpty()`

`zeichenfolge.isEmpty(): boolean`

- Gibt `true` zurück, wenn die aufrufende `zeichenfolge` leer oder nicht vorhanden ist.
- Beispiel: `"Hallo Welt".isEmpty()` gibt `false` zurück.
- Beispiel: `"".isEmpty()` gibt `true` zurück.

### `lower()`

`zeichenfolge.lower(): string`

- Konvertiert die aufrufende `zeichenfolge` in Kleinbuchstaben und gibt diese zurück.

### `replace()`

`zeichenfolge.replace(pattern: string | regexp, replacement: string): string`

- Ersetzt ein Muster in der aufrufenden `zeichenfolge` durch eine neue Zeichenfolge `replacement` und gibt das Ergebnis zurück.
- `pattern` ist das Muster, nach dem in der aufrufenden `zeichenfolge` gesucht werden soll.
- `replacement` ist der Wert, mit dem das Muster ersetzt werden soll.
- Wenn `pattern` eine Zeichenfolge ist, werden alle Vorkommen des Musters ersetzt.
- Wenn `pattern` ein regulärer Ausdruck ist, bestimmt das Flag `g`, ob alle oder (bei fehlendem Flag) nur das erste Vorkommen des Musters ersetzt werden.
- Beispiel: `"a,b,c,d".replace(/,/, "-")` gibt `"a-b,c,d"` zurück.
- Beispiel: `"a,b,c,d".replace(/,/g, "-")` gibt `"a-b-c-d"` zurück.

### `reverse()`

`zeichenfolge.reverse(): string`

- Kehrt die `zeichenfolge` um und gibt diese zurück.
- Beispiel: `"hallo".reverse()` gibt `"ollah"` zurück.

### `slice()`

`zeichenfolge.slice(start: number, end?: number): string`

- Gibt den Teil der `zeichenfolge` zurück, der von `start` bis `end` ausgewählt wurde, wobei `start` und `end` die Indizes von Zeichen in der `zeichenfolge` sind und `end` nicht inbegriffen ist.
- `start` ist der nullbasierte Index, bei dem die Extraktion beginnt.
- `end` (optional) ist der nullbasierte Index, vor dem die Extraktion endet.
- Wird `end` weggelassen, wird die Zeichenfolge von `start` bis zum Ende extrahiert.
- Beispiel: `"hallo".slice(1, 4)` returns `"all"`.

### `split()`

`zeichenfolge.split(separator: string | regexp, n?: number): list`

- Gibt eine Liste von Teilzeichenfolgen zurück.
- `separator` ist das Trennzeichen zum Aufteilen der `zeichenfolge`.
- `n` (optional) ist eine Zahl, die festlegt, dass nur die ersten `n` Elemente in die Ergebnisliste aufgenommen werden.
- Beispiel: `"a,b,c,d".split(",", 3)` oder `"a,b,c,d".split(/,/, 3)` gibt `["a", "b", "c"]` zurück.

### `startsWith()`

`zeichenfolge.startsWith(query: string): boolean`

- Gibt `true` zurück, wenn die `zeichenfolge` mit der übergebenen Zeichenfolge `query` beginnt.
- Beispiel: `"hallo".startsWith("ha")` gibt `true` zurück.

### `title()`

`zeichenfolge.title(): string`

- Wandelt die `zeichenfolge` in eine Zeichenfolge um, in welcher jeweils der erste Buchstabe eines Wortes groß geschrieben ist.
- Beispiel: `"hallo welt".title()` gibt `"Hallo Welt"` zurück.

### `trim()`

`zeichenfolge.trim(): string`

- Entfernt alle Leerzeichen am Anfang und am Ende der `zeichenfolge`.
- Beispiel: `"  hi  ".trim()` gibt `"hi"` zurück.

## Zahl

Diese Funktionen kannst du auf numerische Werte anwenden.

### `abs()`

`zahl.abs(): number`

- gibt den absoluten Wert der `zahl` zurück.
- Beispiel: `(-5).abs()` gibt `5` zurück.

### `ceil()`

`zahl.ceil(): number`

- Rundet die `zahl` zum nächsten Ganzzahlwert auf.
- Beispiel: `(2.1).ceil()` gibt `3` zurück.

### `floor()`

`zahl.floor(): number`

- Rundet die `zahl` zum nächsten Ganzzahlwert ab.
- Beispiel: `(2.9).floor()` gibt `2` zurück.

### `isEmpty()`

`zahl.isEmpty(): boolean`

- Gibt `true` zurück, wenn die `zahl` nicht vorhanden ist.
- Beispiel: `5.isEmpty()` gibt `false` zurück.

### `round()`

`zahl.round(digits?: number): number`

- Rundet die `zahl` zum nächsten Ganzzahlwert auf oder ab.
- Optional kann im Parameter `digits` die Anzahl der Nachkommastellen angegeben werden, auf die gerundet werden soll.
- Beispiel: `(2.5).round()` gibt `3` zurück.
- Beispiel: `(2.3333).round(2)` gibt `2.33` zurück.

### `toFixed()`

`zahl.toFixed(precision: number): string`

- Gibt die `zahl` in ihrer Festkommadarstellung als Zeichenfolge zurück..
- `precision` ist die Anzahl der Nachkommastellen.
- Beispiel: `(3.14159).toFixed(2)` gibt `"3.14"` zurück.

## Liste

Diese Funktionen kannst du auf geordnete Listen von Elementen anwenden , bspw. `[1, 2, 3]`.

### Felder

| Feld           | Typ      | Beschreibung                     |
| -------------- | -------- | -------------------------------- |
| `liste.length` | `number` | Anzahl der Elemente in der Liste |

### `contains()`

`liste.contains(value: any): boolean`

- Gibt `true` zurück, wenn der Wert `value` in der `liste` enthalten ist.
- Beispiel: `[1,2,3].contains(2)` gibt `true` zurück.

### `containsAll()`

`liste.containsAll(...values: any): boolean`

- Gibt `true` zurück, wenn alle Werte aus `values` in der `liste` enthalten sind.
- Beispiel: `[1,2,3].containsAll(2,3)` gibt `true` zurück.

### `containsAny()`

`liste.containsAny(...values: any): boolean`

- Gibt `true` zurück, wenn mindestens einer der Werte aus `values` in der `liste` enthalten ist.
- Beispiel: `[1,2,3].containsAny(3,4)` gibt `true` zurück.

### `filter()`

`liste.filter(filterfunktion: boolean): list`

- Filtert die Elemente der `liste` anhand der übergebenen `filterfunktion` und gibt die gefilterte Liste zurück.
- Die `filterfunktion` kann die Variablen `value` und `index` verwenden und sollte einen Booleschen Wert zurückgeben, der besagt, ob das Listenelement in die Ergebnisliste aufgenommen werden soll.
- `value` entspricht dem Wert des geprüften Listenelements.
- `index` entspricht dem nullbasierten Index des geprüften Listenelements.
- Beispiel: `[1,2,3,4].filter(value > 2)` gibt `[3,4]` zurück.

### `flat()`

`liste.flat(): list`

- Wandelt eine verschachtelte Liste in eine einzige, flache Liste um.
- Beispiel: `[1,[2,3]].flat()` gibt `[1,2,3]` zurück.

### `isEmpty()`

`liste.isEmpty(): boolean`

- Gibt `true` zurück, wenn die `liste` keine Elemente enthält.
- Beispiel: `[1,2,3].isEmpty()` gibt `false` zurück.

### `join()`

`liste.join(separator: string): string`

- Konvertiert eine `liste` in eine einzige Zeichenfolge, wobei der `separator` als Trennzeichen zwischen den Listenelementen verwendet wird.
- Beispiel: `[1,2,3].join(",")` gibt `"1,2,3"` zurück.

### `map()`

`liste.map(converter: any): list`

- Transformiert jedes Element der `liste`, indem die übergebene Konvertierungsfunktion `converter` darauf angewendet wird.
- Die `converter` Funktion kann die Variablen `value` und `index` verwenden und sollte den transformierten Wert zurückgeben, der an die Ergebnisliste angehängt wird.
- `value` entspricht dem Wert des geprüften Listenelements.
- `index` entspricht dem nullbasierten Index des geprüften Listenelements.
- Beispiel: `[1,2,3,4].map(value + 1)` gibt `[2,3,4,5]` zurück.

### `reverse()`

`liste.reverse(): list`

- Kehrt die Reihenfolge der Listenelemente um.
- Beispiel: `[1,2,3].reverse()` gibt `[3,2,1]` zurück.

### `slice()`

`liste.slice(start: number, end?: number): list`

- Gibt eine flache Kopie eines Teils der `liste` zurück vom Listenelement am Index `start` bis `end`, wobei `end` nicht inbegriffen ist.
- `start` ist der nullbasierte Index, bei dem die Extraktion beginnt.
- `end` (optional) ist der nullbasierte Index, vor dem die Extraktion endet.
- Wird `end` weggelassen, wird die `liste` von `start` bis zum letzten Element extrahiert.
- Beispiel: `[1,2,3,4].slice(1,3)` gibt `[2,3]` zurück.

### `sort()`

`liste.sort(): list`

- Sortiert die Elemente der `liste` vom kleinsten zum größten.
- Beispiel: `[3, 1, 2].sort()` gibt `[1, 2, 3]` zurück.
- Beispiel: `["c", "a", "b"].sort()` gibt `["a", "b", "c"]` zurück.

### `unique()`

`liste.unique(): list`

- Entfernt Duplikate aus der `liste`.
- Beispiel: `[1,2,2,3].unique()` gibt `[1,2,3]` zurück.

## Link

Diese Funktionen kannst du auf Link-Objekte anwenden. Ein Link-Objekt erstellst du aus einer [[#`asLink()`|Datei]] oder einem [[#`link()`|Dateipfad]].

### `asFile()`

`link.asFile(): file`

- Gibt ein Datei-Objekt zurück, wenn der `link` sich auf eine gültige, lokale Datei bezieht.
- Beispiel: `link("[[dateiname]]").asFile()`

### `linksTo()`

`link.linksTo(file): boolean`

- Gibt `true` zurück, wenn die durch den `link` repräsentierte Datei einen Link zur Datei `file` enthält, ansonsten `false`.

## Datei

Diese Funktionen kannst du auf Dateien in deinem Vault anwenden.

### `asLink()`

`datei.asLink(display?: string): link`

- Gibt ein Link-Objekt zurück, das in einer Sicht als anklickbarer Link zur `datei` gerendert wird.
- `display` (optional) ist der Anzeigetext für den Link.
- Beispiel: `file.asLink()`

### `hasLink()`

`datei.hasLink(otherFile: file | string): boolean`

- Gibt `true` zurück, wenn die `datei` einen Link zur Datei `otherFile` enthält.
- `otherFile` ist ein Datei-Objekt oder Dateipfad zu einer weiteren Datei.

### `hasProperty()`

`datei.hasProperty(name: string): boolean`

- Gibt `true` zurück, wenn die Notiz `datei` die übergebene [[Eigenschaften|Eigenschaft]] `name` enthält.

### `hasTag()`

`datei.hasTag(...values: string): boolean`

- Gibt `true` zurück, wenn die `datei` mindestens einen der in `values` übergebenen Tags enthält.
- `values` ist eine kommaseparierte Aufzählung von Tag-Namen.
- Beispiel: `file.hasTag("tag1", "tag2")` gibt `true` zurück, wenn die Datei den Tag `#tag1` oder `#tag2` enthält. [[Tags#Verschachtelte Tags|Verschachtelte Tags]], wie `#tag1/a` oder `#tag2/b`, sind dabei eingeschlossen.

### `inFolder()`

`datei.inFolder(folder: string): boolean`

- Gibt `true` zurück, wenn die `datei` sich im spezifizierten Ordner `folder` befindet.
- Beispiel: `file.inFolder("Notizen")` gibt `true` zurück.

## Objekt

Diese Funktionen kannst du auf Sammlungen von Schlüssel-Wert-Paaren anwenden, bspw. `{"a": 1, "b": 2}`.

### `isEmpty()`

`objekt.isEmpty(): boolean`

- Gibt `true` zurück, wenn das `objekt` kein Schlüssel-Wert-Paar enthält.
- Beispiel: `{}.isEmpty()` gibt `true` zurück.

### `keys()`

`objekt.keys(): list`

- Gibt eine Liste der im `objekt` enthaltenen *Schlüssel* zurück.

### `values()`

`objekt.values(): list`

- Gibt eine Liste der im `objekt` enthaltenen *Werte* zurück.

## Regulärer Ausdruck

Diese Funktionen kannst du auf reguläre Ausdrücke anwenden, bspw. `/abc/`.

### `matches()`

`regexp.matches(value: string): boolean`

- `value` is the string to test.
- Gibt `true` zurück, wenn der Wert `value` mit dem regulären Ausdruck `regexp` übereinstimmt, ansonsten `false`.
- Beispiel: `/abc/.matches("abcde")` gibt `true` zurück.
