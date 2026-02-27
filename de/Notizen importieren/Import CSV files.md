---
permalink: import/csv
---

Obsidian lässt dich über das offizielle [[Importer]]-Plugin Daten aus CSV-Dateien importieren. Das ist nützlich, wenn du tabellarische Daten in Anwendungen wie Excel, Google Sheets, Numbers, Notion oder Airtable gespeichert hast.

Der CSV-Import generiert Markdown-Dateien für jede Zeile und eine [[Einführung in Bases|Base]]-Datei, die alle importierten Dateien in einer Tabelle anzeigt.

Wenn du Notizen aus einer bestimmten Anwendung importierst, solltest du zunächst die Liste der vom [[Importer]]-Plugin unterstützten Anwendungen überprüfen, um herauszufinden, ob es einen spezifischen Konverter gibt, der die zu migrierenden Daten besser überführt.

## Notizen aus CSV-Daten erzeugen in Obsidian

Du benötigst hierfür das offizielle [[Importer]]-Plugin von Obsidian, das du [hier installieren](obsidian://show-plugin?id=obsidian-importer) kannst.

1. Öffne die **Einstellungen**.
2. Unter **Externe Erweiterungen** → **Community-Erweiterungen**  [installiere das *Importer*-Plugin](obsidian://show-plugin?id=obsidian-importer).
3. Aktiviere das Importer-Plugin.
4. Öffne das **Importer**-Plugin über die Befehlspalette oder die Schaltfläche in der Werkzeugleiste.
5. Unter **File format** wähle **CSV (.csv).**
6. Wähle den Speicherort deiner CSV-Datei aus.
7. Wähle **Import**, um zu konfigurieren, wie die CSV-Daten in Notizen mit [[Eigenschaften]] konvertiert werden sollen.
8. Wähle **Continue** und warte, bis der Import abgeschlossen ist.
9. Du hast es geschafft!

## Import von CSV-Feldern konfigurieren

Im zweiten Schritt des CSV-Imports kannst du mit Hilfe einer Vorlage festlegen, wie die Daten importiert werden sollen.

Jeder Spalte in deiner CSV-Datei wird anhand des Namens der Kopfzelle eine Variable `{{spalten_name}}` zugewiesen. Diese Variablen kannst du verwenden, um den Namen, Speicherort und Inhalt sowie [[Eigenschaften]] der resultierenden Notiz zu definieren.