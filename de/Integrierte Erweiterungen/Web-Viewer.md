---
permalink: plugins/web-viewer
---

Mit der [[Übersicht|Standarderweiterung]] *Web-Viewer* kannst externe Links direkt innerhalb ![[lucide-monitor-check.svg#icon]] Obsidian-Desktop öffnen. Die Erweiterung erleichtert die Arbeit an Webrecherche-Projekten, da du verlinkte Inhalte lesen kannst, ohne die Anwendung zu wechseln.

Externe Inhalte werden in einer eigenen [[Registerkarten|Registerkarte]] geöffnet, die du wie gewohnt anordnen, aufteilen oder in einem [[Pop-out Fenster]] öffnen kannst. In [[Canvas]]-Dateien als Karten eingebettete Webseiten können als Web-Viewer-Tabs geöffnet werden.

*Web-Viewer* ist kein Ersatz für deinen primären Webbrowser. Die Erweiterung bietet eine Möglichkeit für schnelle Webrecherchen innerhalb Obsidian, jedoch nicht die volle Funktionalität, Sicherheitskontrolle oder Erweiterbarkeit wie ein dedizierter Webbrowser.

## Reader Ansicht

Klicke das Brillensymbol oben rechts im Web-Viewer-Tab, um eine reine Textversion der Webseite anzuzeigen. Diese Funktion bereinigt den Webinhalt mit Hilfe der für Firefox entwickelten Readability-Bibliothek von Mozilla.

## Webseiten speichern

Um eine Webseite in deinem Vault zu speichern, öffne das Drei-Punkte-Menü ( ![[lucide-ellipsis-vertical.svg#icon]] ) und wähle **In Vault speichern...**.

Du kannst in den Erweiterungseinstellungen unter **Speicherort für Webseiten** festlegen, in welchem Ordner die Webseiten im Markdown-Format gespeichert werden sollen.

## Werbeblocker

*Web-Viewer* blockiert Werbung standardmäßig. Du kannst die Werbeblocker-Regeln anpassen, indem du Listen, wie bspw. [Easylist](https://easylist.to/) in den Erweiterungseinstellungen unter **Werbeblocker-Regeln** hinzufügst.

## Sicherheit

Wenn du Drittanbieter-Plugins für Obsidian verwendest, empfehlen wir, für sensible Aufgaben und passwortgeschützte Webseiten die Verwendung deines primären Browsers.

*Web-Viewer* basiert auf derselben [Chromium](https://developer.chrome.com/docs/apps/reference/webviewTag)-Funktion, mit der du auch Webseiten in [[Canvas]] einbetten kannst. *Web-Viewer* wurde einem [unabhängigen Audit](https://obsidian.md/blog/cure53-second-client-audit/) unterzogen, um sicherzustellen, dass die Erweiterung sicher implementiert wurde.

Obsidian Plugins laufen [[Plugin-Sicherheit#Plugin-Fähigkeiten|nicht isoliert (Sandbox)]] und haben daher umfassende Kontrolle über die Anwendung. Dieses Design ermöglicht leistungsstarke Funktionen, bringt jedoch gleichzeitig Sicherheitsrisiken mit sich. Während Obsidian ausgeführt wird, haben Drittanbieter-Erweiterungen vollen Zugriff auf Cookies im *Web-Viewer*.
