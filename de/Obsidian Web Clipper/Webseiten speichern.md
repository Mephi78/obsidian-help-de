---
aliases:
  - Obsidian Web Clipper/Erfasse Webseiten
permalink: web-clipper/erfassen
publish: true
---

Sobald du die Browsererweiterung [[Einführung in Obsidian Web Clipper|Web Clipper]] installiert  hast, kannst du browserabhängig auf verschiedene Weise darauf zugreifen:

1. Über das Obsidian-Symbol in der Werkzeugleiste deines Browsers.
2. Oder über Tastenkürzel, wenn du die Erweiterung mittels Tastatur aktivieren möchtest.
3. Oder über ein Kontextmenü, das du mit Rechtsklick auf die Webseite öffnest, die du gerade besuchst.

Um eine Webseite in Obsidian zu speichern, wähle **Zu Obsidian hinzufügen**.

## Webseite erfassen

Wenn du die Erweiterung öffnest, extrahiert Web Clipper die Daten aus der aktiven Webseite gemäß den Einstellungen in deiner [[Obsidian Web Clipper/Vorlagen|Vorlage]]. Du kannst eigene Vorlagen erstellen und unter Verwendung von [[Variablen|Variablen]] und [[Filter|Filtern]] an deine Bedürfnisse anpassen.

Standardmäßig versucht der Web Clipper, nur den Hauptartikel zu extrahieren und weitere Elemente auszuschließen. Du kannst dieses Verhalten jedoch wie folgt überschreiben:

- Wenn eine benutzerdefinierte Vorlage vorhanden ist, wird diese verwendet.
- Wenn Seiteninhalt ausgewählt wurde, wird die Auswahl verwendet. Mit `Strg/Cmd + A` kannst du die gesamte Seite auswählen.
- Wenn [[Webseiten markieren|Markierungen]] vorgenommen wurden, werden diese verwendet.

## Bilder herunterladen

Bilder werden vom Web Clipper nicht automatisch heruntergeladen. Stattdessen werden Verweise zur Original-URL verwendet. Das spart Speicherplatz in deinem Vault, bedeutet aber auch, dass Bilder im Offline-Betrieb oder wenn die URL nicht mehr funktioniert, nicht angezeigt werden.

Du kannst Bilder für jede Datei in Obsidian herunterladen über die Aktion **Anhänge für die aktuelle Datei herunterladen** aus der [[Befehlspalette]]. Du kannst diesem Befehl auch ein Tastenkürzel zuweisen.

## Tastenkürzel

Web Clipper stellt Tastenkürzel zur Verfügung, mit denen sich deine Arbeitsabläufe beschleunigen lassen. Um die Tastenkürzel zu ändern, öffne die **Web Clipper-Einstellungen** → **Allgemein** und folge den Anweisungen deines Browsers im Abschnitt **Tastenkombinationen**. Mit Ausnahme von Safari unterstützen alle Browser eine Anpassung von Tastenkürzeln.

| Aktion                     | macOS                   | Windows/Linux         |
| -------------------------- | ----------------------- | --------------------- |
| Web Clipper öffnen         | `Cmd + Umschalt + O`    | `Strg + Umschalt + O` |
| Schnell ausschneiden       | `Option + Umschalt + O` | `Alt + Umschalt + O`  |
| Highlighter-Modus wechseln | `Option + Umschalt + H` | `Alt + Umschalt + H`  |

## Schnittstellenfunktionen

Die Benutzerschnittstelle der Browsererweiterung ist in vier Abschnitte unterteilt:

1. In der **Kopfzeile** kannst du die Vorlage wechseln, den [[Webseiten markieren|Marker]] aktivieren und auf die Einstellungen zugreifen.
2. **Eigenschaften** zeigt die aus der Webseite extrahierten Metadaten, die in Obsidian als [[Eigenschaften|Dateieigenschaften]] gespeichert werden.
3. Der **Notiz-Inhalt**, der nach Obsidian gespeichert wird.
4. In der **Fußzeile** kannst du den Vault und Ordner wählen und über eine Schaltfläche die Seite zu Obsidian hinzufügen.

Kopfzeilen-Funktionen:

- **Vorlage**: eine Auswahlliste, um zwischen deinen gespeicherten [[Obsidian Web Clipper/Vorlagen|Vorlagen]] zu wechseln, die du in den Web Clipper-Einstellungen hinzugefügt hast.
- **Seitenvariablen anzeigen ( ... )**: zeigt Variablen an, die du in Vorlagen verwenden kannst.
- **Marker**: eine Schaltfläche, um den [[Webseiten markieren|Marker-Modus]] zu wechseln.
- **In Seite öffnen**: öffnet den Web Clipper-Dialog direkt als Seitenleiste im Browserfenster.
- **Einstellungen ( ![[lucide-settings.svg#icon]] )**: öffnet die Web Clipper-Einstellungen.

Fußzeilen-Funktionen:

- **Zu Obsidian hinzufügen**: Schaltfläche, um die Daten nach Obsidian zu speichern.
- **Vault**: eine Auswahlliste, um zwischen den Vaults zu wechseln, die du über die Web Clipper-Einstellungen hinzugefügt hast.
- **Ordner**: gib hier den Namen eines Ordners ein, in dem die Notiz gespeichert werden soll.
- **Interpreter**: um [[Webseiten interpretieren|Prompts in natürlicher Sprache]] auf die Webseite anzuwenden.

