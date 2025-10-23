---
permalink: teams/verteilung
---

Obsidian läuft als lokale Anwendung auf den Geräten deiner Team-Mitglieder. Du kannst damit online und offline, sicher und privat arbeiten und behältst dabei die volle Kontrolle über die Daten deines Teams. Obsidian ist nicht als Webanwendung verfügbar, daher musst du die Anwendung für das gesamte Team bereitstellen.

## Obsidian installieren und aktualisieren


Dein Team kann Obsidian auf unserer Webseite [herunterladen](https://obsidian.md/download). Die Releases sind auch auf unserer [GitHub-Release-Seite](https://github.com/obsidianmd/obsidian-releases/releases) verfügbar, die Änderungshistorie findest du im [Changelog](https://obsidian.md/changelog/).

> [!tip] Die Installation unter Windows mit dem System-Installer kann mit der Option "Für alle Benutzer" durchgeführt werden.

Wenn du in dein Einstellungen **Automatische Aktualisierungen** erlaubst, werden neue Versionen automatisch installiert beim Neustart von Obsidian. Zusätzlich empfehlen wir regelmäßige [[Aktualisiere Obsidian#Installer Updates|Installer-Aktualisierungen]], um das Electron Framework einschließlich der Sicherheitspatches auf dem aktuellsten Stand zu halten.

Erfahre mehr darüber, wie du den Netzwerkzugriff während dieses Prozesses beschränken kannst unter [[Sicherheitsbetrachtungen für Teams#Netzwerk und Zugriff|Netzwerk und Zugriff]].

## Obsidian konfigurieren

Obsidian lässt sich auf einfache Weise an die Bedürfnisse deines Teams anpassen. Mit einer umfangreichen API und einer großen Anwender-Community bietet Obsidian Zugang zu zahlreichen Erweiterungen, Themen und ergänzenden Tools.

Für sicherheitsrelevante Fragen zu diesen Themen lies bitte den Abschnitt [[Sicherheitsbetrachtungen für Teams]].

### Konfigurationsordner

Im [[Konfigurationsordner]] sind die Anwendungseinstellungen für einen Obsidian-[[Glossar#Vault|Vault]] gespeichert. Standardmäßig ist dies der Ordner `.obsidian`, du kannst diesen aber auch [[Konfigurationsordner#Konfigurationsordner ändern|ändern]].

Wir empfehlen, eine standardisierte Vorlage für den Konfigurationsordner zu erstellen, der auf die Geräte deines Teams verteilt werden kann.

### Plugins

[[Standarderweiterungen]] sind optionale Funktionen, die vom Obsidian-Team entwickelt wurden. Diese Funktionen sind mit Obsidian vorinstalliert und können separat aktiviert oder deaktiviert werden.

[[Externe Erweiterungen]] sind Plugins von Drittanbietern, die separat installiert und aktiviert oder deaktiviert werden können. Drittanbieter-Plugins verwenden die [Obsidian API](https://github.com/obsidianmd/obsidian-api). Sie liegen im Verzeichnis `.obsidian/plugins` innerhalb eines Vaults und können dort auch manuell installiert werden.

### Themen und CSS-Bausteine

[[Themen]] verändern das Design der Obsidian-Bedienoberfläche. Sie können, genauso wie Plugins, aus dem Community-Verzeichnis heruntergeladen und installiert werden. Themes werden im Verzeichnis `.obsidian/themes` innerhalb eines Vaults gespeichert.

[[CSS-Bausteine]] oder Snippets sind kleine `.css` Dateien, welche Teile der Obsidian-Bedienoberfläche optisch verändern. In manchen Fällen können sie auch funktionale Verbesserungen hinzufügen. CSS-Bausteine werden im Verzeichnis `.obsidian/snippets` innerhalb eines Vaults gespeichert.

## Häufig gestellte Fragen

Für Fragen zur Kontoverwaltung und -sicherheit lies bitte den Abschnitt [[Sicherheitsbetrachtungen für Teams#Kontosicherheit|Kontosicherheit]].

### Softwarebereitstellung

**Kann ich Lizenzen auf mehrere Installationen verteilen?**
Derzeit wird die automatisierte Bereitstellung von Lizenzen über ein Softwareverteilungs-Script nicht unterstützt. Falls du an dieser Funktion für dein Team interessiert bist, erstelle bitte einen [Feature Request](https://forum.obsidian.md/c/feature-requests/8). 

**Kann Obsidian bestimmte Funktionen oder Konfigurationen über eine Einstellung oder ein Anwendungs-Flag sperren?**
Derzeit kannst du dies erreichen, indem du den Bearbeitungszugriff auf den `.obsidian` Ordner oder auf bestimmte Dateien und Ordner in diesem Verzeichnis sperrst, wie oben beschrieben. Wenn du an einer erweiterten Zugriffskontrolle für dein Team interessiert bist, erstelle bitte einen [Feature Request](https://forum.obsidian.md/c/feature-requests/8). 
