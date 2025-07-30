---
aliases:
  - front matter
  - Fortgeschrittene Themen/YAML front matter
  - metadata
  - property
  - frontmatter
cssclasses:
  - soft-embed
description: Mit Eigenschaften kannst du Informationen über eine Notiz organisieren. Eigenschaften enthalten strukturierte Daten, wie Text, Links, Datumsangaben, Checkboxen oder Zahlenwerte.
mobile: false
permalink: properties
publish: true
---

Mit Eigenschaften kannst du Informationen über eine Notiz organisieren. Sie enthalten strukturierte Daten, wie Text, Links, Datumsangaben, Kontrollkästchen oder Zahlenwerte. Du magst Eigenschaften vielleicht in Verbindung mit [[Externe Erweiterungen|externen Erweiterungen]] verwenden, die nützliche Dinge mit diesen strukturierten Daten anstellen können.

## Eigenschaften zu einer Notiz hinzufügen

Es gibt verschiedene Wege, einer Notiz eine Eigenschaft hinzuzufügen:

- Verwende den [[Command palette|Befehl]] **Dateieigenschaften hinzufügen**.
- Verwende das [[Hotkeys|Tastenkürzel]] **`Strg/Cmd + ;`** (oder auf der deutschen Tastatur **`Strg + ü`**).
- Wähle **Dateieigenschaften hinzufügen** über das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) **Weitere Optionen** rechts oben in deiner Notiz.
- Tippe `---` am Anfang deiner Notiz.

Sobald du eine Eigenschaft hinzufügst, erscheint am Anfang der Notiz eine Zeile mit dem *Eigenschaftsnamen* und dem *Eigenschaftswert*.

Du kannst jeden beliebigen Namen wählen. Obsidian stellt einige Standardeigenschaften zur Verfügung: `tags`, `cssclasses` und `aliases`.

Sobald du einen Eigenschaftsnamen vergeben hast, kannst du diesem einen Wert zuweisen.

### Eigenschaftstypen

Zusätzlich zum Namen und Wert haben Eigenschaften auch einen *Typ*. Der Eigenschaftstyp bestimmt, welche Art von Werten darin gespeichert werden können und wie Obsidian diese verarbeitet. Um den Typ einer Eigenschaft zu ändern, klicke das Typ-Symbol neben dem Eigenschaftsnamen und wähle eine andere Option. Du kannst Eigenschaftstypen auch verwalten über die Standarderweiterung [[Properties view|Eigenschaften-Ansicht]].

Obsidian unterstützt die folgenden Eigenschaftstypen:

- **[[#^text-list|Text]]**
- **[[#^text-list|Liste]]**
- **[[#^numbers|Zahl]]**
- **[[#^checkbox|Checkbox]]**
- **[[#^date-time|Datum]]**
- **[[#^date-time|Datum & Uhrzeit]]**

Sobald einem Eigenschaftsnamen ein Eigenschaftstyp zugewiesen wurde, verwenden alle Eigenschaften im Vault mit demselben Namen auch denselben Typ.

## Erweiterte Einsatzmöglichkeiten

### Links

Eigenschaften vom Typ **Text** und **Liste** kannst du als Werte URLs und [[Internal links|interne Links]] zuweisen mittels `[[Link]]` Syntax.

### Nach Eigenschaften suchen

Eigenschaften haben ihre eigene [[Search|Syntax für die Suche]], die du neben anderen Suchbegriffen und Operatoren verwenden kannst, siehe [[Search#Search properties|Nach Eigenschaften suchen]].

### Vorlagen

Du kannst Eigenschaften auch in [[Integrierte Erweiterungen/Templates|Vorlagen]] verwenden.

Wenn du in die aktive Notiz eine Vorlage einfügst, werden alle Eigenschaften aus der Vorlage zur Notiz hinzugefügt. Obsidian führt auch alle Eigenschaften, die bereits in der Notiz vorhanden sind, mit den Eigenschaften der Vorlage zusammen. ^templates-properties

### Eigenschaften umbenennen

Du kannst eine Eigenschaft umbenennen mit Rechtsklick auf die Eigenschaft in der [[Properties view|Ansicht "Alle Eigenschaften"]].

### Anzeige-Modi

Du kannst wählen, wie Dateieigenschaften in deiner Notiz angezeigt werden sollen. Öffne dazu die **Einstellungen** ( ![[lucide-settings.svg#icon]] ) und wähle unter **Editor → Eigenschaften im Dokument** eine der folgenden Optionen:

- **sichtbar** (Standard) — zeigt Eigenschaften am Anfang der Notiz, sofern welche vorhanden sind.
- **nicht sichtbar** — blendet die Eigenschaften in der Notiz aus, in der [[Properties view|Eigenschaften-Ansicht]] bleiben sie dennoch sichtbar.
- **Quelle** — zeigt Eigenschaften in der Live-Vorschau im YAML-Format an.

### CSS-Bausteine

Du kannst mit der Eigenschaft `cssclasses` [[CSS-Bausteine]] verwenden, um die Darstellung einzelner Notizen anzupassen.

### Nicht unterstützt

Einige Funktionen werden derzeit von Obsidian nicht unterstützt:

- **Verschachtelung**: Um verschachtelte Eigenschaften anzuzeigen, empfehlen wir die Verwendung der [[Views and editing mode#Source mode|Quellcode-Ansicht]].
- **Stapelverarbeitung**: Zur Massenbearbeitung von Eigenschaften außerhalb der [[Properties view|Eigenschaften-Ansicht]] empfehlen wir die Verwendung von Werkzeugen wie VSCode, Batch-Scripten oder externen Erweiterungen.
- **Markdown in Eigenschaften**: Dies ist eine absichtliche Einschränkung, da Eigenschaften für kleine, atomare Informationen gedacht sind, die sowohl für den Menschen als auch maschinenlesbar sind.
## Tastenkürzel

### Eigenschaft hinzufügen

| Aktion                           | Tastenkürzel   |
| -------------------------------- | -------------- |
| Neue Dateieigenschaft hinzufügen | `Strg/Cmd + ;` |

> [!TIP] Auf der deutschen Tastatur kannst du `Strg + ü` verwenden oder dem Befehl einfach ein neues [[Hotkeys#Setting hotkeys|Tastenkürzel zuweisen]].

### Zwischen Eigenschaften wechseln

Wenn eine Eigenschaft den Fokus hat:

| Aktion                            | Tastenkürzel                            |
| --------------------------------- | --------------------------------------- |
| Nächste Eigenschaft fokussieren   | `Pfeil nach unten` oder `Tab`           |
| Vorherige Eigenschaft fokussieren | `Pfeil nach oben` oder `Umschalt + Tab` |
| Zum Editor springen               | `Alt + Pfeil nach unten`                |

### Eigenschaften auswählen

| Aktion                       | Tastenkürzel                  |
| ---------------------------- | ----------------------------- |
| Auswahl nach oben erweitern  | `Umschalt + Pfeil nach oben`  |
| Auswahl nach unten erweitern | `Umschalt + Pfeil nach unten` |
| Alles auswählen              | `Strg/Cmd + A`                |

### Eigenschaften bearbeiten

| Aktion                      | Tastenkürzel                                                                                  |
| --------------------------- | --------------------------------------------------------------------------------------------- |
| Eigenschaftsname bearbeiten | `PFeil nach links`                                                                            |
| Eigenschaftswert bearbeiten | `Pfeil nach rechts`                                                                           |
| Eigenschaft fokussieren     | `Escape`                                                                                      |
| Eigenschaft löschen         | `Strg/Cmd + Rücktaste`<br><br>Falls Eigenschaften ausgewählt sind, wird die Auswahl gelöscht. |
| Rückgängig                  | `Strg/Cmd + Z`                                                                                |
| Wiederholen                 | `Strg/Cmd + Umschalt + Z`                                                                     |

### Vim (für Fortgeschrittene)

| Aktion                              | Tastenkürzel |
| ----------------------------------- | ------------ |
| Nach unten                          | `j`          |
| Nach oben                           | `k`          |
| Eigenschaftsname fokussieren        | `h`          |
| Eigenschaftswert fokussieren        | `l`          |
| Wert fokussieren (Cursor am Ende)   | `A`          |
| Wert fokussieren (Cursor am Anfang) | `i`          |
| Neue Eigenschaft hinzufügen         | `o`          |

## Eigenschaftsformat

Eigenschaften werden im [YAML](https://yaml.org/)-Format am Anfang der Datei gespeichert. YAML ist ein beliebtes Format, das leicht zu verstehen, menschen- und maschinenlesbar ist.

Eigenschaftsnamen werden vom dazugehörigen Wert getrennt durch einen Doppelpunkt gefolgt von einem Leerzeichen:

```yaml
---
name: wert
---
```

Die Reihenfolge der Schlüssel-Wert-Paare spielt keine Rolle, jedoch muss jeder Schlüssel innerhalb einer Notiz eindeutig sein. Du kannst bspw. nicht mehr als eine `tags`-Eigenschaft definieren.

Werte können Text, Zahlen, `true` oder `false` und sogar Wertesammlungen (Listen) beinhalten.
^text-list

```yaml
---
titel: Krieg der Sterne # eine Text-Eigenschaft
jahr: 1977
favorit: true
schauspieler: # eine Listen-Eigenschaft
  - Mark Hamill
  - Harrison Ford
  - Carrie Fisher
---
```

In **Text**- und **Listen**-Eigenschaften müssen interne Links in Anführungszeichen eingeschlossen werden. Obsidian fügt diese automatisch hinzu, wenn du Links manuell zu einer Notiz hinzufügst. Aber denke daran, die Anführungsstriche in Vorlagen eigenständig hinzuzufügen.

```yaml
---
link: "[[Link]]" 
linkliste: 
  - "[[Link]]" 
  - "[[Link2]]"
---
```

Eigenschaften vom Typ **Zahl** müssen immer Zahlenwerte enthalten, keine Ausdrücke mit Operatoren. Es werden Ganzzahl- und Dezimalzahlwerte unterstützt.
^numbers

```yaml
---
jahr: 1977
menge: 3.14
---
```

Eigenschaften vom Typ **Checkbox** enthalten den Wert `true` oder `false`. Ein leerer Wert wird als `false` interpretiert. In der Live-Vorschau wird die Eigenschaft als Kontrollkästchen repräsentiert.
^checkbox

```yaml
---
favorit: true
gelesen: false
besitz: # wird als false interpretiert
```

Eigenschaften vom Typ **Datum** oder **Datum & Uhrzeit** werden im folgenden Format gespeichert: 
^date-time

```yaml
---
datum: 2020-08-21
uhrzeit: 2020-08-21T10:30:00
---
```

Die Datumsauswahl verwendet das Standard-Datumsformat deines Betriebssystems. Du kannst es in den Systemeinstellungen ändern:

> [!info]- Windows
> **Systemeinstellungen → Zeit & Sprache → Sprache & Region → Regionales Format → Formate ändern**
> 
> ![[Windows-OS-DateTime-DE.png#interface]] 

> [!info]- Mac OS
> **Systemeinstellungen → Sprache & Region → Datumsformat**
> 
> ![[Mac-OS-DateTime.png|450]]

Wenn die Standarderweiterung [[Daily notes|Tägliche Notizen]] aktiviert ist, fungieren Eigenschaften vom Typ Datum zusätzlich als interner Link zur täglichen Notiz für das entsprechende Datum.

![[Daily notes#^daily-notes-date]]

### JSON-Eigenschaften

Obwohl wir die Verwendung von YAML empfehlen, kannst du Eigenschaften auch im [JSON](https://www.json.org/)-Format definieren:

```json
---
{
  "tags": ["journal"],
  "publish": false
}
---
```

Beachte, dass der JSON-Block als YAML gelesen, intepretiert und gespeichert wird.

## Standardeigenschaften

Obsidian stellt eine Reihe von Standardeigenschaften bereit:

| Eigenschaft  | Typ   | Beschreibung                                                            |
| ------------ | ----- | ----------------------------------------------------------------------- |
| `tags`       | Liste | Siehe [[Bearbeiten und Formatieren/Tags\|Tags]].                        |
| `aliases`    | Liste | Siehe [[Aliases]].                                                      |
| `cssclasses` | Liste | Ermöglicht die Gestaltung einzelner Notizen mit [[CSS-Bausteine\|CSS]]. |

## Eigenschaften für Obsidian Publish

Folgende Eigenschaften können mit [[Obsidian Publish/Einführung|Obsidian Publish]] verwendet werden:

| Eigenschaft   | Beschreibung                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `publish`     | Siehe [[Publish your content#Automatically select notes to publish\|Notizen automatisch zur Veröffentlichung auswählen]]. |
| `permalink`   | Siehe [[Permalinks\|Permalinks]].                                                                                         |
| `description` | Siehe [[Social media link previews#Description\|Beschreibung]].                                                           |
| `image`       | Siehe [[Social media link previews#Image\|Bild]].                                                                         |
| `cover`       | Siehe [[Social media link previews#Image\|Bild]].                                                                         |

## Veraltete Eigenschaften

Diese Eigenschaften wurden mit Obsidian 1.4 als veraltet markiert und sollten durch ihre modernen Entsprechungen ersetzt werden. Ihre Unterstützung als [[#Standardeigenschaften]] wird mit Obsidian 1.9 eingestellt.

| Eigenschaft | Beschreibung                       |
| ----------- | ---------------------------------- |
| `tag`       | Veralteter Alias für `tags`.       |
| `alias`     | Veralteter Alias für `aliases`.    |
| `cssclass`  | Veralteter Alias für `cssclasses`. |

> [!tip] Wenn du alle deine Dateien auf das Format der neuen [[#Standardeigenschaften]] umstellen musst, kannst du den [[Format converter]] für die Stapelverarbeitung verwenden.

