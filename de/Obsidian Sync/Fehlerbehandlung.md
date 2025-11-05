---
aliases:
cssclasses:
  - soft-embed
description: Erfahre mehr über häufig auftretende Probleme bei der Verwendung von Obsidian Sync.
mobile: true
permalink: sync/fehlerbehandlung
publish: true
---

Hier beschreiben wir bei der Verwendung von [[Einführung in Obsidian Sync|Obsidian Sync]] gelegentlich auftretende Probleme und Lösungen dafür. Es wird empfohlen, zunächst die Abschnitte [[Statussymbole und Benachrichtigungen]] sowie [[Häufig gestellte Fragen]] zu lesen.

## Allgemein

### Auflösen von Konflikten

Ein Konflikt tritt auf, wenn Änderungen an derselben Notiz auf zwei oder mehr Geräten vorgenommen werden, bevor diese synchronisiert wurden. Wenn du bspw. eine Notiz auf dem Computer bearbeitest und vor dem Hochladen der Änderung dieselbe Notiz auf dem Mobilgerät änderst.

Konflikte treten eher im Offline-Betrieb auf, da mehr Änderungen und längere Zeiträume zwischen den Synchronisierungen die Wahrscheinlichkeit von Konflikten erhöht.

Wenn Obsidian Sync Konflikte zwischen der lokalen und der Remote-Version einer Notiz erkennt, führt es die Versionen mit Hilfe des [Diff-Match-Patch](https://github.com/google/diff-match-patch)-Algorithmus von Google zusammen.

Konflikte in der Obsidian-Konfiguration, z.B. in Plugin-Einstellungen, werden anders behandelt. Obsidian Sync führt JSON-Dateien zusammen, indem es beim Hochladen die Schlüsselwerte der Remote-Datei mit denen der lokalen Datei überschreibt.

> [!help] Filtere das [[Statussymbole und Benachrichtigungen#Sync-Log|Sync-Log]] nach "Merge Conflicts", um zu prüfen, wann Konflikte aufgetreten sind.

### Sync hat eine soeben auf zwei Geräten erstellte Notiz gelöscht

In der Regel versucht Obsidian Sync [[#Auflösen von Konflikten|Konflikte aufzulösen]], indem es widersprüchliche Notizen von den verschiedenen Geräten zusammenführt. Dennoch können Probleme auftreten, wenn in deinem Vault beim Start der Anwendung Notizen *automatisch generiert* bzw. *geändert* werden, wie bspw. durch die Erweiterungen [[Tägliche Notiz]] oder [Templater](https://github.com/SilentVoid13/Templater).

Wenn eine Notiz lokal auf einem Gerät erstellt wird und Obsidian Sync innerhalb weniger Minuten eine Remote-Version derselben Notiz herunterlädt, wird Sync nur die Remote-Version beibehalten, ohne beide Notizen zusammenzuführen. In diesem Fall kannst du die lokale Version über die [[Datenwiederherstellung]] zurückholen.

### Änderungen an Plugins und Einstellungen werden nicht synchronisiert

Obsidian [[Häufig gestellte Fragen#Werden synchronisierte Einstellungen im laufenden Betrieb aktualisiert?|aktualisiert nicht alle Einstellungen im laufenden Betrieb]]. Nach der Aktualisierung von Einstellungen oder Plugins musst du Obsidian auf weiteren Geräten neu starten, damit die Änderungen übernommen werden. Auf ![[obsidian-icon-smartphone.svg#icon]] Mobilgeräten kann ein erzwungenes Beenden der App notwendig sein.

> [!example] Änderung des Themas
> - Auf deinem primären Gerät (für gewöhnlich ein Computer) änderst du dein Thema zurück zum Standard-Design.
> - Das Sync-Log bestätigt, dass die Aktualisierung an den Remote-Vault gesendet wurden, aber dein Mobilgerät zeigt noch immer das benutzerdefinierte Design.
> - Überprüfe im Sync-Log auf dem Mobilgerät, ob die Datei `appearance.json` aktualisiert wurde.
> - Starte Obsidian neu auf deinem Mobilgerät.
> - Nach dem Neustart sollte Obsidian auf dem Mobilgerät dasselbe Thema verwenden wie auf deinem Computer.

### Meine Dateien verschwinden immer wieder aus Sync nach der Datenwiederherstellung

Dieses Problem tritt am häufigsten unter Windows auf, da der Windows Defender möglicherweise Dateien mit Code-Blöcken unter Quarantäne stellt, wodurch betroffene Notizen verschwinden.

Eine weitere häufig Ursache ist die doppelte Synchronisierung, wobei Obsidian Sync parallel zu einem anderen Synchronisierungsdienst verwendet wird.

![[Umstellung auf Obsidian Sync#Verschiebe deinen Vault aus deinem Drittanbieter-Sync- oder Cloud-Speicher]]

---

Schließlich kann dies auch passieren, wenn eine Datei auf einem Gerät wiederhergestellt, aber auf einem anderen Gerät gelöscht wird aufgrund [[Statussymbole und Benachrichtigungen#Meldungen zu übersprungenen Dateien|unzulässiger Zeichen]] im Dateinamen.

## Android

**Mein Gerät löscht Anhänge, die ich über Obsidian Sync erhalten habe**

Wahrscheinlich werden deine Anhänge durch Google oder Android Photos verwaltet. Um zu verhindern, dass dein System Dateien ändert, die du über Obsidian Sync erhältst, erstelle auf deinem Android-Gerät eine `.nomedia` [Datei](https://support.google.com/android/thread/60342076/what-are-these-nomedia-files) in jedem Ordner deines Vaults, der Bilder enthält.

> [!tip] Die Community-Erweiterung [Android Nomedia](https://obsidian.md/plugins?id=android-nomedia) erleichtert diesen Prozess. Installiere das Plugin nur auf deinem Android-Gerät, `.nomedia` Dateien werden von Obsidian Sync nicht synchronisiert.
