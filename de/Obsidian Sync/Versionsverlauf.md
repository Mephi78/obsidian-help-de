---
aliases:
  - Sync-Historie
  - Sync-Seitenleiste
cssclasses:
  - soft-embed
description: Obsidian Sync protokolliert alle Synchronisierungsvorgänge, prüft regelmäßig auf Aktualisierungen und erstellt neue Versionen deiner Notizen.
mobile: true
publish: true
---

[[Einführung in Obsidian Sync|Obsidian Sync]] prüft regelmäßig, ob Aktualisierungen für deine [[Konfiguration und selektive Synchronisierung|synchronisierten Dateien]] anliegen und protokolliert alle Änderungen. Diese werden als neue Einträge im [[#Versionsverlauf]] verzeichnet. 

So kannst du auf diese Informationen zugreifen:

- [[#Synchronisierungsverlauf]]
- [[#Versionsverlauf]]

Obwohl keine Funktion von Obsidian Sync, ist auf jedem Gerät auch ein lokaler Versionsverlauf verfügbar, wenn die Obsidian-Erweiterung [[Datenwiederherstellung]] aktiviert ist.

## Synchronisierungsverlauf

Mit der Funktion Synchronisierungsverlauf (oder Sync-Seitenleiste), die in Obsidian 1.7 eingeführt wurde, kannst du schnell alle erstellten oder geänderten Notizen bzw. Anhänge anzeigen, die kürzlich synchronisiert wurden. Du kannst dir diese Funktion auch als *Bearbeitungsverlauf* vorstellen.

In der Seitenleiste kannst du ein Element auswählen, um die Datei im aktiven Fenster zu öffnen. Mit Rechtsklick auf ein Element öffnest du das Kontextmenü, das verschiedene Aktionen bereitstellt, bspw. um eine Datei zu verschieben oder ihren [[#Notizen und Anhänge|Versionsverlauf]] anzuzeigen.

> [!compatibility] Nur für Desktop-Version
> Wenn du in der Seitenleiste mit dem Mauszeiger über eine synchronisierte Datei fährst, kannst du sehen, wer sie zuletzt bearbeitet hat. Diese Funktion ist besonders nützlich für die [[Zusammenarbeit in einem freigegebenen Vault|Zusammenarbeit]] in einem freigegebenen Vault.

> [!tip] Tipp
> Einstellungen und gelöschte Dateien werden in der Sync-Seitenleiste nicht angezeigt. Diese findest du stattdessen im [[#Notizen und Anhänge|Versionsverlauf]].

### Synchronisierungsverlauf anzeigen

Wenn du das [[Einführung in Obsidian Sync|Sync]]-Plugin aktivierst, ist der Versionsverlauf automatisch aktiviert, erscheint aber nicht standardmäßig in der Seitenleiste. Du musst die Sync-Seitenleiste manuell hinzufügen über die Befehlspalette oder ein Tastenkürzel.

#### Aktivieren über Befehlspalette

> [!info] Die Obsidian-Erweiterung [[Befehlspalette]] muss aktiviert sein.

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]

1. Öffne die **Befehlspalette**. ( ![[lucide-terminal.svg#icon]] )
2. Gib "Sync" ein.
3. Wähle die Option **Sync: Synchronisierungsverlauf anzeigen**.

Der Synchronisierungsverlauf erscheint dann in der [[Seitenleisten|rechten Seitenleiste]].

**Mobile** ![[obsidian-icon-smartphone.svg#icon]]

1. Öffne die [[Werkzeugleiste]] ( ![[lucide-menu.svg#icon]] ).
2. Öffne die **Befehlspalette**. ( ![[lucide-terminal.svg#icon]] )
3. Gib "Sync" ein.
4. Wähle die Option **Sync: Synchronisierungsverlauf anzeigen**.

Der Synchronisierungsverlauf erscheint dann als Auswahloption in der [[Seitenleisten|rechten Seitenleiste]].

#### Aktivieren über Tastenkürzel

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Tastenkürzel**.
3. Gib im Suchfeld "Sync" ein.
4. Weise der Aktion **Sync: Synchronisierungsverlauf anzeigen** ein Tastenkürzel zu.

## Versionsverlauf

Zusätzlich zum [[#Synchronisierungsverlauf]] führt Obsidian auch einen Versionsverlauf für die Wiederherstellung von Notizen und Anhängen. Wenn du aus Versehen eine Notiz löschst oder zu einer früheren Version zurückkehren möchtest, kannst du diese aus dem Versionsverlauf wiederherstellen.

Die Aufbewahrungsfrist für den Versionsverlauf hängt von deinem [[Tarife und Speicherkapazität|Obsidian Sync-Tarif]] ab. Im Standard-Tarif werden Notizen einen Monat lang aufbewahrt, im Plus-Tarif sogar 12 Monate. Nach Ablauf dieser Frist werden ältere Versionen deiner Notizen gelöscht. 

Für [[Anhänge]] werden ältere Versionen nur <u>zwei Wochen</u> aufbewahrt.

![[Zusammenarbeit in einem freigegebenen Vault#^version-history-image]]

### Notizen und Anhänge

Der Vorgang zum Wiederherstellen von Anhängen ist derselbe wie für Notizen. 

#### Versionsverlauf einer Datei anzeigen

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]
1. Wähle im **Dateiexplorer** die Notiz, die du wiederherstellen möchtest.
2. Wähle **Versionsverlauf öffnen**.
3. Wähle auf der linken Seite die Version der Notiz aus, die du ansehen möchtest.
4. Der Inhalt der Notiz wird rechts angezeigt. 

**Mobile** ![[obsidian-icon-smartphone.svg#icon]]
1. Wähle im **Dateiexplorer** die Notiz, die du wiederherstellen möchtest.
2. Drücke lange auf die Notiz, um das Kontextmenü zu öffnen.
3. Wähle **Versionsverlauf öffnen**.
4. Wähle im Popup-Menü die Version der Notiz aus, die du ansehen möchtest.
5. Nach der Auswahl kannst du den Inhalt der Notiz überprüfen.

#### Versionsverlauf einer gelöschten oder umbenannten Datei anzeigen

1. Öffne die **Einstellungen** → **Sync**.
2. Neben **Gelöschte Dateien** wähle **Anzeigen**.
3. Wähle die Notiz, für die du den Versionsverlauf sehen möchtest.
4. Wähle im Popup-Menü die Version der Notiz aus, die du ansehen möchtest.

#### Frühere Version einer Datei wiederherstellen

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]
1. Wähle im **Dateiexplorer** die Notiz, die du wiederherstellen möchtest.
2. Wähle **Versionsverlauf öffnen**.
3. Wähle auf der linken Seite die Version der Notiz aus, die du ansehen möchtest. Der Inhalt wird rechts angezeigt. 
4. Wähle **Wiederherstellen**.
5. Der Inhalt wird mit der wiederhergestellten Version ersetzt.

**Mobile** ![[obsidian-icon-smartphone.svg#icon]]
1. Wähle im **Dateiexplorer** die Notiz, die du wiederherstellen möchtest.
2. Drücke lange auf die Notiz, um das Kontextmenü zu öffnen.
3. Wähle **Versionsverlauf öffnen**.
4. Wähle im Popup-Menü die Version der Notiz aus, die du wiederherstellen möchtest.
5. Nach der Auswahl kannst du den Inhalt der Notiz überprüfen.
6. Wähle **Wiederherstellen**.
7. Der Inhalt wird mit der wiederhergestellten Version ersetzt.

#### Gelöschte Datei wiederherstellen

1. Öffne die **Einstellungen** → **Sync**.
2. Neben **Gelöschte Dateien** wähle **Anzeigen**.
3. Wähle die Notiz, die du wiederherstellen möchtest.
4. Wähle links die Version der Notiz aus, die du wiederherstellen möchtest.
5. Wähle **Wiederherstellen** auf der rechten Seite.
6. Die Notiz wird an ihrem ursprünglichen Speicherort im Dateisystem wiederhergestellt.

> [!tip] Du kannst mehrere Notizen für **Mehrere wiederherstellen** auswählen, indem du die Checkboxen aktivierst oder die Notizen mit `Umschalt + Klick` auswählst. Diese Dateien können nicht in dem Menü geprüft werden. 

### Einstellungsverlauf

Obsidian Sync verfolgt auch die Änderungen in den Vault-Einstellungen. 

#### Einstellungsverlauf anzeigen

1. Öffne die **Einstellungen** → **Sync**.
2. Scrolle zum Abschnitt **Vault-Konfiguration synchronisieren**. 
3. Wähle **Anzeigen** neben **Einstellungsverlauf**.
4. Wähle im Dialog **Einstellungsdatei** die Einstellungsdatei, die du anzeigen möchtest.  

#### Frühere Version einer Einstellung wiederherstellen

1. Öffne die **Einstellungen** → **Sync**.
2. Scrolle zum Abschnitt **Vault-Konfiguration synchronisieren**. 
3. Wähle **Anzeigen** neben **Einstellungsverlauf**.
4. Wähle im Dialog **Einstellungsdatei** die Einstellungsdatei, die du wiederherstellen möchtest.  
5. Wähle **Wiederherstellen**.
6. Starte Obsidian neu, um die Einstellungen zu übernehmen. Für mehr Informationen, siehe [[Obsidian Sync einrichten#Obsidian Sync konfigurieren|Obsidian Sync konfigurieren]].
