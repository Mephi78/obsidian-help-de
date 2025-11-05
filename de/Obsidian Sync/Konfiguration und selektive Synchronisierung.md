---
aliases:
  - Sync-Einstellungen
  - Selektive Synchronisierung
  - Obsidian Sync/Auswahl zu synchronisierender Dateien und Einstellungen
description: Erfahre, wie du Obsidian Sync konfigurieren und festlegen kannst, welche Dateien synchronisiert werden.
mobile: true
permalink: sync/einstellungen
publish: true
---

Wenn du einen [[Tarife und Speicherkapazität#Neuen Remote-Vault erstellen|Remote-Vault erstellst]] und [[Obsidian Sync einrichten#Remote-Vault verbinden|verbindest]], kannst du den Remote-Vault über die Einstellungen der Obsidian-Erweiterung *Sync* verwalten.

## Sync-Einstellungen

**Remote-Vault**  
Hier wird dein aktuell verbundener Remote-Vault angezeigt. Über die Schaltfläche **Trennen** kannst du die Verbindung zum Remote-Vault aufheben. Über die Schaltfläche **Verwalten** kannst du alle Remote-Vaults anzeigen, auf die dein Nutzerkonto Zugriff hat (einschließlich zur [[Zusammenarbeit in einem freigegebenen Vault|Zusammenarbeit]] freigegebener Vaults).

> [!todo] Falls dein Vault sich in einem Ordner befindet, der möglicherweise von einem Drittanbieter-Dienst synchronisiert wird, erscheint hier eine rote Warnmeldung. Befolge die Anleitung unter [[Umstellung auf Obsidian Sync]], um dieses Problem zu beheben.

**Sync-Status**  
Zeigt den aktuellen Synchronisierungsstatus des Remote-Vaults an. Über die Schaltfläche **Anhalten** bzw. **Fortfahren** kannst du je nach Status die Synchronisierung anhalten oder fortsetzen.

**Name des Gerätes**  
Weise dem Gerät, das gerade synchronisiert wird, einen eindeutigen Namen zu. Das ist hilfreich bei der Analyse des [[Statussymbole und Benachrichtigungen#Sync-Log|Sync-Protokolls]]. Die Einstellung ist gerätespezifisch, ebenso wie die [[#Selektive Synchronisierung]].

**[[#Auflösen von Konflikten|Konflikte beim Zusammenführen]]**
Entscheide, wie Konflikte aufgelöst werden sollen, wenn eine Notiz auf mehreren Geräten gleichzeitig geändert wird. Die Einstellung ist gerätespezifisch, ebenso wie die [[#Selektive Synchronisierung]].

**Gelöschte Dateien**  
Enthält Schaltflächen zum **Zeigen** bzw. **Wiederherstellen** gelöschter Dateien. Für weitere Informationen, siehe [[Versionsverlauf]].

**Größe des Vaults**  
Zeigt einen Fortschrittsbalken über die Auslastung deines Sync-Speicherplatzes.

> [!tip] Aufgrund serverseitiger Verarbeitung kann die Aktualisierung der Speicherauslastung bis zu 30 Minuten dauern.

**Support kontaktieren**  
Enthält Anweisungen zur Kontaktaufnahme mit dem [[Hilfe und Kontakt#Obsidian Support kontaktieren|Obsidian Support]]. Du kannst über Schaltflächen die **Debug-Informationen kopieren** und eine **Email an den Support** senden.

### Auflösen von Konflikten

Obsidian Sync bietet eine grundlegende [[Obsidian Sync/Fehlerbehandlung#Auflösen von Konflikten|Konfliktbehandlung]] für die Verarbeitung von Änderungen, die von verschiedenen Geräten vorgenommen wurden. Ab Obsidian 1.9.7 kannst du für jedes Gerät wählen, wie Konflikte behandelt werden sollen:
- **Automatisch zusammenführen **(Standard): Obsidian Sync führt alle Änderungen von den verschiedenen Geräten in einer Notiz zusammen.  Dadurch bleiben alle Änderungen erhalten, jedoch können gelegentlich Formatierungsprobleme auftauchen, die manuell bereinigt werden müssen.
- **Konfliktdatei erstellen**: Wenn Obsidian Sync konfliktbehaftete Änderungen erkennt, wird eine separate Konfliktdatei erstellt, anstatt die Notizen automatisch zusammenzuführen. Du kannst dann beide Versionen prüfen und sie manuell zusammenführen, damit behältst du die volle Kontrolle über das Ergebnis.

> [!note] Die Option *Konfliktdatei* unterstützt derzeit keine In-App-Werkzeuge zum Zusammenführen. Du kannst Community-Erweiterungen mit "Diff"- oder "Merge"-Funktionen verwenden, um diesen Vorgang innerhalb Obsidian zu unterstützen.

## Selektive Synchronisierung

Du kannst über die Sync-Einstellungen auch bestimmen, welche Dateien synchronisiert werden sollen.  Dieser Abschnitt behandelt die Optionen **Selektive Synchronisierung** und **Vault-Konfiguration synchronisieren** sowie die damit verbundenen Einschränkungen.

Dateien, die mit deinem [[Lokale und Remote-Vaults|Remote-Vault]] synchronisiert werden, werden auf dein [[Häufig gestellte Fragen#Wie groß kann jeder Remote-Vault sein?|Speicher-Limit]] angerechnet. Standardmäßig aktiviert Obsidian Sync die **Selektive Synchronisierung** für folgende Dateitypen:

- Bilder
- Audiodateien
- Videos
- PDFs

Um weitere Dateitypen zu synchronisieren, aktiviere die Option **Alle anderen Dateien synchronisieren**.

Die Standardeinstellung für **Vault-Konfiguration synchronisieren** beinhaltet:

- Andere Dateitypen
- Allgemeine Einstellungen
- Darstellung
- Themen und Snippets
- Tastenkürzel
- Aktive Obsidian-Erweiterungen
- Obsidian-Erweiterungseinstellungen

Um Community-Erweiterungen zu synchronisieren, aktiviere manuell **Aktive externe Erweiterungen** und **Installierte externe Erweiterungen**.

### Zu synchronisierende Dateitypen ändern

1. Öffne die **Einstellungen → Sync**.
2. Aktiviere unter **Selektive Synchronisierung** die Dateitypen, die synchronisiert werden sollen.
3. Starte Obsidian neu, um die Einstellungen zu übernehmen. Auf dem ![[obsidian-icon-smartphone.svg#icon]] Mobilgerät oder Tablet ist möglicherweise ein erzwungener Neustart erforderlich.

Beachte, dass dein [[Tarife und Speicherkapazität|Sync-Tarif]] die maximale Dateigröße bestimmt, die du synchronisieren kannst. Der Standard-Tarif erlaubt die Synchronisierung von Dateien bis zu einer Größe von 5 MB, während der Plus-Tarif Dateigrößen bis zu 200 MB unterstützt.

> [!info] Wenn du eine Datei in **Ausgeschlossene Dateien** hinzufügst, die zuvor bereits synchronisiert wurde, wird diese nicht automatisch aus dem Remote-Vault entfernt. Konfiguriere deine Sync-Einstellungen am besten, *vor* der ersten Synchronisierung, um unnötigen Speicherverbrauch zu vermeiden.

### Ordner von der Synchronisierung ausschließen

Standardmäßig synchronisiert Obsidian Sync alle Dateien und Ordner in deinem Vault. So schließt du bestimmte Ordner von der Synchronisierung aus:

1. Öffne die **Einstellungen → Sync**.
2. Neben **Ausgeschlossene Ordner** wähle **Verwalten**.
3. Wähle den Ordner aus der Liste, den du ausschließen möchtest.
4. Bestätige mit **Fertig**.

Um einen Ordner aus der Liste der ausgeschlossenen Ordner zu entfernen, wähle die Schaltfläche ![[lucide-x.svg#icon]] neben dem entsprechenden Ordnernamen.

#### Immer von der Synchronisierung ausgeschlossen

##### Snapshots für die Datenwiederherstellung

Die Snapshots für die [[Datenwiederherstellung]] werden niemals mit Obsidian Sync synchronisiert, da Snapshots in den [[Datenspeicherung#Globale Einstellungen|Globalen Einstellungen]] gespeichert werden.

##### Versteckte Dateien und Ordner

Dateien und Ordner, deren Namen mit einem Punkt (`.`) beginnen, werden als versteckte Dateien behandelt und somit von der Synchronisierung ausgeschlossen. Die einzige Ausnahme stellt der [[Konfigurationsordner]] (`.obsidian`) dar, der bei Bedarf synchronisiert wird.

Mögliche Beispiele für versteckte Dateien und Ordner, die nicht synchronisiert werden:

- `.vscode`
- `.git`
- `.idea`
- `.gitignore`

##### Sync-Einstellungen

Die Sync-Einstellungen selbst werden nicht synchronisiert. Du musst Obsidian Sync auf jedem Gerät separat konfigurieren.

## Synchronisierte Vault-Einstellungen aktualisieren

Befolge diese Schritte, um die Sync-Einstellungen auf mehreren Geräten zu ändern:

> [!tip] Die Begriffe "primäres" und "weitere" Geräte dienen lediglich dem besseren Verständnis - für Obsidian Sync ist diese Unterscheidung nicht von Belang.

### Primäres Gerät

Dein primäres Gerät (in der Regel der Computer) dient als "Quelle der Wahrheit". Änderungen auf diesem Gerät werden auf alle weiteren Geräte synchronisiert.

1. Öffne die **Einstellungen → Sync**.
2. Aktiviere die gewünschten Einstellungen unter **Vault-Konfiguration synchronisieren**.
3. Starte Obsidian neu. Auf ![[obsidian-icon-smartphone.svg#icon]] Mobilgeräten bzw. Tablets ist möglicherweise ein erzwungener Neustart notwendig.
4. Warte bis die Synchronisierung der Einstellungen mit dem Remote-Vault abgeschlossen ist.

### Weitere Geräte

Weitere Geräte (bspw. dein Smartphone) erhalten Aktualisierungen vom primären Gerät.

1. Öffne die **Einstellungen → Sync**.
2. Aktiviere die gewünschten Einstellungen unter **Vault-Konfiguration synchronisieren**.
3. Warte bis die die Änderungen vom Remote-Vault heruntergeladen sind.
4. Starte die Obsidian App neu, um die synchronisierten Einstellungen zu übernehmen. Auf ![[obsidian-icon-smartphone.svg#icon]] Mobilgeräten bzw. Tablets ist möglicherweise ein erzwungener Neustart notwendig.

### Neuladen der Einstellungen

Bestimmte Einstellungen können über Obsidian Sync im laufenden Betrieb aktualisiert werden, während andere einen Neustart der Anwendung erfordern:

- **Im laufenden Betrieb (Hot-Reload-fähig)**: Die meisten Obsidian-Einstellungen, einschließlich Tastenkürzel und Eigenschaften, Einstellungen für die Darstellung und bereits aktivierte Obsidian-Erweiterungen.
- **Neustart erforderlich**: CSS-Änderungen (z.B. [[CSS-Bausteine]], [[Themen]]), Graph-Ansicht-Einstellungen und die Aktivierung bzw. Deaktivierung einiger Obsidian-Erweiterungen (bspw. *Tägliche Notiz*).

Community-Erweiterungen unterstützen üblicherweise kein Hot Reload und erfordern den Neustart der Anwendung, um geänderte Einstellungen zu übernehmen.

> [!todo] Plugin-Entwickler: Erfahre, wie du die [Hot-Reload-Funktionalität für Obsidian Sync integrieren](https://docs.obsidian.md/Reference/TypeScript+API/Plugin/onExternalSettingsChange) kannst.

## Einstellungsprofile

Obsidian Sync kann mehrere [[Konfigurationsordner]] mit demselben Remote-Vault synchronisieren, was die Erstellung separater Einstellungsprofile ermöglicht (bspw. eines für Mobilgeräte, ein anderes für den Laptop).

### Einstellungsprofil erstellen

So erstellst du ein neues Einstellungsprofil:

1. Öffne die **Einstellungen → Dateien & Links**.
2. Gib unter **Konfigurationsordner überschreiben** einen Namen für dein Profil ein, beginnend mit einem Punkt (`.`), z.B. `.obsidian-mobile`.
3. Starte Obsidian neu, um die Änderung zu übernehmen.

> [!note] Hinweis
> Wenn du das Einstellungsprofil änderst, musst du deine Sync-Einstellungen neu konfigurieren. Um zu vermeiden, dass installierte Plugins und Themen neu heruntergeladen werden müssen, kopiere deinen bestehenden Konfigurationsordner `.obsidian` und benenne ihn entsprechend dem neuen Profil um (z.B. `.obsidian-mobile`), *bevor* du diese Einstellung änderst.
