---
permalink: publish/verwalten
publish: true
---

Verwalte eine oder mehrere Webseiten mit [[Einführung in Obsidian Publish|Obsidian Publish]].

Eine Webseite ist eine Sammlung von Notizen, die in Obsidian Publish gehostet wird und online verfügbar ist, entweder über eine Obsidian Publish-Adresse oder deine [[Eigene Domain|eigene Domain]].

## Neue Webseite erstellen

> [!note] Die Anzahl der Webseiten, die du erstellen kannst, ist abhängig von deinem Obsidian Publish-Abo. Stelle sicher, dass dein Kontingent es erlaubt, eine neue Seite zu erstellen.

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Wenn du bereits eine Webseite hast, wähle **Seite wechseln** ( ![[lucide-repeat.svg#icon]] ).
3. Gib im Feld **Website-ID** den gewünschten Pfad für deine Webseite ein. Bspw. wird eine Seite mit der ID `meine-fantastische-seite` verfügbar sein unter `publish.obsidian.md/meine-fantastische-seite`.
4. Bestätige mit **Erstellen**.

## Webseite löschen

> [!note] Alle Notizen verbleiben in deinem Vault, auch wenn du eine Webseite löschst.

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Wähle **Seite wechseln** ( ![[lucide-repeat.svg#icon]] ).
3. Wähle **Website löschen** ( ![[lucide-x.svg#icon]] ) rechts neben der Seite, die du löschen möchtest.
4. Klicke **Löschen**, um den Löschvorgang zu bestätigen.

## Zwischen Webseiten wechseln

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Wähle **Seite wechseln** ( ![[lucide-repeat.svg#icon]] ).
3. Klicke **Auswählen** rechts neben der Seite, zu der du wechseln möchtest.

## Webseiten-ID ändern

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Wähle **Seite wechseln** ( ![[lucide-repeat.svg#icon]] ).
3. Wähle **Website-ID bearbeiten** ( ![[lucide-edit-3.svg#icon]] ) rechts neben der Seite, die du bearbeiten möchtest.
4. Gib in **Website-ID** die neue ID für deine Seite ein.
5. Bestätige mit **Ändern**.

## Webseiten-Einstellungen anzeigen

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).

## Seiteneinstellungen

### Allgemein

| Option                                   | Typ          | Beschreibung                                                                                                                                   |
| ---------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Name der Website                         | Eingabe      | Der öffentliche Name und Titel deiner Obsidian Publish-Webseite.                                                                               |
| Startseite                               | Eingabe      | Der Pfad zur Markdown-Datei, die als Startseite angezeigt werden soll.                                                                         |
| Logo                                     | Eingabe      | Ein Bild, das du als Seiten-Logo verwenden möchtest. Die Bilddatei muss [[Inhalte veröffentlichen#Notizen veröffentlichen\|veröffentlicht]] werden.         |
| Website-Zusammenarbeit                   | Schaltfläche | Bestimme andere Benutzer, die Bearbeitungsrechte auf deine veröffentlichten Dateien erhalten sollen. Diese benötigen ein Obsidian-Nutzerkonto. |
| Eigene Domain                            | Schaltfläche | [[Eigene Domain]]                                                                                                                              |
| Verbiete Indizierung durch Suchmaschinen | Schalter     | Es wird eine Datei `robots.txt` hinzugefügt, um respektvolle Suchmaschinen daran zu hindern, deine Webseite zu indizieren.                     |

### Darstellung

| Option                 | Typ      | Beschreibung                                                                                |
| ---------------------- | -------- | ------------------------------------------------------------------------------------------- |
| Farbschema             | Auswahl  | Wähle den Standard-Anzeigemodus: **Hell**, **Dunkel** oder **Systemeinstellung verwenden**. |
| Hell/Dunkel umschalten | Schalter | Erlaube Besuchern, den Hell-/Dunkel-Modus umzuschalten.                                     |

## Lese-Erlebnis

| Option                 | Typ      | Beschreibung                                                                                                   |
| ---------------------- | -------- | -------------------------------------------------------------------------------------------------------------- |
| Vorschau anzeigen      | Schalter | Entscheide, ob beim Überfahren mit dem Mauszeiger eine Seitenvorschau für interne Links angezeigt werden soll. |
| Seitentitel ausblenden | Schalter | Entscheide, ob der Seitentitel einer Notiz als erste Überschrift angezeigt werden soll.                        |
| Lesbare Zeilenlänge    | Schalter | Entscheide, ob die lesbare Zeilenlänge begrenzt werden soll.                                                   |
| Strenge Zeilenumbrüche | Schalter | Entscheide, ob strenge Zeilenumbrüche angewendet werden sollen.                                                |
| Seiten stapeln         | Schalter | Entscheide, ob deine Webseite [[Registerkarten#Tab-Gruppen stapeln\|gestapelte Tabs]] verwenden soll.          |

### Komponenten

| Option                 | Typ          | Beschreibung                                                                                                                                                |
| ---------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navigation anzeigen    | Schalter     | Aktiviere eine [[Dateiexplorer]]-Sicht zur Navigation auf deiner Webseite.                                                                                  |
| Navigation anpassen    | Schaltfläche | [[Webseite individualisieren#Navigation anpassen\|Bearbeite]] die Anzeigereihenfolge deiner Dateien und Ordner, wenn die Navigations-Anzeige aktiviert ist. |
| Suche anzeigen         | Schalter     | Entscheide, ob ein Suchfeld angezeigt werden soll.                                                                                                          |
| Graph-Ansicht anzeigen | Schalter     | Entscheide, ob eine [[Graph-Ansicht#Lokaler Graph\|Graph-Ansicht]] in der rechten Seitenleiste deiner Webseite angezeigt werden soll.                       |
| Gliederung anzeigen    | Schalter     | Entscheide, ob ein [[Gliederung\|Inhaltsverzeichnis]] für die aktive Seite angezeigt werden soll.                                                           |
| Rückverweise anzeigen  | Schalter     | Entscheide, ob [[Rückverweise]] angezeigt werden sollen.                                                                                                    |

### Andere Seiten-Einstellungen

| Option                         | Typ          | Beschreibung                                                                                                                               |
| ------------------------------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Passwörter                     | Schaltfläche | [[Obsidian Publish/Sicherheit und Datenschutz#Webseiten-Passwort hinzufügen\|Setze ein Passwort]], um den Zugriff auf die gesamte Webseite zu beschränken. |
| Google Analytics Tracking-Code | Eingabe      | **Nur mit eigener Domain**. Trage deinen Google Analytics Tracking-Code hier ein.                                                          |
