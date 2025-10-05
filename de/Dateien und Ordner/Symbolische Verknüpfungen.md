---
permalink: symlinks
---

Du kannst [Symbolische Verkknüpfungen](https://de.wikipedia.org/wiki/Symbolische_Verkn%C3%BCpfung) (Symlinks) oder [Soft Links](https://learn.microsoft.com/de-de/windows/win32/fileio/hard-links-and-junctions#junctions) in deinem Vault verwenden, um Dateien außerhalb des Vaults und des [[Datenspeicherung#Globale Einstellungen|Systemverzeichnisses]] zu speichern.

> [!danger] Verwendung auf eigene Gefahr
> Wir raten jedoch dringend davon ab, symbolische Verknüpfungen zu verwenden. Mit der Verwendung von Symlinks oder Soft Links in deinem Vault riskierst du eine Beschädigung oder den Verlust deiner Daten sowie den Absturz der Anwendung. Sorge dafür, regelmäßig Sicherungskopien von deinem Vault und den Einstellungen zu erstellen.

Im Folgenden sind einige bekannte Probleme und Einschränkungen aufgezählt, die du möglicherweise in Betracht ziehen möchtest:

- Symlink-Schleifen sind unzulässig, um einen Absturz der Anwendung aufgrund einer Endlosschleife zu verhindern.
- Symlink-Zielverzeichnisse müssen vollständig vom Stammverzeichnis des Vaults und von anderen Symlink-Zielen getrennt sein. Getrennt bedeutet, dass ein Ordner keinen anderen Ordner enthält und umgekehrt. Obsidian ignoriert Symlinks zu einem übergeordneten Verzeichnis des Vaults sowie Symlinks von einem Ordner zu einem anderen innerhalb desselben Vaults. Das ist eine Sicherheitsmaßnahme, um doppelte Dateien in einem Vault zu vermeiden, die zu mehrdeutigen Links führen könnten.
- Symlinks vertragen sich möglicherweise nicht gut mit Obsidian Sync oder anderen Synchronisierungsverfahren. Wenn das Ziel eines Symlinks selbst ein Ordner ist, der über einen anderen Obsidian-Vault synchronisiert wird, kann dies zu Synchronisierungskonflikten und letztendlich möglicherweise zu Datenverlust führen. Einige Synchronisierungswerkzeuge, wie bspw. Git, synchronisieren nicht den Symlink, sondern den *Pfad*, auf den ein Symlink verweist. Das kann zu unerwünschten Ergebnissen führen, wenn du deinen Vault auf diese Weise zur Verwendung für andere freigibst.
- Obsidians Dateimanager kann keine Dateien über Gerätegrenzen hinweg verschieben. Wenn du also einen Symlink auf ein anderes Laufwerk verwendest, kannst du Dateien nicht mit dem integrierten [[Dateiexplorer|Dateiexplorer]] zwischen dem verknüpften Ordner und deinem Vault verschieben. (Dafür müsstest du den Dateimanager deines Betriebssystems verwenden, wobei Obsidian diesen Vorgang so interpretiert, als wäre eine Datei gelöscht und eine neue erstellt worden. Interne Links werden dabei *nicht* automatisch aktualisiert.)
- Datei-Symlinks (als Gegenstück zu Symlinks auf Verzeichnisse) funktionieren *möglicherweise*, werden aber derzeit nicht offiziell unterstützt. Änderungen, die außerhalb von Obsidian erfolgen, werden nicht überwacht. Wenn du also eine verknüpfte Datei direkt änderst, wird Obsidian die Änderung nicht erkennen und bspw. Suchindizes nicht aktualisieren.
- Symlinks auf den Ordner `.obsidian`, um dieselben Vault-Einstellungen in mehreren Vaults zu verwenden, **führen mit hoher Wahrscheinlichkeit zur Beschädigung deiner Einstellungen**, es sei denn, du weißt *genau*, was du tust. Falls du dich für diesen Weg entscheidest, solltest du zumindest vorher Sicherungskopien erstellen.

