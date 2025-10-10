---
permalink: plugins/werkbank
---

Mit der [[Standarderweiterungen|Standarderweiterung]] *Notizen-Werkbank* kannst du Notizen zusammenführen oder eine in mehrere Notizen aufteilen.

## Notizen zusammenfügen

Durch das Zusammenführen wird eine Notiz zu einer anderen hinzugefügt und die erste gelöscht. Die *Notizen-Werkbank* aktualisiert alle Links, so dass sie auf die zusammengeführte Notiz verweisen.

Bei der Auswahl einer Notiz, mit der eine andere zusammengeführt werden soll, kannst du zwischen folgenden Methoden wählen:

- `Eingabetaste`: Hängt die Quell-Notiz ans *Ende* der Ziel-Notiz.
- `Umschalt + Eingabetaste`: Fügt die Quell-Notiz am *Anfang* der Ziel-Notiz ein.
- `Strg + Eingabetaste` (oder `Cmd + Eingabetaste` unter macOS): Erstellt eine neue Notiz mit dem Inhalt der Quell-Notiz.

Um die aktive Notiz mit einer anderen in deinem Vault zusammenzuführen:

**Dateiexplorer**

1. Öffne mit Rechtsklick auf die Notiz, die du zusammenführen möchtest, das Kontextmenü.
2. Klicke **Verbinde gesamte Notiz mit...**.
3. Wähle die Notiz, mit der die erste zusammengeführt werden soll.
4. Bestätige die Sicherheitsabfrage über die Schaltfläche **Verbinden**.

**Befehlspalette**

1. Öffne die [[Befehlspalette]].
2. Wähle **Notizen-Werkbank: Verbinde aktive Notiz mit einer anderen Notiz...**.
3. Wähle die Notiz, mit der du die aktive zusammenführen möchtest.
4. Bestätige die Sicherheitsabfrage über die Schaltfläche **Verbinden**.

> [!tip] Tipp
> Standardmäßig erscheint eine Sicherheitsabfrage, bevor Notizen zusammengeführt werden. Falls du diese deaktivierst und versehentlich Notizen zusammenführst, kannst du dies mit Hilfe der Erweiterung [[Datenwiederherstellung]] wieder rückgängig machen.

## Notiz aufteilen

Wenn du eine Notiz auswählst, in welche die Selektion extrahiert werden soll, hast du folgende Methoden zur Auswahl:

- `Eingabetaste`: Hängt die Auswahl ans *Ende* der Ziel-Notiz.
- `Umschalt + Eingabetaste`: Fügt die Auswahl am *Anfang* der Ziel-Notiz ein.
- `Strg + Eingabetaste` (oder `Cmd + Eingabetaste` unter macOS): Erstellt eine neue Notiz mit dem ausgewählten Text.

Um Text in eine neue Notiz zu extrahieren:

**Editor**

1. Markiere im **Bearbeitungsmodus** den Text, den du extrahieren möchtest.
2. Öffne mit Rechtsklick auf die Selektion das Kontextmenü.
3. Wähle **Aktive Auswahl extrahieren...**.
4. Wähle die Notiz, in die der Text extrahiert werden soll.

**Befehlspalette**

1. Markiere im **Bearbeitungsmodus** den Text, den du extrahieren möchtest.
2. Öffne die [[Befehlspalette]].
3. Wähle den Befehl **Notizen-Werkbank: Aktive Auswahl extrahieren...**.
4. Wähle die Notiz, in die der Text extrahiert werden soll.

> [!tip] Tipp
> Standardmäßig wird in der Quell-Notiz der extrahierte Text durch einen Link zur Ziel-Notiz ersetzt. In den Einstellungen kannst du festlegen, ob stattdessen die neue Notiz [[Dateien einbetten|eingebettet]] oder gar nichts hinterlassen werden soll.

## Vorlagendatei

Durch Einrichten einer Vorlagendatei kannst du den extrahierten Text anpassen, bevor er in die neue Notiz eingefügt wird. Um eine Vorlage zu verwenden, gib den **Speicherort der Vorlagendatei** in den Erweiterungseinstellungen an.

Die Vorlage kann folgende Variablen enthalten:

| Variable          | Beschreibung                                                                                                                            |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `{{content}}`     | Platzhalter für den extrahierten Text. Falls du diese Variable nicht verwendest, fügt die Erweiterung den Text am Ende der Vorlage ein. |
| `{{fromTitle}}`   | Titel der Quell-Notiz.                                                                                                                  |
| `{{newTitle}}`    | Titel der Ziel-Notiz.                                                                                                                   |
| `{{date:FORMAT}}` | Erstellungsdatum der Notiz. Formatierungsbeispiel: `{{date:YYYY-MM-DD}}`.                                                               |
