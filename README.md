## Mitmachen

### So geht's

- erstelle einen Fork [dieses Repositories](https://github.com/Mephi78/obsidian-help-de)
- achte darauf, **alle Branches** zu forken, indem du das Häkchen neben *Copy the `master` branch only* entfernst!

![Screenshot Fork All Branches](https://raw.githubusercontent.com/Mephi78/obsidian-help-de/translation-guide/obsidian-help-de-anleitung-fork.png)

- checke den `translation-colab` Branch aus
- nun erstelle daraus deinen eigenen neuen Branch und benenne ihn, wie du möchtest

```bash
$ git checkout translation-colab
$ git checkout -b dein-neuer-branch-name
```

- erstelle ein [Issue](https://github.com/Mephi78/obsidian-help-de/issues) mit einer Liste der Seiten, die du bearbeiten möchtest und warte, dass dir die Aufgabe zugewiesen wird
- übersetze die dir zugeordneten Seiten in deiner lokalen Kopie
- öffne dazu den Ordner `de` deiner lokalen Kopie als Obsidian Vault, während du deinen neuen Branch ausgecheckt hast
- achte darauf, keine Dateinamen (Titel der Notiz) zu ändern
- interne Links kannst du so übersetzen:

```md
[LINK BLEIBT SO|Deine Übersetzung als alternativer Linktext]
```

- pushe deine Änderungen wie gewohnt

```
$ git add .
$ git commit -m 'Add translation #issue'
$ git push
```

- wenn du eine (oder mehrere) Seiten komplett übersetzt hast, erstelle einen Pull Request auf den Branch `translation-colab` und gib im Titel das zugehörige Issue an

### Was wird übersetzt

Grundsätzlich werden alle Inhalte des Vaults übersetzt, wie hier nicht abschließend aufgezählt:

- Notizen
- Notiz- und Verzeichnisnamen
- Aliasse
- Permalinks
- Bezeichnungen von Anhängen
- Alternative Linktexte
- Metadaten im Feld `description`

> [!WARNING] Achtung!
> Wir bitten dich darum, Übersetzungsvorschläge für **Notiz- und Verzeichnisnamen** sowie **Bezeichnungen von Anhängen** im Issue oder PR zu notieren, aber diese nicht selbst zu ändern, da hiervon für gewöhnlich mehrere Notizen betroffen sind.

Zur Orientierung hier eine Übersicht der Darstellungsreihenfolge der Verzeichnisse (oberste Ebene im Obsidian-Dateiexplorer) nach dem Veröffentlichen des Vaults als Webseite. Themen, die zuerst übersetzt werden sollten, sind hervorgehoben.

| Englisch                  | Deutsch                           |
|---------------------------|-----------------------------------|
| Getting started           | ==Erste Schritte==                |
| Import notes              | Notizen Importieren               |
| User interface            | ==Benutzerschnittstelle==         |
| Editing and formatting    | ==Bearbeiten und Formatieren==    |
| Linking notes and files   | ==Notizen und Dateien verlinken== |
| Files and folders         | Dateien und Verzeichnisse         |
| Plugins                   | ==Integrierte Erweiterungen==     |
| Obsidian Publish          | ==Obsidian Publish==              |
| Obsidian Sync             | ==Obsidian Sync==                 |
| Obsidian Web Clipper      | Obsidian Web Clipper              |
| Extending Obsidian        | Obsidian erweitern und anpassen   |
| Contributing to Obsidian  | Mitmachen                         |
| Licenses and payment      | Lizenzen und Zahlung              |
| Teams                     | Teams                             |
| Obsidian                  | Obsidian                          |
### Tricks & Kniffe

> [!TIP] Überschriften übersetzen
> Achte darauf, **Überschriften** zu übersetzen, indem du im Editor mit Rechtsklick auf die Überschrift das Kontextmenü aufrufst und **Diese Überschrift umbenennen...** auswählst. Auf diese (und **nur auf diese**) Weise aktualisieren sich Links auf Überschriften im gesamten Vault automatisch. 
> Wichtig: **Optionen > Dateien & Links > Links immer aktualisieren** muss aktiviert sein!

### Verwendung von KI

KI-generierte Übersetzungen werden **nicht akzeptiert**. Wer offensichtlich KI-generierte Texte in seinen Pull Request einschließt, wird von der Beteiligung an diesem Repository ausgeschlossen.

Das hat einen ganz einfachen Grund: Die Nutzungsbedingungen von KI-Werkzeugen zur Texterstellung beinhalten in den allermeisten Fällen die Klausel, dass der Leser nicht im Glauben gelassen werden darf, ein solcher Text sei ausschließlich von einem Menschen erstellt worden. Es ist also eine schlichte Lizenzfrage und Diskussionen darüber sollten hiermit von vornherein ausgeschlossen sein.

### Wie ist der Arbeitsstand

Den aktuellen Arbeitsstand der deutschen Übersetzung kannst du sehen, wenn du diesen **Translation Guide** in deine lokale Kopie des Vaults einfügst.

- kopiere dazu die Datei [`README.md`](https://github.com/Mephi78/obsidian-help-de/blob/translation-guide/README.md) und füge sie als neue Notiz ins Wurzelverzeichnis deiner lokalen Kopie des `/de`-Vaults ein
- installiere die externe Erweiterung [Dataview](https://blacksmithgu.github.io/obsidian-dataview/) und aktiviere in den Einstellungen die *Javascript Queries* UND *Inline Javascript Queries*, um die [[#Berichte]] unten ordentlich anzuzeigen

> [!WARNING] Achtung - **Diese Notiz nicht in den Master mergen!**
> Damit diese Notiz nicht versehentlich in den Master übernommen wird, führe nach dem Stagen deiner Änderungen den folgenden Befehl aus, um die Datei von deinem Commit auszuschließen.
> 
> ```bash
> $ git reset -- README.md
> ```

### Aktualisierungen im Master

Das englische Original der Obsidian Hilfeseiten lebt und wächst weiter. Daher wird es von Zeit zu Zeit notwendig sein, auch die deutsche Übersetzung anzupassen.

Zu diesem Zweck erstellen wir ein **Update-Issue** und aktualisieren anschließend den Branch `translation-colab` überwacht.

```
$ git switch master
$ git pull
$ git switch translation-colab
$ git pull
$ git merge master
$ git push origin
```

Wurden mit der Aktualisierung Dateien im Verzeichnis `/en` geändert, werden ihre deutschen Pendants im Anschluss mit `#UPDATE` getagged und die notwendigen Änderungen im zugehörigen Issue als TODO vermerkt.
## Berichte

> [!INFO] [Dataview Plugin](https://blacksmithgu.github.io/obsidian-dataview/) erforderlich

> [!TIP]- In Bearbeitung: **`$= dv.span( dv.pages("#WIP").length )`**
> **Wenn erledigt, `#WIP` entfernen!**
> 
> ```dataview
> TABLE WITHOUT ID
> file.link AS Seite, file.etags AS Bearbeiter
> FROM #WIP
> SORT file.name ASC
> ```

> [!WARNING]- Offen: **`$= dv.span( dv.pages("#TODO").length )`** von `$= dv.span( dv.pages().length-1 )`
> **In Bearbeitung setzen: `#TODO` ersetzen durch `#WIP/<BEARBEITERKÜRZEL>`**
> 
> ```dataview
> LIST WITHOUT ID
> FROM #TODO
> SORT file.name ASC
> ```

> [!QUESTION]- Aktualisierung erforderlich: **`$= dv.span( dv.pages("#UPDATE").length )`** von `$= dv.span( dv.pages().length-1 )`
> **Falls der englische Master Aktualisierungen enthält seit der Übersetzung, werden davon betroffene Notizen mit `#UPDATE` getagged und damit wieder zur Bearbeitung markiert.**
> 
> **In Bearbeitung setzen: `#UPDATE` ersetzen durch `#WIP/<BEARBEITERKÜRZEL>`**
> 
> ```bash
> $ git diff <COMMIT_SHA> HEAD -- en/
> ```
> 
> ```dataview
> LIST WITHOUT ID
> FROM #UPDATE
> SORT file.name ASC
> ```

> [!SUCCESS]+ Erledigt: **`$= dv.span( dv.pages().where( p => !p.file.tags.includes("#WIP") && !p.file.tags.includes("#TODO") && !p.file.tags.includes("#UPDATE") ).length-1 )`** von `$= dv.span( dv.pages().length-1 )`
> ```dataview
> LIST WITHOUT ID
> FROM -#TODO AND -#WIP AND -#UPDATE
> SORT file.name ASC
> ```
