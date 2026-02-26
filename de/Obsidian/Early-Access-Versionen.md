---
aliases:
  - Konzepte/Insider Builds
  - Insider Builds
permalink: early-access
---

Erhalte frühzeitigen Zugriff auf kommende Releases, indem du die *Early-Access-Versionen* aktivierst. Early Access ist nur für Anwender mit einer [[Catalyst Lizenz]] verfügbar.

> [!warning] Achtung
> Early-Access-Versionen sind Beta-Versionen. Sie beinhalten neue Funktionen, sind jedoch möglicherweise weniger stabil. Wenn du eine zuverlässige Arbeitsweise bevorzugst, solltest du Early-Access-Versionen nicht aktivieren.
> 
> Bedenke, dass Entwickler von Community-Plugins und Themen Early-Access-Versionen zur selben Zeit erhalten, wie alle anderen. Hab Geduld mit den Entwicklern, wenn diese Änderungen vornehmen müssen, um neue Funktionen zu unterstützen.

## Early-Access für Desktop aktivieren

Du kannst Early-Access-Versionen wie folgt aktivieren:

1. Öffne die ![[lucide-settings.svg#icon]] **Einstellungen**.
2. Wähle **Allgemein**.
3. Melde dich unter **Nutzerkonto** an.
4. Gib deine **E-Mail** und dein **Passwort** ein.
5. Kehre nach der Anmeldung zu den **Einstellungen** zurück.
6. Wähle **Allgemein**.
7. Unter **Anwendung** aktiviere **Insider-Builds erhalten**.
8. Wähle **Nach Aktualisierungen suchen** und dann **Neu starten**.

## Early-Access für Mobile aktivieren

Eine Anleitung zur Aktivierung von Early-Access-Versionen auf deinem Mobilgerät findest du wie folgt:

1. Lade [Discord](<https://discord.com>) herunter und installiere es.
2. Tritt dem [Obsidian Discord-Server](https://discord.gg/obsidianmd) bei.
3. [[Catalyst Lizenz#Discord-Abzeichen erhalten|Hol dir dein Discord-Abzeichen]], um Zugang zu unseren Insider-Kanälen zu erhalten.
4. Im Kanal `#insider-welcome` findest du Anweisungen, wie du Early-Access-Versionen für deinen Mobilgerät-Typ herunterladen kannst.

## Fehlerberichte und andere Rückmeldungen

Solltest du in einer Early-Access-Version ein Problem entdecken, melde es bitte dem Obsidian-Team. Schau jedoch vorher, ob das Problem bereits im [Forum](https://forum.obsidian.md/) oder auf Discord gemeldet wurde.

Nutze zur Meldung von Problemen einen der folgenden Kanäle:

- Melde Fehler auf Discord im dafür vorgesehenen Kanal `#insider-release`.
- Erstelle im Forum ein neues Thema unter [Bug reports](https://forum.obsidian.md/c/bug-reports/7).

Wenn du ein Problem meldest, gib bitte die Build-Version und das Betriebssystem aus, auf dem du Obsidian ausführst. Die Build-Version findest du unter **Einstellungen → Allgemein → Version**.

## Zurück zur öffentlichen Version wechseln: Desktop

So wechselst du auf dem Desktop zur Verwendung der öffentlichen Versionen zurück (kein Early-Access):

1. Deaktiviere Early-Access-Versionen.
	1. Öffne die **Einstellungen**.
	2. Wähle **Allgemein**.
	3. Unter **Anwendung** deaktiviere **Insider-Builds erhalten**.
2. Schließe Obsidian.
3. Lösche die Datei `obsidian-VERSION.asar`, wobei `VERSION` für die Obsidian-Version steht.
   - Windows: `%APPDATA%\obsidian\obsidian-VERSION.asar`
   - Mac: `~/Library/Application Support/obsidian/obsidian-VERSION.asar`
   - Linux: `~/.config/obsidian/obsidian-VERSION.asar`
1. Starte Obsidian neu.

## Zurück zur öffentlichen Version wechseln: Mobile

So wechselst du auf dem Mobilgerät zur Verwendung der öffentlichen Versionen zurück (kein Early-Access):

1. Erstelle eine Sicherungskopie deines Vaults.
2. Deinstalliere Obsidian.
3. Installiere Obsidian entweder aus dem Play Store oder dem Apple App Store neu.
4. Stelle deinen Vault aus der Sicherungskopie wieder her.
5. Öffne Obsidian.
