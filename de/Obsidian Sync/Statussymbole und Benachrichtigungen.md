---
aliases:
  - Sync-Statussymbol
  - Sync-Icon
  - Sync-Log
  - Aktivitätslog
description: Erfahre mehr über die Obsidian Sync-Statussymbole und das Aktivitätslog.
mobile: true
permalink: sync/benachrichtigungen
publish: true
---

Obsidian Sync informiert dich über den Sync-Status einerseits mittels [[#Sync-Statussymbol|Statussymbol]] sowie ausführlicher über das [[#Sync-Log|Sync-Log]]. Nähere Informationen zur Versionskontrolle in Obsidian Sync findest du im Abschnitt [[Versionsverlauf]].

## Sync-Statussymbol

Das Sync-Statussymbol findest du auf dem  ![[lucide-monitor-check.svg#icon]] Desktop in der [[Statusleiste]] und auf deinem ![[obsidian-icon-smartphone.svg#icon]] Mobilgerät in der [[Seitenleisten#Seitenleisten ein- oder ausblenden|rechten Seitenleiste]]. Das Icon zeigt verschiedene Synchronisierungszustände an:

- ![[obsidian-icon-sync-synced.svg#icon]] **Synchronisiert**: Obsidian Sync hat deine Dateien vollständig synchronisiert. Das Icon ist in der Regel grün.
- ![[obsidian-icon-sync-syncing.svg#icon]] **Sync läuft**: Obsidian ist dabei, deine Dateien zu aktualisieren. Dieses Icon ist in der Regel violett.
- ![[obsidian-icon-sync-paused.svg#icon]] **Angehalten**: Die Synchronisierung wurde angehalten, aber Obsidian ist noch immer mit dem Remote-Vault verbunden. Das Icon ist in der Regel violett.
- ![[obsidian-icon-sync-disconnected.svg#icon]] **Nicht verbunden**: Die Erweiterung Sync ist zwar aktiviert, aber der [[Lokale und Remote-Vaults|lokale Vault]] ist nicht mit einem Remote-Vault verbunden. Dieses Icon ist in der Regel rot.

Wenn du das Symbol anklickst oder -tippst, öffnet sich ein Kontextmenü mit folgenden Optionen:

- ![[obsidian-icon-sync-paused.svg#icon]] Anhalten (bzw. ![[lucide-circle-play.svg#icon]] Fortfahren, falls angehalten)
- ![[lucide-history.svg#icon]] [[Versionsverlauf]] (ausgegraut, wenn keine Notiz aktiv ist)
- ![[lucide-align-left.svg#icon]] [[#Sync-Log]] öffnen
- ![[lucide-trash-2.svg#icon]] [[Versionsverlauf#Gelöschte Datei wiederherstellen|Gelöschte Dateien]]
- ![[lucide-settings.svg#icon]] [[Konfiguration und selektive Synchronisierung|Sync-Einstellungen]]

## Sync-Log

Obsidian Sync protokolliert alle Synchronisierungsvorgänge zwischen deinen lokalen Dateien und dem Remote-Vault. Im Log findest du Uploads, Downloads, Löschvorgänge und alle Probleme, wie Konflikte beim Zusammenführen von Notizen oder Verbindungsprobleme.

**Auf Sync-Log zugreifen:**
- Klicke das Sync-Statussymbol in der Statusleiste
- Oder wähle **Einstellungen → Sync → Sync-Log**
- Oder öffne die  **Befehlspalette → Sync: Sync-Log öffnen**

Das Protokoll enthält Zeitstempel und Details zu jedem Synchronisierungsvorgang und unterstützt damit die Fehlerbehebung bei Synchronisierungsproblemen.

> [!warning] Das Sync-Log wird beim Schließen der Anwendung geleert. Falls es bei der Synchronisierung zu Fehlern kommt, kopiere das Protokoll, **bevor** du Obsidian beendest.

Das Protokoll unterscheidet Meldungen in folgende Kategorien:

- [[#Allgemeine Meldungen]]
- [[#Fehlermeldungen]]
- [[#Meldungen zu übersprungenen Dateien]]
- [[#Meldungen zum Nutzerkonto]]

Du kannst die Log-Meldungen filtern nach **Alle**, **Fehler**, **Übersrprungen** und **Konflikte beim Zusammenführen**. Darüber hinaus kannst du das Synchronisierungsprotokoll über das Suchfeld im Sync-Dialog durchsuchen.

> [!summary] Nachfolgend haben wir einige der wahrscheinlichsten Meldungen aufgeführt, die dir begegnen könnten. Die Auflistung ist nicht abschließend. Solltest du bei einem Fehler die Meldung im Sync-Log nicht verstehen, [[Hilfe und Kontakt#Obsidian Support kontaktieren|kontaktiere den Obsidian Support]].

### Allgemeine Meldungen

**Connecting to server**  

Serververbindung wird aufgebaut: Obsidian versucht, eine Verbindung zum [[Obsidian Sync/Sicherheit und Datenschutz#Wie finde ich meinen aktuellen Sync-Server und wo wird er gehostet?|Sync-Server]] herzustellen, auf dem dein Remote-Vault gespeichert ist.

**Connected to server. Detecting changes...**  

Server verbunden, suche nach Änderungen: Obsidian hat eine Verbindung hergestellt und vergleicht den lokalen mit dem Remote-Vault, um festzustellen, ob Änderungen erforderlich sind.

> [!info] Diese Meldung kann auch auf potenzielle Synchronisierungsprobleme hinweisen. Sollte diese Meldung sich häufen und du glaubst, es sind immer noch Elemente zu synchronisieren, [[Hilfe und Kontakt#Obsidian Support kontaktieren|kontaktiere den Obsidian Support]].

**Fully synced**   

Vollständig synchronisiert: Der lokale und der Remote-Vault wurden vollständig synchronisiert.

**Merging conflicted file**  

Zusammenführen konfliktbehafteter Datei: Bei der Synchronisierung wurde ein Konflikt festgestellt und die Datei wurde nicht überschrieben, sondern zusammengeführt. Für nähere Informationen, siehe [[Obsidian Sync/Fehlerbehandlung#Auflösen von Konflikten|Auflösen von Konflikten]]. Falls die Zusammenführung nicht erwünscht ist, kannst du die vorhergehende Version über den [[Versionsverlauf]] oder die [[Datenwiederherstellung]] wiederherstellen.

**Rejected server change**  

Serveränderungen abgelehnt: Die Änderungen im Remote-Vault sind älter als die lokale Version auf deinem Gerät, weshalb die lokale Version beibehalten und die Änderungen im Remote-Vault ignoriert werden.

### Fehlermeldungen

Diese Meldungen beschreiben bei der Synchronisierung einer Datei aufgetretene Fehler.

**Out of memory**  

Zu wenig Speicher: Dieses Problem ist typisch für ![[obsidian-icon-smartphone.svg#icon]] Mobilgeräte, wenn nicht genügend Speicherplatz oder Arbeitsspeicher zur Verfügung steht zum Herunterladen einer Datei. Dies passiert häufig bei sehr großen Dateien, wie bspw. Videos.

### Meldungen zu übersprungenen Dateien

Diese Meldungen beschreiben, was übersprungen wurde und möglicherweise warum. 

**Unable to download file with illegal name**  

Datei mit unzulässigem Namen kann nicht heruntergeladen werden: Der Dateiname enthält [Sonderzeichen oder Namenskonventionen](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names), die auf dem Ziel-Betriebssystem nicht zulässig sind. Der Einfachheit halber solltest du die Datei auf dem Quellsystem umbenennen, um alle Sonderzeichen außer `-` und `_` zu entfernen.

Beachte, dass dies auf Android-Geräten auch Dateien mit mehreren Punkten `.` im Dateinamen betreffen kann. 

### Meldungen zum Nutzerkonto

Diese Meldungen hängen mit Änderungen an deinem Abonnement oder Nutzerkonto zusammen. 

**Vault limit exceeded**  

Vault-Limit überschritten: Du hast die [[Häufig gestellte Fragen#Wie groß kann jeder Remote-Vault sein?|maximale Speichergröße]] für dein Nutzerkonto überschritten. Anhänge und der Versionsverlauf werden auf den Speicher angerechnet. Auch wenn dein Vault selbst kleiner erscheint, als das Limit, können ältere Versionen und Dateien dafür sorgen, dass es überschritten wird.

> [!TIP] So reduzierst du die Größe deines Vaults
> 
> 1. Öffne die **Einstellungen → Sync**.
> 2. Verwende die Optionen unter **Vault-Größe über Limit**, um sehr große Dateien zu entfernen.

**Vault not found**  

Vault nicht gefunden - diese Meldung erscheint in folgenden Fällen:

1. Der Remote-Vault wurde von einem anderen Gerät aus gelöscht.
2. Das Sync-Abo ist vor mehr als 30 Tage abgelaufen, weshalb der Remote-Vault gelöscht wurde.
3. Das Sync-Abo wurde gekündigt oder [[Refund policy|erstattet]], was zur Löschung des Remote-Vault geführt hat.
 
In diesen Fällen musst du die [[Obsidian Sync einrichten#Verbindung zu Remote-Vault trennen|Verbindung zum Remote-Vault trennen]] und einen [[Obsidian Sync einrichten#Neuen Remote-Vault erstellen|neuen Remote-Vault erstellen]], um deine lokalen Daten beizubehalten.

**Your subscription to Obsidian sync has expired.**  

Dein Obsidian Sync-Abo ist abgelaufen: Das Abo für dein Nutzerkonto ist nun vollständig abgelaufen, da wir die Zahlung nicht verarbeiten konnten. Um Obsidian Sync weiterhin zu verwenden, musst du Sync über dein [Nutzerkonto](https://obsidian.md/account/sync) neu abonnieren.

### Netzwerkmeldungen

**Unable to connect to server**

Verbindung zum Server nicht möglich: Obsidian Sync hat aus unbekannten Gründen die Verbindung zum Sync-Server unterbrochen. Sync wird regelmäßig versuchen, die Verbindung wiederherzustellen.

Unter iOS sieht diese Meldung wie folgt aus:
`Null is not an object (evaluating 'this.socket.send')`

Das hat dieselbe Bedeutung wie `Unable to connect to server` und ist keinesfalls ein Hinweis darauf, dass etwas anderes nicht in Ordnung ist. 
