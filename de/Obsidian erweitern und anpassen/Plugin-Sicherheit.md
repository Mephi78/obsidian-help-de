---
permalink: plugin-sicherheit
publish: true
---

Das Obsidian-Team nimmt Sicherheit sehr ernst. Hier erläutern wir die Risiken, die mit der Installation von [[Externe Erweiterungen|externen Erweiterungen]] verbunden sind und welche Maßnahmen wir ergreifen, um diese möglichst gering zu halten.

## Eingeschränkter Modus

Standardmäßig läuft Obsidian im *Eingeschränkten Modus*, um die Ausführung von Drittanbieter-Code zu verhindern. Du solltest den eingeschränkten Modus nur dann ausschalten, wenn du den Autoren der Plugins vertraust, die in deinem Vault installiert sind.

Um den *Eingeschränkten Modus* zu deaktivieren:

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Externe Erweiterungen**.
3. Klicke **Community-Erweiterungen aktivieren**.

Um den *Eingeschränkten Modus* zu aktivieren:

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Externe Erweiterungen**.
3. Klicke neben **Eingeschränkter Modus** auf **Einschalten**.

Wenn du den *Eingeschränkten Modus* einschaltest, verbleiben bereits installierte Erweiterungen zwar in deinem Vault, aber sie werden dann von Obsidian ignoriert.

## Plugin-Fähigkeiten

Aufgrund technischer Einschränkungen kann Obsidian die Berechtigungen oder Zugriffsebenen für Drittanbieter-Erweiterungen nicht zuverlässig beschränken. Das bedeutet, Plugins übernehmen die Zugriffsebenen von Obsidian. Beachte daher anhand folgender Beispiele, welche Möglichkeiten externen Erweiterungen offen stehen.

Community-Erweiterungen können:

- auf Dateien auf deinem Rechner zugreifen.
- eine Verbindung ins Internet herstellen.
- zusätzliche Programme auf deinem Rechner installieren.

> [!tip] Tipp
> Falls du mit sensiblen Daten arbeitest und eine externe Erweiterung installieren möchtest, empfehlen wir dir, vor der Verwendung eine unabhängige Sicherheitsprüfung des Plugins durchzuführen.

## Plugin-Prüfprozess

Nachdem eine Community-Erweiterung im Plugin Store eingereicht wurde, wird sie einer ersten Prüfung unterzogen. Alle Plugins müssen den [Obsidian-Entwicklerrichtlinien](https://docs.obsidian.md/Developer+policies) entsprechen.

Das Obsidian-Team ist klein und wir können nicht jede neue Version der externen Plugins manuell prüfen. Wir vertrauen stattdessen auf die Unterstützung der Community, Probleme mit externen Erweiterungen frühzeitig zu erkennen und zu melden.

- Falls du kleinere Sicherheitslücken in einer Community-Erweiterung entdeckst, lies bitte die `security.md` oder `readme.md` des Plugin-Entwicklers, um zu erfahren, wie du diese melden kannst.
- Schwerwiegende Sicherheitslücken solltest du **zusätzlich** dem [[Hilfe und Kontakt#Obsidian Support kontaktieren|Obsidian Support]] melden.
- Wenn du vermutest, dass eine Erweiterung bösartig ist, melde dies bitte direkt dem [[Hilfe und Kontakt#Obsidian Support kontaktieren|Obsidian Support]] oder sende eine Direktnachricht an unsere Moderatoren.


