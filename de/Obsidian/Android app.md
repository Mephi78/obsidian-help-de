---
permalink: android
---

Um deine Notizen mit Obsidian auf Android zu synchronisieren, siehe [[Synchronisiere Notizen zwischen Geräten]].

## Vault-Speicherort

Wenn du Obsidian auf Android startest, wirst du aufgefordert, einen Speicherort für deinen Vault festzulegen. Du kannst zwischen **Gerätespeicher** (empfohlen) und **Anwendungsspeicher** wählen.

### Gerätespeicher

Mit der Option **Gerätespeicher** werden deine Daten in einem freigegebenen Ordner auf deinem Gerät gespeichert. Auf diese Weise können auch andere Apps und Dienste auf Dateien in deinem Vault zugreifen, wie Drittanbieter-[[Synchronisiere Notizen zwischen Geräten|Synchronisierungsdienste]].

Diese Option ist empfohlen, da sie eine bessere Kompatibilität mit Synchronisierungsdiensten gewährleistet und sicherstellt, dass deine Daten auch nach Deinstallation von Obsidian erhalten bleiben. Es werden jedoch zusätzliche Berechtigungen für den Zugriff auf die Dateien deines Geräts benötigt.

Aufgrund von Einschränkungen bei Android fordert Obsidian *Zugriff auf Alle Dateien*, um zuverlässig zu funktionieren. [Google empfiehlt](https://developer.android.com/training/data-storage/manage-all-files) diese Einstellung für "Dokumentenmanagement-Apps" wie Obsidian.

Die App verwendet diese Berechtigung nur, um dir Zugriff auf deine Daten auf deinem Gerät zu ermöglichen. Wir haben zu keinem Zeitpunkt Zugriff auf deine Daten. Erfahre mehr darüber, wie wir deine Daten schützen, auf unserer Webseite im Abschnitt [Sicherheit](https://obsidian.md/security).

### Anwendungsspeicher

Mit der Option **Anwendungsspeicher** werden deine Daten im privaten App-Speicher von Obsidian gespeichert. Deine Daten bleiben dadurch von anderen Apps isoliert, was für zusätzlichen Datenschutz sorgt.

Diese Option eignet sich, wenn du keine externen Synchronisierungsdienste verwendest und ein strengeres Sandboxing auf App-Ebene für deine Notizen bevorzugst.

Mit dieser Option kannst du [[Einführung in Obsidian Sync|Obsidian Sync]] und Drittanbieter-Plugins verwenden, die als [[Externe Erweiterungen|Externe Erweiterung]] verfügbar sind. Externe Dienste hingegen, wie Syncthing, sind nicht verwendbar, weil diese auf freigegebene Ordner bauen.

> [!warning] Mit der Deinstallation von Obsidian werden deine lokalen Notizen ebenfalls gelöscht, wenn du den **Anwendungsspeicher** verwendest.
