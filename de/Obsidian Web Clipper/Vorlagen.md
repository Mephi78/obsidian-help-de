---
permalink: web-clipper/vorlagen
description: Erfahre, wie du Vorlagen für Web Clipper erstellst, die Metadaten von Webseiten automatisch erfassen.
publish: true
---

Mit [[Einführung in Obsidian Web Clipper|Web Clipper]] kannst du Vorlagen erstellen, die automatisch Metadaten und Inhalte von Webseiten erfassen. Im [clipper-templates Repository](https://github.com/kepano/clipper-templates) findest du einige Beispiel-Vorlagen. 

## Vorlage erstellen oder bearbeiten

Um eine Vorlage zu **erstellen**, gehe in die Web Clipper-Einstellungen und wähle **Neue Vorlage** in der Seitenleiste. Im sich öffnenden Dialog **Vorlage bearbeiten** kannst du über die Option **Mehr** rechts oben auch eine Vorlage **duplizieren**.

Um eine Vorlage zu **bearbeiten**, wähle diese in der Seitenleiste aus. Deine Änderungen werden automatisch gespeichert.

Vorlagen verwenden [[Variablen]] und [[Filter]], mit denen du individuell anpassen kannst, wie Webinhalte gespeichert werden.

## Vorlagen importieren oder exportieren

So importierst du eine Vorlage:

1. Öffne die Web Clipper-**Einstlellungen** ( ![[lucide-settings.svg#icon]] ) in der Browsererweiterung.
2. Wähle irgendeine Vorlage aus der Seitenleiste.
3. Wähle **Importieren** rechts oben im Dialog **Vorlage bearbeiten**.
4. Ziehe eine `.json`-Vorlage auf den Dialog **Vorlage importieren** oder füge JSON in das Textfeld ein.
5. Bestätige mit **Importieren**. Es wird eine neue Vorlage erstellt.

Um eine Vorlage zu exportieren, wähle **Exportieren** rechts oben im Dialog **Vorlage bearbeiten**. Die Vorlage wird als `.json`-Datei heruntergeladen.

Über **Mehr** → **Als JSON kopieren** kannst du die Vorlage auch in die Zwischenablage kopieren.

## Vorlagen-Einstellungen

### Verhalten

So bestimmst du, wie Web Clipper Inhalte nach Obsidian speichert:

- **Neue Notiz erstellen**
- **Zu  bestehender Notiz hinzufügen** (am Anfang oder Ende)
- **Zur Tagesnotiz hinzufügen** (am Anfang oder Ende): beachte, dass hierfür die Erweiterung [[Tägliche Notiz]] aktiviert sein muss
- **Notiz überschreiben**

### Vorlage automatisch auslösen

Vorlagen-Auslöser sorgen dafür, dass eine Vorlage automatisch ausgewählt wird, basierend auf der URL oder den [Schema.org](https://schema.org/)-Daten in der zu erfassenden Webseite. Du kannst für jede Vorlage mehrere, durch Zeilenumbruch getrennte Regeln definieren.

Die erste Übereinstimmung in deiner Vorlagen-Liste bestimmt, welche Vorlage verwendet wird. Du kannst die Reihenfolge der Vorlagen ändern, indem du sie in der Seitenleiste per Drag & Drop verschiebst.

#### Einfacher URL-Abgleich

Der einfache Abgleich löst eine Vorlage aus, wenn die URL der aktiven Webseite mit dem angegebenen Muster *beginnt*, z.B. mit `https://obsidian.md`.

#### Verwendung von regulären Ausdrücken

Vorlagen können mit Hilfe von regulären Ausdrücken auch basierend auf komplexeren URL-Mustern ausgelöst werden. Schließe den regulären Ausdruck in Schrägstriche (`/`) ein. Denke daran, Sonderzeichen (wie `.` oder `/`) in regulären Ausdrücken mit einem Backslash (`\`) zu escapen.

Beispiel: `/^https:\/\/www\.imdb\.com\/title\/tt\d+\/reference\/?$/` setzt den Auslöser auf jede IMDB-Webseite.

#### Verwendung von Schema.org

Du kannst den Auslöser auf in einer Webseite vorhandene [schema.org](https://schema.org/)-Daten setzen. Verwende das Präfix `schema:` gefolgt von einem Schema-Schlüssel, auf den du abgleichen möchtest. Optional kannst du einen erwarteten Wert angeben.

Einige Beispiele:

- `schema:@Recipe` reagiert auf Webseiten mit dem Schema-Typ "Recipe".
- `schema:@Recipe.name` wird mit Seiten übereinstimmen, die `@Recipe.name` enthalten.
- `schema:@Recipe.name=Kekse` stimmt mit Seiten überein, deren `@Recipe.name` auf "Kekse" gesetzt ist.

Schema.org-Werte können auch verwendet werden, um [[Variablen#Schema.org-Variablen|Vorlagen-Daten vorauszufüllen]].

### Interpreter-Kontext

Wenn die [[Webseiten interpretieren|Interpreter]]-Funktion aktiviert ist, kannst du [[Variablen#Prompt-Variablen|Prompt-Variablen]] verwenden, um Seiteninhalte mit Hilfe natürlicher Sprache zu extrahieren. Du kannst für jede Vorlage den [[Webseiten interpretieren#Kontext|Kontext]] bestimmen, auf den Interpreter zugreifen soll. 