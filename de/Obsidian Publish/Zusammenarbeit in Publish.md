---
aliases:
  - Obsidian Publish/Zusammenarbeit
description: Erfahre, wie du mit anderen Obsidian-Anwendern gemeinsam eine Webseite veröffentlichen kannst mit Obsidian Publish.
publish: true
mobile: true
permalink: publish/zusammenarbeit
---

Erfahre, wie du mit anderen Obsidian-Anwendern gemeinsam an einer [[Einführung in Obsidian Publish|Obsidian Publish]]-Webseite arbeiten kannst. Indem du deine Freunde oder Kollegen als Mitwirkende zu deiner Webseite hinzufügst, können diese Änderungen auf deiner Webseite veröffentlichen.

Nur der Eigentümer der Webseite benötigt dafür ein aktives Obsidian Publish-Abonnement. Für Mitwirkende genügt ein [Obsidian-Benutzerkonto](https://obsidian.md/account).

> [!warning] Bevor du Änderungen an einer freigegebenen Webseite veröffentlichst, denke daran, die [[#Änderungen zwischen Mitwirkenden synchronisieren|Änderungen zwischen Mitwirkenden zu synchronisieren]]. Andernfalls besteht die Gefahr, dass Änderungen von anderen Mitwirkenden überschrieben werden.

## Mitwirkende hinzufügen

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ) oder öffne die [[Befehlspalette]] und wähle **Veröffentlichen: Änderungen veröffentlichen...**
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. Neben **Website-Zusammenarbeit** wähle **Verwalten**.
4. Gib unter **Nutzer einladen** die Mailadresse des Mitwirkenden ein.
5. Wähle **Hinzufügen**.

## Mitwirkende entfernen

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ) oder öffne die [[Befehlspalette]] und wähle **Veröffentlichen: Änderungen veröffentlichen...**
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. Neben **Website-Zusammenarbeit** wähle **Verwalten**.
4. Neben dem Mitwirkenden, den du entfernen möchtest, wähle **Nutzer entfernen** ( ![[lucide-x.svg#icon]] ).

## Änderungen zwischen Mitwirkenden synchronisieren

Obsidian Publish synchronisiert veröffentlichte Änderungen nicht automatisch mit deinem lokalen Vault. Mitwirkende müssen die Synchronisierung von Änderungen manuell anstoßen.

Um eine lokale Notiz mit den Änderungen von der Live-Version deiner Webseite zu synchronisieren:

1. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ) oder öffne die [[Befehlspalette]] und wähle **Veröffentlichen: Änderungen veröffentlichen...**
2. Öffne mit Rechtsklick (oder durch langes Drücken) auf die Änderung, die du synchronisieren möchtest, das Kontextmenü und wähle **Live-Version verwenden**. **Die Notiz in deinem lokalen Vault wird dadurch überschrieben.**

> [!tip] Wir empfehlen, ein anderes Tool zur Synchronisierung von Änderungen zwischen Vaults zu verwenden, wie bspw. [[Einführung in Obsidian Sync|Obsidian Sync]] oder [git](https://git-scm.com/).

## Berechtigungen

Die folgende Tabelle enthält die verfügbaren Berechtigungsprofile für den Webseiten-Eigentümer und Mitwirkende:

| Aktion                            | Mitwirkende | Eigentümer |
| --------------------------------- | :---------: | :--------: |
| Neue Seiten veröffentlichen       |      ✓      |     ✓      |
| Änderungen veröffentlichen        |      ✓      |     ✓      |
| Seiten deaktivieren               |      ✓      |     ✓      |
| Seiteneinstellungen konfigurieren |             |     ✓      |
| Berechtigungen verwalten          |             |     ✓      |

