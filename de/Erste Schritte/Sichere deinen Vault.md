---
aliases:
  - Obsidian Sync/Obsidian Sync und Drittanbieter-Dienste
  - Obsidian Sync/Sichere deinen Vault
  - Backup
permalink: backup
---

Wenn du noch keine Sicherungskopie deines Rechners erstellt hast, dann ist jetzt der beste Zeitpunkt! Obsidians Erweiterung zur [[File recovery|Datenwiederherstellung]] ist nützlich, aber hat ihre Grenzen. Die Erweiterung kann nur eine bestimmte Datenmenge wiederherstellen und speichert die Wiederherstellungsdaten pro Gerät. Für einen zuverlässigeren Schutz deiner Daten empfiehlt es sich, ein geeignetes Backup-System einzusetzen.

**Warum solltest du deine Daten sichern?**

Standardmäßig speichert Obsidian deine Notizen **lokal** auf deinem Gerät, nicht in einer Cloud. Das bedeutet, [die Daten gehören dir allein](https://obsidian.md/about) und du behältst die volle Kontrolle darüber. Daten auf lokalen Speichern können jedoch auch beschädigt werden oder verloren gehen. Es ist keine Frage ob dies passiert, sondern wann. Sicherungskopien schützen deine Daten vor unerwarteten Ereignissen und sichern dir die bleibende Kontrolle über deine Notizen.

## Synchronisieren ist keine Datensicherung

Dienste wie [[Obsidian Sync/Einführung|Obsidian Sync]], iCloud, OneDrive oder Dropbox helfen dir, deine Notizen zwischen verschiedenen Geräten zu synchronisieren. Diese Dienste bieten zwar Funktionen wie die [[Version history|Wiederherstellung von Notizen]], sind aber **nicht für Datensicherungen ausgelegt**. Die Synchronisierung hält deine Notizen zwar auf dem neuesten Stand, schützt sie aber nicht vor Datenverlust.

- **Synchronisierung:** Die Synchronisierung sorgt dafür, dass deine Dateien auf allen Geräten identisch sind. Wenn du eine Datei auf einem Gerät änderst, wird sie auf allen synchronisierten Geräten aktualisiert. Synchronisierungsdienste kennen kein "primäres" Gerät.
- **Sicherung:** Bei einer Sicherung wird eine Kopie deiner Daten an einem anderen Ort gespeichert, damit du diese im Falle von Beschädigungen oder Datenverlust wiederherstellen kannst. Sicherungen sind nicht für Aktualisierungen in Echtzeit oder die Zusammenarbeit gedacht.

Um deinen Vault zuverlässig zu sichern, verwende am besten eine geeignete Sicherungssoftware, die eine Einweg-Kopie deiner Daten an einem sicheren Speicherort erstellt, ohne die Daten auf deinem Gerät zu ändern.

Wenn du mehrere Geräte und die Synchronisation verwendest, wähle **ein Gerät** aus, von welchem du regelmäßig Sicherungskopien erstellst. In der Regel wird dies dein Hauptgerät sein, mit dem du am meisten arbeitest.

> [!Example] Du verwendest Obsidian Sync auf deinem Laptop, Tablet, Handy und dem Arbeitsrechner. Die meiste Zeit arbeitest du auf dem Arbeitsrechner in deinem Vault, manchmal auf dem Laptop, seltener auf dem Tablet oder Handy. In diesem Fall ist der Arbeitsrechner dein Hauptgerät, das du für die Sicherungskopien verwenden solltest.

## Externe Erweiterungen

Das Obsidian-Team kann zwar offiziell keine bestimmte Erweiterung empfehlen, zwei Plugins zur Datensicherung sind jedoch bei unseren Anwendern besonders beliebt:

- **[Obsidian Git](https://obsidian.md/plugins?id=obsidian-git):** Mit dieser Erweiterung kannst du deinen Vault sichern, indem du seinen Inhalt in einem [Git-Repository](https://git-scm.com/book/de/v2/Git-Grundlagen-Ein-Git-Repository-anlegen) speicherst. Eine effektive Methode, die deine Notizen mit einer Versionskontrolle versieht und sie auf einem Remote-Server sichert. Beachte aber, dass deine Daten auf diese Weise ggf. auf einer [[#Cloud-basierte Sicherungsdienste|externen Hosting-Plattform]] gespeichert werden.
- **[Local Backup](https://obsidian.md/plugins?id=local-backup):** Mit dieser Erweiterung kannst du lokale Kopien deines Vaults in einem Verzeichnis deiner Wahl erstellen, mit Optionen für die Archivierung. Du kannst auch ein Sychronisierungsverzeichnis wählen, wie bspw. einen Dropbox-Ordner, um lokale und Cloud-Sicherungen zu kombinieren. Diese Methode lässt sich gut **kombinieren** mit den unten beschriebenen Optionen.

## Cloud-basierte Sicherungsdienste

> [!info] Es wird nicht empfohlen, den Speicherort deines Vaults im von dir verwendeten Backup-Dienst zu belassen.

Die Datensicherung in der Cloud ist eine Alternative zur physischen Datenspeicherung, anstelle einer externen Festplatte oder eines USB-Sticks. Externe Festplatten oder USB-Sticks können verloren gehen oder beschädigt werden. Der größte Vorteil einer Cloud-Sicherung besteht darin, dass die Daten jederzeit und überall verfügbar sind. Der Nachteil jedoch ist, dass sich die meisten cloudbasierten Sicherungsdienste im Besitz von privaten Unternehmen befinden.

In puncto Sicherheit solltest du bei Cloud-Sicherungen immer genau auf die Zugriffs- und Datensicherheit achten. [World Backup Day](https://www.worldbackupday.com/de) führt eine Liste von Cloud-Backup-Anbietern.

## Externe Speichermedien

**Festplatten und SSD-Laufwerke**
Externe Festplatten sind auch in einer zunehmend cloud-basierten Welt noch wertvoll und werden überwiegend für die Speicherung von Daten und Sicherungskopien verwendet. Der größte Nachteil von externen Festplatten ist, dass sie kaputt- oder verloren gehen können. Von Vorteil ist, dass der Speicherplatz nur einmal gekauft werden muss. Externe Festplatten können im Zusammenhang mit [[#Computer-Backups]] verwendet werden.

**USB-Sticks**
Flash-Laufwerke (auch USB-Stick oder Memory-Stick) bieten eine einfache und schnelle Methode für Datensicherungen.

1. Stecke den USB-Stick in den PC oder Laptop.
2. Stelle sicher, dass das Gerät erkannt wurde und im Dateisystem eingebunden ist. Formatiere den USB-Stick ggf., damit er mit deinem Dateisystem kompatibel ist.
3. Kopiere deinen Vault-Ordner vom aktuellen Speicherort auf das USB-Laufwerk.
4. Trenne das USB-Laufwerk sicher und ziehe dann den USB-Stick aus dem Gerät.

**NAS-Sicherung**
Für versierte Anwender sei die Datensicherung auf einem NAS-Server (Network Attached Storage) als gute und sichere Methode empfohlen, da dieser über mehrere Festplatten und zusätzliche Wiederherstellungsmechanismen verfügt.

> [!tip] Enthält dein externes Speichermedium sensible Informationen, bewahre es sicher auf, z.B. in einem abgesicherten Raum.

## Computer-Backups

Betriebssysteme bieten auch von Hause aus die Möglichkeit, Datensicherungen online oder auf externen Speichermedien zu erstellen.

- **[Windows](https://www.microsoft.com/en-us/windows/learning-center/back-up-files)**: Sicherungskopien mit OneDrive oder auf einem externen Laufwerk erstellen.
- **[Mac](https://support.apple.com/de-de/104984)**: Sicherungskopien auf externen Speichermedien mit Time Machine erstellen.
- **[Linux](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/)**: Daten mit `rsync` in ein Laufwerk oder Verzeichnis deiner Wahl spiegeln.

## Nächste Schritte

Diese Hilfeseite bietet einen kurzen Überblick über Backup-Möglichkeiten, erhebt aber keinen Anspruch auf Vollständigkeit. Finde detaillierte Informationen auf [Worldbackupday.com](https://www.worldbackupday.com/de) oder frage andere Obsidian-Anwender aus [unserer Community](https://obsidian.md/community) nach ihren Backup-Strategien.
