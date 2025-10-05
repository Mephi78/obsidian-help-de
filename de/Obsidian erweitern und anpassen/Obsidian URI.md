---
aliases:
  - Obsidian URI verwenden
  - Fortgeschrittene Themen/Obsidian URI verwenden
  - Konzepte/Obsidian URI
---

*Obsidian URI* ist ein anwendungsspezifisches Protokoll, das es erlaubt, verschiedene Obsidian-Funktionen aufzurufen, bspw. das Öffnen oder Erstellen einer Notiz. Damit ermöglicht *Obsidian URI* Automation und anwendungsübergreifende Arbeitsabläufe.

## URI Format

Obsidian URIs verwenden das folgende Format:

```
obsidian://aktion?param1=wert&param2=wert
```

Der Parameter `aktion` definiert die Aktion, die ausgeführt werden soll. Verfügbare Aktionen:

- `open` öffnet eine Notiz.
- `new` erstellt eine neue Notiz oder fügt etwas zu einer vorhandenen hinzu.
- `daily` öffnet oder erstellt eine [[Tägliche Notiz|Tägliche Notiz]].
- `search` öffnet die [[Suche]].


> [!warning] Encoding
> Stelle sicher, dass deine Werte entsprechend [URL-encoded](https://de.wikipedia.org/wiki/URL-Encoding) sind. Schrägstriche `/` müssen bspw. durch `%2F` oder Leerzeichen durch `%20` ersetzt werden. Das ist besonders wichtig, da falsch kodierte "reservierte" Zeichen die URI-Interpretation beeinträchtigen können.

## Notiz öffnen

Die Aktion `open` öffnet einen Obsidian-Vault oder eine Notiz in diesem Vault.

### Anwendungsbeispiele

- `obsidian://open?vault=Mein%20Vault`
  Öffnet den Vault `Mein Vault`. Falls dieser bereits geöffnet ist, erhält er den Fokus.
- `obsidian://open?vault=ef6ca3e3b524d22f`
  Öffnet den Vault mit der ID `ef6ca3e3b524d22f`.
- `obsidian://open?vault=Mein%20Vault&file=Meine%20Notiz`
  Öffnet die Notiz `Meine Notiz.md` im Vault `Mein Vault`, vorausgesetzt die Notiz existiert.
- `obsidian://open?path=%2Fhome%2Fuser%2FMein%20Vault%2Fpfad%2Fzu%2FMeine%20Notiz`
  Sucht nach einem Vault unter dem Pfad `/home/user/Mein Vault/pfad/zu/Meine Notiz`. Gibt dann den Rest des Pfades an den `file` Parameter weiter. Wenn bspw. ein Vault existiert unter `/home/user/Mein Vault`, hätte diese Aktion dieselben Auswirkungen, wie wenn allein der `file` Parameter auf `pfad/zu/Meine Notiz` gesetzt wäre.


> [!tip] Überschrift oder Block öffnen
> Mit entsprechendem Encoding kannst du direkt zu einer Überschrift oder einem Block in einer Notiz springen. `Notiz%23Titel` springt zur Überschrift "Titel" und `Notiz%23%5EBlock` springt zum Block namens "Block".

### Parameter

- `vault` kann ein Vault-Name oder die Vault-ID[^1] sein.
- `file` kann ein Dateiname oder ein Pfad unterhalb des Vault-Wurzelverzeichnisses zu einer bestimmten Datei sein. Bei `md`-Dateien kann die Dateiendung weggelassen werden.
- `path` ein absoluter Pfad zu einer Datei.
  - Dieser Parameter überschreibt ggf. die beiden Parameter `vault` und `file`.
  - Die Anwendung wird nach einem Vault innerhalb des angegebenen Dateipfades suchen.
  - Der Rest des Pfades ersetzt dann den `file` Parameter.
- `prepend` wird Text am Anfang der Datei einfügen und versuchen, die Eigenschaften zusammenzuführen.
- `append` wird Text am Ende der Datei einfügen und versuchen, die Eigenschaften zusammenzuführen.

## Notiz erstellen

Die Aktion `new` erstellt eine neue Notiz im Vault, optional mit Textinhalt.

### Anwendungsbeispiele

- `obsidian://new?vault=Mein%20Vault&name=Meine%20Notiz`
  Öffnet den Vault `Mein Vault` und erstellt eine neue Notiz mit dem Titel `Meine Notiz`.
- `obsidian://new?vault=Mein%20Vault&file=pfad%2Fzu%2FMeine%20Notiz`
  Öffnet den Vault `Mein Vault` und erstellt eine neue Notiz im Pfad `pfad/zu/Meine Notiz`.

### Parameter

- `vault` kann ein Vault-Name oder die Vault-ID[^1] sein.
- `name` ist der Name der zu erstellenden Datei. Ist dieser spezifiziert, wird der Speicherort basierend auf deinem "Standardordner für neue Notizen" gewählt.
- `file` ist ein absoluter Pfad innerhalb des Vaults, den Dateinamen eingeschlossen. Überschreibt ggf. `name`.
- `path` ist ein globaler absoluter Pfad. Verhält sich ähnlich wie der Parameter `path` in der Aktion `open`. Überschreibt ggf. die beiden Parameter `vault` und `file`.
- `content` (optional) Textinhalt der Notiz.
- `clipboard` (optional) legt fest, dass der Inhalt der Zwischenablage verwendet wird, anstatt `content` zu spezifizieren.
- `silent` (optional) bewirkt, dass die Aktion ausgeführt wird, ohne die neue Notiz zu öffnen.
- `append` (optional) hängt den Text an eine existierende Notiz an, falls diese existiert.
- `overwrite` (optional) überschreibt eine ggf. bereits existierende Notiz, aber nur, wenn `append` nicht gesetzt ist.
- `x-success` (optional) siehe [[#X-Callback-URL Parameter verwenden]].

## Tägliche Notiz öffnen oder erstellen

Die Aktion `daily` erstellt oder öffnet deine [[Tägliche Notiz|Tägliche Notiz]]. Die Erweiterung muss dafür aktiviert sein.

### Anwendungsbeispiele

- `obsidian://daily?vault=Mein%20Vault`
   Öffnet den Vault `Mein Vault` und erstellt oder öffnet deine tägliche Notiz.

### Parameter

Die Aktion `daily` akzeptiert dieselben Parameter wie die [[#Notiz erstellen#Parameter|Aktion new]].

## Suche öffnen

Die Aktion `search` öffnet die [[Suche]] im angegebenen Vault und führt optional einen Suchterm aus.

### Anwendungsbeispiele

- `obsidian://search?vault=Mein%20Vault`
  Öffnet den Vault `Mein Vault` und darin die [[Suche]].
- `obsidian://search?vault=Mein%20Vault&query=Obsidian`
  Öffnet den Vault `Mein Vault` und führt darin die [[Suche]] nach `Obsidian` aus.

### Parameter

- `vault` kann ein Vault-Name oder die Vault-ID[^1] sein.
- `query` (optional) ein Suchbegriff.

## Hookmark-Integration

Diese Obsidian URI kannst du mit [Hookmark](https://hookproductivity.com/) verwenden. 

### Anwendungsbeispiele

`obsidian://hook-get-address`

### Parameter

- `vault` (optional) kann ein Vault-Name oder die Vault-ID[^1] sein. Ohne den Parameter wird der aktuelle oder zuletzt fokussierte Vault verwendet.
- `x-success` (optional) siehe [[#X-Callback-URL Parameter verwenden]].
- `x-error` (optional) siehe [[#X-Callback-URL Parameter verwenden]].

Wenn `x-success` definiert ist, wird die API den Wert als X-Callback-URL verwenden. Andernfalls wird ein Markdown-Link zur aktuell fokussierten Notiz in die Zwischenablage kopiert in der Form einer `obsidian://open`-URL.

## X-Callback-URL Parameter verwenden

Manche API-Endpunkte akzeptieren die X-Callback-URL Parameter `x-success` und `x-error`. Wenn vorhanden, übermittelt Obsidian die folgenden Informationen an den Callback `x-success`:

- `name` ist der Name der Datei ohne Dateiendung.
- `url` die `obsidian://`-URL für diese Datei.
- `file` (![[lucide-monitor-check.svg#icon]] nur Desktop) die `file://`-URL für diese Datei.

Wenn Obsidian bspw. die Anfrage `obsidian://.....x-success=myapp://x-callback-url` erhält, wird die Antwort so aussehen:
`myapp://x-callback-url?name=...&url=obsidian%3A%2F%2Fopen...&file=file%3A%2F%2F...`

## Verkürztes Format

Zusätzlich zu den oben beschriebenen Formaten sind zwei weitere, "verkürzte" Formate verfügbar, um Vaults und Dateien zu öffnen:

1. `obsidian://vault/Mein Vault/Meine Notiz` ist äquivalent zu `obsidian://open?vault=Mein%20Vault&file=Meine%20Notiz`.
2. `obsidian:///absoluter/pfad/zu/Meine Notiz` ist äquivalent zu `obsidian://open?path=%2Fabsoluter%2Fpfad%2Fzu%2FMeine%20Notiz`.

## Fehlerbehandlung

### Obsidian URI registrieren

Unter Windows und macOS sollte es ausreichen, die Anwendung einmal zu starten, um das Obsidian-URI-Protokoll auf deinem Rechner zu registrieren.

Wesentlich aufwendiger ist dieser Vorgang unter Linux:

1. Stelle sicher, dass du eine Datei `obsidian.desktop` erstellst. Weitere Informationen findest du in den [GNOME Developer Docs](https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html#desktop-files).
2. Stelle sicher, dass deine `.desktop`-Datei das Feld `Exec` als `Exec=executable %u` spezifiziert. `%u` wird verwendet, um die `obsidian://`-URIs an die Anwendung zu übergeben.
3. Wenn du den AppImage Installer verwendest, musst du diesen möglicherweise wie folgt entpacken: `Obsidian-x.y.z.AppImage --appimage-extract`. Dann stelle sicher, dass die `Exec` Direktive auf die entpackte ausführbare Datei verweist.


[^1]: Die Vault-ID ist ein zufälliger 16-Zeichen-Code, der dem Vault zugewiesen wurde, z.B. `ef6ca3e3b524d22f`. Diese ID ist eindeutig je Ordner auf deinem Rechner. Du findest die ID in der Vault-Verwaltung, indem du im Kontextmenü für den Vault auf "Vault-ID kopieren" klickst.
