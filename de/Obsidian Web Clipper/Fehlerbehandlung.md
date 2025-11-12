---
permalink: web-clipper/fehlerbehandlung
publish: true
---

Bei Problemen mit [[Einführung in Obsidian Web Clipper|Web Clipper]] kannst du Hilfe über den [offiziellen Discord-Kanal](https://discord.com/channels/686053708261228577/1285652864089198672) erhalten. Fehler kannst du auch im [GitHub Repository](https://github.com/obsidianmd/obsidian-clipper) melden.

## Allgemein

### Einige Inhalte fehlen

Standardmäßig versucht Web Clipper, die Inhalte einer Webseite intelligent zu erfassen. Möglicherweise funktioniert dies jedoch nicht auf allen Webseiten erfolgreich.

Web Clipper verwendet [Defuddle](https://github.com/kepano/defuddle), um nur den Hauptinhalt einer Webseite zu erfassen. Das schließt in der Regel nur Kopf- und Fußzeilen sowie weitere Zusatzelemente aus, kann jedoch manchmal dazu führen, dass Inhalte entfernt werden, die du gern behalten möchtest. Du kannst diesbezügliche Fehler [an Defuddle melden](https://github.com/kepano/defuddle).

So kannst du Defuddle in Web Clipper umgehen:

- Wähle Textabschnitte aus oder verwende `Cmd/Strg + A`, um den gesamten Text auszuwählen.
- [[Webseiten markieren|Markiere Inhalte]], um genau auszuwählen, was erfasst werden soll.
- Verwende eine [[Obsidian Web Clipper/Vorlagen|benutzerdefinierte Vorlage]] für die Webseite.

### In Obsidian erscheint kein Inhalt

Wenn du keine Inhalte in Obsidian siehst, nachdem du **Zu Obsidian hinzufügen** gewählt hast:

- Überprüfe Obsidian's [[Hilfe und Kontakt#Konsolenprotokolle auslesen|Entwicklerkonsole]] nach Fehlern.
- Prüfe, ob der Vaultname in den Web Clipper-Einstellungen genau mit dem Namen deines Vaults übereinstimmt (*nicht mit dem Vault-Pfad*).
- Prüfe, ob der Ordnername korrekt formatiert ist.

## Linux

#### Obsidian wird nicht geöffnet

- Stelle sicher, dass das [[Obsidian URI]]-Protokoll [[Obsidian URI#Obsidian URI registrieren|registiert]] ist.
- Wenn du Firefox verwendest, musst du dieses möglicherweise in den [Browsereinstellungen registrieren](https://kb.mozillazine.org/Register_protocol).

#### Obsidian startet, aber nur der Dateiname wird gespeichert

Wahrscheinlich kann Obsidian nicht auf deine Zwischenablage zugreifen. Der Zugriff auf die Zwischenablage wird benötigt, um Daten aus deinem Browser nach Obsidian zu übertragen. Deine Einstellungen können sich darauf auswirken, wie Apps in Sandboxen ausgeführt werden sowie auf die Berechtigungen für die Zwischenablage.

Wenn du Wayland verwendest, stelle sicher, dass Obsidian die Leseberechtigung auf deine Zwischenablage besitzt, wenn die Anwendung nicht den Fokus hat. Bspw. in deiner Hyprland-Konfiguration:

```ini
# hyprland.conf
misc {
    focus_on_activate = true
}
```

- Falls du Flatpak verwendest, versuche es mit einer [offiziell unterstützten Obsidian-Version](https://obsidian.md/download).
- Als Umgehungslösung kannst du über die **Web Clipper-Einstellungen** → **Allgemein** in den **Legacy-Modus** wechseln. Das umgeht die Zwischenablage und speichert den Inhalt direkt über die URI. Beachte, dass dadurch die Anzahl der Zeichen begrenzt ist, die erfasst werden können, je nach Browser und Linux-Distribution.

## iOS und iPadOS

So aktivierst du die Web Clipper-Erweiterung für Safari:

1. Öffne Safari und tippe auf die Schaltfläche ganz links in der URL-Leiste des Browsers, die wie ein Rechteck mit Linien darunter aussieht.
2. Wähle **Erweiterungen verwalten**.
3. Aktiviere **Obsidian Web Clipper** in der Erweiterungsliste.
4. Schließe das Menü.
5. Um die Erweiterung zu verwenden, tippe das **Puzzle-Symbol** in der URL-Leiste.

So lässt du Web Clipper auf allen Webseiten zu:

1. Öffne die iOS-**Einstellungen** →  **Apps** →  **Safari** →  **Erweiterungen**.
2. Unter **Berechtigungen** die Ausführung auf allen Webseiten zulassen.

So erlaubst du Obsidian, immer Inhalte von Web Clipper zu empfangen:

1. Öffne die iOS-**Einstellungen** →  **Apps** →  **Obsidian**.
2. Setze **Aus anderen Apps einfügen** auf **Zulassen**.
