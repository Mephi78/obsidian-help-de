---
aliases:
  - Obsidian Sync/Speicherlimit für Remote-Vaults
  - Speicherlimits
  - Obsidian Sync/Speicherbegrenzung
description: Informiere dich über die verfügbaren Abo-Tarife für Obsidian Sync.
mobile: true
permalink: sync/tarife
publish: true
---

## Tarifübersicht

Um deine Notizen mit [[Einführung in Obsidian Sync|Obsidian Sync]] zu synchronisieren, benötigst du ein Sync-Abonnement. Du kannst einen der Abo-Tarife erwerben, indem du dich mit deinem [Obsidian-Nutzerkonto](https://obsidian.md/account/sync) anmeldest. Unsere Preisliste findest du auch auf unserer [Sync-Startseite](https://obsidian.md/sync).

Unsere Abo-Tarife *Sync Standard* und *Sync Plus* im Vergleich:

|                                                   | Sync Standard | Sync Plus        |
| ------------------------------------------------- | ------------- | ---------------- |
| Synchronisierte Vaults                            | 1             | 10               |
| Maximale Dateigröße                               | 5 MB          | 200 MB           |
| Gesamtspeicherplatz                               | 1 GB          | 10 GB bis 100 GB |
| [[Versionsverlauf]]                               | 1 Monat       | 12 Monate        |
| Geräte                                            | Unbegrenzt    | Unbegrenzt       |
| [[Zusammenarbeit in einem freigegebenen Vault\|Vault-Freigabe]] | Ja            | Ja               |

## Speicherkapazität

Die Datenmenge, die du mit [[Einführung in Obsidian Sync|Obsidian Sync]] speichern kannst, hängt von deinem Abo-Tarif ab. Mit *Sync Plus* kannst du über dein persönliches [Obsidian-Dashboard](https://obsidian.md/account/sync) zusätzlichen Speicherplatz erwerben (bis zu 100 GB). Für mehr Informationen, siehe [[Häufig gestellte Fragen]].

Es gibt ein kontoübergreifendes Gesamtspeicherlimit für alle Notizen in deinen Vaults. [[Versionsverlauf]] und [[Anhänge]] werden auf das Speicherlimit deines Nutzerkontos ebenfalls angerechnet.

Wenn du die Speichergrenze für dein Konto erreichst, stellt Obsidian Sync die Synchronisierung deiner Dateien ein und du wirst aufgefordert, deine Remote-Vaults zu bereinigen.

### Sehr große Dateien finden und löschen

Um sehr große Dateien in deinem Vault zu identifizieren und zu löschen:

1. Öffne **Einstellungen** → **Sync**.
2. Wähle **Zeige größte Dateien** neben **Vault-Größe über Limit**. 
	1. Falls **Vault-Größe über Limit** nicht angezeigt wird, hast du ==das Limit noch nicht erreicht==.
3. Schließe den Dialog **Zeige größte Dateien**.
4. Lösche einige große Dateien, die du nicht länger benötigst.
5. Warte, bis Obsidian die Überprüfung abgeschlossen hat. Das kann eine Weile dauern.
6. Öffne **Einstellungen** → **Sync**.
7. Wähle **Bereinigen** neben **Vault-Größe über Limit**. Die gelöschten Dateien werden nun auch aus dem Remote-Vault gelöscht, um Speicherplatz zu schaffen.

Nachdem die Bereinigung auf dem Sync-Server übernommen wurde, sollte Obsidian Sync wieder wie gewohnt arbeiten.

### Neuen Remote-Vault erstellen

Du kannst einen **neuen Remote-Vault erstellen**, um sehr große Dateien bereits vor der Synchronisierung auszuschließen. Der Versionsverlauf deiner Dateien wird zurückgesetzt, wenn du einen neuen Remote-Vault erstellst. Stelle sicher, dass du den Versionsverlauf nicht mehr benötigst, bevor du mit den folgenden Schritten fortfährst.

Um einen neuen Remote-Vault zu erstellen:

1. Öffne **Einstellungen** → **Sync**.
2. Neben **Remote-Vault** klicke **Verwalten**.
3. Wähle **Neuen Vault erstellen** und folge den [[Obsidian Sync einrichten#Neuen Remote-Vault erstellen|bekannten Schritten]]. Falls dir die Vaults ausgehen, musst du möglicherweise zunächst einen Remote-Vault [[Obsidian Sync einrichten#Verbindung zu Remote-Vault trennen|trennen]] und [[Obsidian Sync einrichten#Remote-Vault löschen|löschen]].
4. Lege vor der Synchronisierung mit deinem neuen Remote-Vault die auszuschließenden Dateien fest.
5. Starte Obsidian neu, damit die Änderungen greifen.
6. Öffne **Einstellungen** → **Sync**.
7. Wähle **Fortfahren**, um die Synchronisierung mit dem neuen Remote-Vault zu starten.

Der neue Remote-Vault sollte weniger Speicherplatz verbrauchen als der vorherige, da der Versionsverlauf und die ausgeschlossenen Dateien nun fehlen.

## Tarif hochstufen

Über dein persönliches [Obsidian-Dashboard](https://obsidian.md/account/sync) kannst du dein Sync-Abo vom Standard-Tarif zum Plus-Tarif hochstufen oder im Plus-Tarif das Speicherlimit bis auf 100 GB erhöhen.

## Tarif herabstufen

Wenn du deinen Tarif herabstufen möchtest, musst du ggf. zunächst Speicherplatz freigeben, damit der von deinen Remote-Vaults belegte Speicher die Grenzen des neuen Tarifs nicht überschreitet. Derzeit gibt es keinen schnelle Weg, bestimmte Dateien aus einem existierenden Remote-Vault zu entfernen, da Anhänge bis zu zwei Wochen lang im Versionsverlauf behalten und auf dein Speicherlimit angerechnet werden. 

An schnellsten kannst du Sync-Speicher zu reduzieren, indem du einen neuen Remote-Vault erstellst, bei dem Anhänge deaktiviert sind. Lösche anschließend den alten Remote-Vault, um den Speicherplatz freizugeben. Beachte, dass auf diese Weise auch der Versionsverlauf verloren geht.

Wenn du von *Sync Plus* zu *Sync Standard* wechselst, musst du auch die Anzahl deiner synchronisierten Vaults auf einen einzigen reduzieren, bevor eine Herabstufung möglich wird.

### Versionsverlauf beibehalten

Anhänge werden bis zu zwei Wochen in deinem [[Versionsverlauf]] gespeichert. Falls du für die nahe Zukunft eine Herabstufung deines Tarifs planst, könntest du damit beginnen, Anhänge aus deinem lokalen Vault zu entfernen. 

Nach zwei Wochen werden diese automatisch aus dem Versionsverlauf deines Remote-Vaults entfernt und damit nicht mehr auf dein Speicherlimit angerechnet, so dass du deinen Abo-Tarif herabstufen kannst und gleichzeitig der Versionsverlauf für die restlichen Dateien, insbesondere deiner Notizen, erhalten bleibt.
