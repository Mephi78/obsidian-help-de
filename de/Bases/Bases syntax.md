---
permalink: bases/syntax
aliases:
  - Bases Dateiformat
description: Einführung in Obsidian's Bases Syntax.
mobile: true
publish: true
---

Wenn du in Obsidian eine [[Erstelle eine Base|Base erstellst]], wird diese als `.base`-Datei gespeichert. Bases werden in der Regel interaktiv über die Bedienoberfläche bearbeitet, aber du kannst den Quellcode auch manuell editieren und in einen Quelltext-Block einbetten.

Mit der [[Einführung in Bases|Bases]] Syntax kannst du [[Sichten]], Filter und Formeln definieren. Bases müssen aus validem YAML bestehen und dem nachfolgend definierten Schema entsprechen.

## Anwendungsfall

Das folgende Beispiel einer Base-Datei werden wir Schritt für Schritt im Detail durchgehen.

```yaml
filters:
  or:
    - file.hasTag("tag")
    - and:
        - file.hasTag("buch")
        - file.hasLink("Lehrbuch")
    - not:
        - file.hasTag("buch")
        - file.inFolder("Pflichtlektüre")
formulas:
  formatierter_preis: 'if(preis, preis.toFixed(2) + " Euro")'
  stp: "(preis / alter).toFixed(2)"
properties:
  note.status:
    displayName: Status
  formula.formatierter_preis:
    displayName: "Preis"
  file.ext:
    displayName: Dateieindung
summaries:
  customAverage: 'values.mean().round(3)'
views:
  - type: table
    name: "Meine Tabelle"
    limit: 10
    groupBy:
      property: note.age
      direction: DESC
    filters:
      and:
        - 'status != "erledigt"'
        - or:
            - "formula.stp > 5"
            - "preis > 2.1"
    order:
      - file.name
      - file.ext
      - note.alter
      - formula.stp
      - formula.formatierter_preis
    summaries:
      formula.stp: Average
```

### Filter

Standardmäßig umfasst eine Base alle Dateien im Vault. Es gibt kein `from` oder `source`, wie in SQL oder Dataview. Im Abschnitt `filters` kannst du Bedingungen definieren, um den Datensatz einzugrenzen.

```yaml
filters:
  or:
    - file.hasTag("tag")
    - and:
        - file.hasTag("buch")
        - file.hasLink("Lehrbuch")
    - not:
        - file.hasTag("buch")
        - file.inFolder("Pflichtlektüre")
```

Es gibt zwei Möglichkeiten, Filter anzuwenden:

1. Auf globaler Ebene im Abschnitt `filters` (siehe oben) definierte Filter werden auf alle Sichten in der Base angewendet.
2. Auf Sicht-Ebene im Abschnitt `view` definierte Filter gelten nur für eine bestimmte Sicht.

Die beiden Abschnitte sind funktional gleichwertig und die Filterdefinitionen werden bei der Auswertung für eine Sicht mit `UND` verkettet.

Der Abschnitt `filters` enthält entweder eine einzelne Filteranweisung als Zeichenfolge oder ein rekursiv definiertes Filterobjekt. Filterobjekte können einen oder mehrere `and`, `or` oder `not` Operatoren enthalten. Eine Filteranweisung ist eine Code-Zeile, die bei Anwendung auf eine Notiz wahr oder falsch ergibt. Folgende Varianten sind möglich:

- Ein einfacher Vergleich mittels arithmetischen Operatoren.
- Eine Funktion.

Obsidian bietet eine Vielzahl von integrierten [[Funktionen]], die durch externe Plugins noch erweitert werden können.

Syntax und verfügbare Funktionen sind identisch für globale und Sicht-Filter.

### Formeln

Der Abschnitt `formulas` definiert Formel-Eigenschaften, die in allen Sichten einer Base angezeigt werden können.

```yaml
formulas:
  formatierter_preis: 'if(preis, preis.toFixed(2) + " Euro")'
  stp: "(preis / alter).toFixed(2)"
```

Formel-Eigenschaften unterstützen arithmetische Grundoperatoren und eine Reihe von integrierten [[Funktionen]]. Zukünftig können externe Erweiterungen weitere Funktionen für die Verwendung in Formeln hinzufügen.

Du kannst Eigenschaften je nach Typ auf unterschiedliche Weise referenzieren:

- **Notiz-Eigenschaften** sind Eigenschaften, die im Frontmatter einer Notiz definiert sind, z.B. `note.preis` oder `note["preis"]`.  
  Wenn kein Präfix definiert ist, wird eine Eigenschaft als `note`-Eigenschaft interpretiert.
- **Datei-Eigenschaften** beschreiben die Datei selbst.  
  Z.B. `file.size` (Dateigröße) oder `file.ext` (Dateiendung). Du kannst das Datei-Objekt auch direkt referenzieren, bspw. `file.hasLink()`.
- **Formel-Eigenschaften** sind in der Base definierte Formeln.  
  Z.B. `formula.formatierter_preis`.

Eine Formel kann wiederum andere Formel-Eigenschaften enthalten, solange kein Zirkelbezug vorliegt.

Formel-Eigenschaften werden in YAML immer als Zeichenketten gespeichert, aber ihr eigentlicher **Ausgabedatentyp** wird durch den Typ der zugrundeliegenden Daten und den Rückgabewert der Funktion bestimmt.

Beachte, dass die Anwendung von verschachtelten Anführungszeichen erforderlich ist, um String-Literale in YAML-Feldern zu verwenden. Literale müssen in einfache oder doppelte Anführungszeichen gesetzt werden.

### Eigenschaften

Im Abschnitt `properties` kannst du Einstellungen zu jeder Eigenschaft definieren. Es hängt von der jeweiligen Sicht ab, wie die Einstellungswerte interpretiert werden. In Tabellen wird der `displayName` bspw. als Spaltenüberschrift verwendet.

```yaml
properties:
  note.status:
    displayName: Status
  formula.formatierter_preis:
    displayName: "Preis"
  file.ext:
    displayName: Dateiendung
```

In Filtern oder Formeln werden Anzeigenamen nicht verwendet.

> [!note] Hinweis
> Achte darauf, im Abschnitt `properties` auch Notiz-Eigenschaften in der vollständigen Punkt-Notation zu verwenden. Die [[#Notiz-Eigenschaften|Kurzschreibweise]] funktioniert hier nicht.

### Zusammenfassungen

Der Abschnitt `summaries` kann verwendet werden, um benutzerdefinierte Zusammenfassungsformeln zu definieren. Zusätzlich zur Definition eigener Formeln stehen hier einige Standard-Zusammenfassungsformeln zur Verfügung.

```yaml
summaries:
  customAverage: 'values.mean().round(3)'
```

Die benutzerdefinierte Formel `customAverage` im Beispiel entspricht der Standard-Formel `Average`, bis auf dass der Wert auf eine andere Anzahl von Stellen gerundet wird. In Zusammenfassungsformeln steht das Schlüsselwort `values` für eine Liste aller Werte für diese Eigenschaft über alle Notizen des Ergebnissatzes hinweg. Eine Zusammenfassungsformel sollte einen einzigen Wert (`Value`) zurückgeben.

Beachte, dass dieser `summaries`-Abschnitt sich vom gleichnamigen Abschnitt `summaries` in der [[#Sichten|Sichten-Konfiguration]] unterscheidet, in welchem Zusammenfassungsformeln bestimmten Eigenschaften zugewiesen werden.

#### Standard-Zusammenfassungsformeln

| Name      | Typ     | Beschreibung                                                     |
| --------- | ------- | ---------------------------------------------------------------- |
| Average   | Zahl    | Der mathematische Mittelwert aller Zahlen aus den Eingabewerten. |
| Min       | Zahl    | Die kleinste Zahl aus den Eingabewerten.                         |
| Max       | Zahl    | Die größte Zahl aus den Eingabewerten.                           |
| Sum       | Zahl    | Die Summe aller Zahlen aus den Eingabewerten.                    |
| Range     | Zahl    | Die Differenz zwischen `Max` und `Min`.                          |
| Median    | Zahl    | Der mathematische Median aller Zahlen aus den Eingabewerten.     |
| Stddev    | Zahl    | Die Standardabweichung aller Zahlen aus den Eingabewerten.       |
| Earliest  | Datum   | Das früheste Datum aus den Eingabewerten.                        |
| Latest    | Datum   | Das späteste Datum aus den Eingabewerten.                        |
| Range     | Datum   | Die Differenz zwischen `Latest` und `Earliest`.                  |
| Checked   | Boolean | Die Anzahl aller `true`-Werte.                                   |
| Unchecked | Boolean | Die Anzahl aller `false`-Werte.                                  |
| Empty     | Jeder   | Die Anzahl aller Werte, die leer sind.                           |
| Filled    | Jeder   | Die Anzahl aller Werte, die nicht leer sind.                     |
| Unique    | Jeder   | Die Anzahl der eindeutigen Werte aus der Eingabe.                |

### Sichten

Der Abschnitt `views` bestimmt, wie die anzuzeigenden Daten gerendert werden. Jeder Eintrag in der `views`-Liste definiert eine separate Sicht auf dieselben Daten. Du kannst so viele Sichten definieren, wie du benötigst.

Hier im Beispiel enthält die Liste nur einen Eintrag, also eine Sicht.

```yaml
views:
  - type: table
    name: "Meine Tabelle"
    limit: 10
    groupBy:
      property: note.age
      direction: DESC
    filters:
      and:
        - 'status != "erledigt"'
        - or:
            - "formula.stp > 5"
            - "preis > 2.1"
    order:
      - file.name
      - file.ext
      - note.alter
      - formula.stp
      - formula.formatierter_preis
    summaries:
      formula.stp: Average
```

- `type` kann eines der integrierten oder durch Plugins hinzugefügten [[Sichten#Layout|Layouts]] enthalten.
- `name` ist der Anzeigename, der verwendet werden kann, um das Standard-Layout festzulegen (mittels [[Erstelle eine Base#Base-Datei einbetten|Anchor Tag]]).
- `filters` definiert die auf eine bestimmte Sicht anzuwendenden Filter, wie oben beschrieben.
- `order` bestimmt, welche Elemente in welcher Reihenfolge angezeigt werden sollen. Im Beispiel ist eine Tabellen-Sicht definiert, wobei die in `order` gelisteten Elemente als anzuzeigende Spalten interpretiert werden.
- `groupBy` bestimmt eine Eigenschaft und Sortierreihenfolge. Der Wert der angegebenen Eigenschaft für jede Zeile wird verwendet, um die Zeile in Gruppen einzuordnen.
- `summaries` ordnet Eigenschaftsnamen einer benannten Zusammenfassung zu. Zusammenfassungen führen eine Aggregation der Eigenschaft über alle Zeilen hinweg durch.

[[Sichten]] können *zusätzliche Daten* hinzugefügt werden, die für die Funktionsweise oder Darstellung eines spezifischen Layouts notwendig sind. Plugin-Entwickler sollten jedoch darauf achten, keine Schlüssel zu verwenden, die bereits durch die Standarderweiterung *Bases* verwendet werden.

Ein Tabellen-Layout könnte diese Zusatzinformationen bspw. verwenden, um die Anzahl der angezeigten Zeilen zu limitieren oder zu definieren, welche Spalten in welcher Richtung für die Sortierung verwendet werden. Ein anderes Layout, wie z.B. eine Landkarte, könnte dies verwenden, um zu definieren, welche Notiz-Eigenschaften den Breiten- und Längengrad enthalten und welche der Eigenschaften als Titel für eine Stecknadel-Markierung verwendet werden soll.

Es ist angedacht, dass die API künftig das Lesen und Schreiben dieser Zusatzinformationen erlaubt, so dass für ein Layout eine eigene Konfigurationsschnittstelle erstellt werden kann.

## Eigenschaften

Bases kennt drei Arten von Eigenschaften:

1. **Notiz-Eigenschaften** sind im Frontmatter von Markdown-Dateien gespeichert.
2. **Datei-Eigenschaften** sind für jeden Dateityp zugänglich.
3. **Formel-Eigenschaften** sind in der `.base`-Datei selbst definiert (siehe [[#Formeln|oben]]).

### Notiz-Eigenschaften

[[Eigenschaften|Notiz-Eigenschaften]] sind nur für Markdown-Dateien verfügbar und werden im YAML-Frontmatter einer Notiz definiert. Auf diese Eigenschaften kannst du entweder mit `note.eigenschaftsname` oder einfach verkürzt mit `eigenschaftsname` zugreifen.

### Datei-Eigenschaften

Datei-Eigenschaften beziehen sich auf die jeweils verarbeitete Datei. Diese Eigenschaften sind für alle [[Dateitypen]] verfügbar, auch für Anhänge.

Ein Filter `file.ext == "md"` würde bspw. die Dateiendungen der Dateien in deinem Vault untersuchen und alle Markdown-Dateien zurückgeben.

| Eigenschaft       | Typ    | Beschreibung                                                                                                                                                                                                                                            |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `file.backlinks`  | Liste  | Liste der [[Rückverweise]] einer Datei. **Hinweis**: Diese Eigenschaft ist sehr leistungsintensiv. Kehre nach Möglichkeit die Suche um und verwende stattdessen `file.links`. Ergebnisse werden nicht automatisch aktualisiert bei Änderungen im Vault. |
| `file.ctime`      | Datum  | Erstellungszeitpunkt                                                                                                                                                                                                                                    |
| `file.embeds`     | Liste  | Liste aller in die Notiz eingebetteten Elemente                                                                                                                                                                                                         |
| `file.ext`        | Text   | Dateiendung                                                                                                                                                                                                                                             |
| `file.file`       | Datei  | Dateiobjekt, nur in bestimmten Funktionen verwendbar                                                                                                                                                                                                    |
| `file.folder`     | Text   | Pfad zum Ordner, in dem die Datei gespeichert ist                                                                                                                                                                                                       |
| `file.links`      | Liste  | Liste aller interner Links in einer Notiz, einschließlich Frontmatter                                                                                                                                                                                   |
| `file.mtime`      | Datum  | Zeitpunkt der letzten Bearbeitung                                                                                                                                                                                                                       |
| `file.name`       | Text   | Dateiname                                                                                                                                                                                                                                               |
| `file.path`       | Text   | Speicherpfad der Datei                                                                                                                                                                                                                                  |
| `file.properties` | Objekt | Alle Eigenschaften der Datei. **Hinweis**: Ergebnisse werden bei Änderungen im Vault nicht automatisch aktualisiert.                                                                                                                                    |
| `file.size`       | Zahl   | Dateigröße                                                                                                                                                                                                                                              |
| `file.tags`       | Liste  | Liste aller Tags in einer Notiz, einschließlich Frontmatter                                                                                                                                                                                             |

### Zugriff auf Eigenschaften mit `this`

Verwende das Objekt `this`, um gezielt auf Dateieigenschaften zuzugreifen. Worauf `this` verweist, hängt davon ab, wo die Base angezeigt wird.

Wird die Base im Hauptfenster geöffnet, verweist `this` auf die Eigenschaften der Base-Datei selbst. `this.file.folder` enthält dann bspw. den Speicherpfad zur Base-Datei.

Bei eingebetteten Bases verweist `this` auf die Eigenschaften der Datei (Notiz oder Canvas), in die die Base eingebettet wurde. `this.file.name` gibt dann bspw. den Namen der einbettenden Datei zurück.

Aus einer Seitenleiste heraus bezieht sich `this` auf die derzeit aktive Datei. Auf diese Weise kannst du kontextbezogene Abfragen basierend auf der im Hauptfensterbereich aktiven Datei erstellen und diese in einer der Seitenleisten anzeigen. Du könntest damit bspw. die [[Rückverweise]]-Ansicht nachempfinden, indem du dem Filter `file.hasLink(this.file)` anwendest.

## Operatoren

### Arithmetische Operatoren

Arithmetische Operatoren führen arithmetische Berechnungen mit Zahlen aus, bspw. `radius * (2 * 3.14)`.

| Operator | Beschreibung   |
| -------- | -------------- |
| `+`      | Addition       |
| `-`      | Subtraktion    |
| `*`      | Multiplikation |
| `/`      | Division       |
| `%`      | Modulo         |
| `( )`    | Klammern       |

### Datumsberechnung

Datumsangaben können geändert werden, indem eine Zeitdauer addiert oder subtrahiert wird. Die Dauer kann im folgenden Format angegeben werden:

| Format                   | Dauer   |
| ------------------------ | ------- |
| `y`, `year`, `years`     | Jahr    |
| `M`, `month`, `months`   | Monat   |
| `d`, `day`, `days`       | Tag     |
| `w`, `week`, `weeks`     | Woche   |
| `h`, `hour`, `hours`     | Stunde  |
| `m`, `minute`, `minutes` | Minute  |
| `s`, `second`, `seconds` | Sekunde |

Verwende für Berechnungen mit Datumsobjekten den `+` oder `-` Operator mit einer Dauer im Textformat, z.B. addiert `date + "1M"` einen Monat zu einem Datum, während `date - "2h"` zwei Stunden abzieht.

Die globale [[Funktionen|Funktion]] `today()` kann verwendet werden, um das aktuelle Datum zu ermitteln und `now()` ruft das aktuelle Datum mit Uhrzeit ab.

- `now() + "1 day"` gibt das Datum mit Uhrzeit zurück, das genau 24 Stunden nach der Ausführung liegt.
- `file.mtime > now() - "1 week"` gibt `true` zurück, wenn die Datei innerhalb der letzten Woche geändert wurde.
- `date("2024-12-01") + "1M" + "4h" + "3m"` gibt ein Datumsobjekt zurück, das `2025-01-01 04:03:00` darstellt.
- Subtrahiere zwei Datumsangaben, um die Differenz dazwischen in Millisekunden zu erhalten, z.B. `now() - file.ctime`.
- Um das Datum aus einer Datumsangabe mit Uhrzeit zu extrahieren, kannst du `datetime.date()` verwenden.
- Verwende die Funktion `format()`, um ein Datum zu formatieren, bspw. `datetime.format("YYYY-MM-DD")`.

### Vergleichsoperatoren

Mit Vergleichsoperatoren kannst du Zahlen oder Datumsobjekte vergleichen. Der Gleichheits- und Ungleichheits-Operator kann verwendet werden, um jegliche Werte zu vergleichen, nicht nur Zahlen und Datumsangaben.

| Operator | Beschreibung        |
| -------- | ------------------- |
| `==`     | ist gleich          |
| `!=`     | ungleich            |
| `>`      | größer als          |
| `<`      | kleiner als         |
| `>=`     | größer oder gleich  |
| `<=`     | kleiner oder gleich |

### Logische Operatoren

Boolesche Operatoren können verwendet werden, um Werte logisch zu verknüpfen oder zu negieren, was in der Aussage *wahr* oder *falsch* resultiert.

| Operator | Beschreibung    |
| -------- | --------------- |
| `!`      | logisches NICHT |
| `&&`     | logisches UND   |
| \|\|     | logisches ODER  |

## Funktionen

Für die Verwendung in [[#Formeln|Formeln]] und [[Sichten#Filter|Filtern]] gibt es eine [[Funktionen|Reihe von Funktionen]].

## Typen

Bases verfügt über ein Typsystem, das von Formeln und Filtern verwendet wird, um Funktionen auf Eigenschaften anzuwenden.

### Zeichenfolgen, Zahlen und Boolean

Zeichenfolgen, Zahlen und boolsche Werte sind sogenannte primitive Typen, für deren Erstellung keine Funktion erforderlich ist.

- Zeichenfolgen werden in einfache oder doppelte Anführungszeichen gesetzt, bspw. `"Text"`.
- Zahlen werden mit Ziffern geschrieben und können optional zur Verdeutlichung in Klammern gesetzt werden, z.B. `1` oder `(2.5)`.
- Boolsche Werte werden ohne Anführungszeichen als `true` oder `false` geschrieben.

### Datum und Zeitdauer

Datumsangaben repräsentieren ein bestimmtes Datum oder ein Datum mit Uhrzeit, je nachdem, welche Funktion zur Erstellung verwendet oder welcher Datentyp der [[Eigenschaften|Eigenschaft]] zugewiesen wurde.

- Verwende die Funktion `date`, um ein Datum zu erzeugen, z.B. `date("2025-01-01 12:00:00")`.
- Um ein Datum zu ändern, addiere oder subtrahiere eine Dauer, z.B. `now() + "1 hour"` oder `today() - "7d"`.
- Vergleiche Datumsangaben mit Vergleichsoperatoren (z.B. `>`, `<`) oder arithmetischen Operatoren (z.B. `(now() + "1d") - now()` ergibt `86400000` Millisekunden).
- Um Teile eines Datums zu extrahieren, verwende die verfügbaren Felder (bspw. `now().hour`) oder eine entsprechende Funktion (z.B. `now.time()`).
- Für Datumsobjekte sind noch eine Reihe weitere [[Funktionen|Felder und Funktionen]] verfügbar.

### Objekte und Listen

- Wandle ein einzelnes Element mit der Funktion `list()` in eine Liste um. Diese Funktion ist hilfreich für Eigenschaften, die sowohl Listen, als auch Einzelwerte enthalten können.
- Verwende eckige Klammern (`[]`) in Verbindung mit einem nullbasierten Index, um auf Listenelemente zuzugreifen. `eigenschaft[0]` gibt bspw. das erste Element einer Liste zurück.
- Verwende eckige Klammern (`[]`) in Verbindung mit dem Elementnamen oder die Punkt-Notation, um auf Objekte zuzugreifen, z.B. `adresse["straße"]` oder `adresse.straße`.

### Dateien und Links

[[Verlinke Notizen|Wikilinks]] in [[Eigenschaften|Frontmatter-Eigenschaften]] werden automatisch als Link-Objekte erkannt. Link-Objekte werden in [[Sichten]] als klickbare Links gerendert.

- Erstelle einen Link mit der globalen [[Funktionen|Funktion]] `link`, z.B. `link("dateiname")` oder `link("https://obsidian.md")`.
- Du kannst Links aus einer beliebigen Zeichenfolge erstellen, z.B. `link(file.ctime.date().toString())`.
- Um den Anzeigetext festzulegen, übergib der Funktion optional eine Zeichenfolge oder ein Icon als zweiten Parameter, z.B. `link("dateiname", "Anzeige")` oder `link("dateiname", icon("plus"))`.

Ein Dateiobjekt kann mittels `file.asLink()` und einem optionalen Anzeigetext in einen Link umgewandelt werden.

Du kannst Links mit `==` und `!=` vergleichen. Solange zwei Links auf dieselbe Datei verweisen, werden sie als gleich betrachtet. Ist die referenzierte Datei nicht vorhanden, wird stattdessen der Anzeigetext verglichen.

Links können mit Dateien verglichen werden, wie z.B. `file` oder `this`. Verweist der Link auf die verglichene Datei, werden beide als gleich betrachtet, z.B. `autor == this`.

Du kannst auch prüfen, ob Links in Listen enthalten sind, z.B. `autoren.contains(this)`.
