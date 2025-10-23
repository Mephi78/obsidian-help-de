---
aliases:
  - Obsidian Publish/Notizen veröffentlichen und entpublizieren
description: Erfahre, wie du mit Obsidian Publish Inhalte veröffentlichen kannst.
permalink: publish/publish
mobile: true
publish: true
---

Hier erklären wir, wie du veröffentlichte Inhalte verwalten kannst. Um zu erfahren, wie du die Darstellung deiner Webseite anpassen kannst, siehe [[Webseite individualisieren]].

## Voraussetzungen

- Ein Obsidian-Nutzerkonto. Falls du noch keines besitzt, [registriere dich jetzt](https://obsidian.md/auth?returnto=%2Faccount%2Fpublish#signup).
- Ein aktives Obsidian Publish-Abo. Falls du noch keines besitzt, erwirb ein Abo über [dein Obsidian-Nutzerkonto](https://obsidian.md/account/publish).
- Die Obsidian-Erweiterung **Veröffentlichen** ist [[Obsidian Publish einrichten#Obsidian Publish aktivieren|aktiviert]].
- Eine [[Webseiten verwalten#Neue Webseite erstellen|Webseite]] wurde bereits erstellt.

## Notizen veröffentlichen

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Im **Publish**-Dialog wähle **Neu**, um alle nicht veröffentlichten Notizen zu sehen.
3. Wähle die Notizen aus, die du veröffentlichen möchtest.
4. Bestätige mit **Veröffentlichen**.

## Notizen entpublizieren

Notizen verbleiben in deinem lokalen Vault, auch wenn du sie entpublizierst, also von deiner Webseite löschst.

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Im **Publish**-Dialog wähle **Unverändert**, um alle veröffentlichten Notizen zu sehen.
3. Wähle die Notizen aus, die du entpublizieren möchtest.
4. Bestätige mit **Veröffentlichen**.

## Veröffentlichte Notizen aktualisieren

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Im **Publish**-Dialog wähle **Änderungen**, um alle seit der letzten Veröffentlichung geänderten Notizen zu sehen.
3. Wähle die Notizen aus, die du aktualisieren möchtest.
4. Bestätige mit **Veröffentlichen**.

> [!hint] In diesem Schritt werden auch lokal umbenannte oder gelöschte Notizen und Bilder von der Webseite gelöscht. Du musst die Checkbox manuell aktivieren, damit diese Daten von der Webseite gelöscht werden, da diese aus Sicherheitsgründen nicht automatisch ausgewählt werden.

## Verlinkte Daten veröffentlichen

Beim Veröffentlichen von Notizen, die interne Links oder eingebettete Bilder enthalten, entstehen möglicherweise tote Links, wenn die verlinkten Inhalte nicht auch veröffentlicht werden. **Obsidian Publish** hilft dir, dies zu verhindern, indem alle in bereits ausgewählten Notizen verlinkten Medien und Notizen automatisiert ausgewählt werden.

Um alle verlinkten Notizen in die Auswahl aufzunehmen, wähle **Verlinkte hinzufügen** im **Publish**-Dialog.

Überprüfe die Auswahl vor dem Veröffentlichen, um sicherzustellen, dass keine Daten ausgewählt wurden, die du noch nicht veröffentlichen möchtest.

> [!tip] Die Funktion **Verlinkte hinzufügen** beachtet die von dir als [[#Daten ignorieren|zu ignorieren]] definierten Daten.

## Daten zum Veröffentlichen automatisch auswählen

Um eine Notiz in der Liste der geänderten oder neuen Notizen automatisch auszuwählen, füge dieser die [[Eigenschaften|Eigenschaft]] `publish: true` hinzu.

Notizen und Bilder werden ebenfalls automatisch ausgewählt, wenn sie sich in bestimmten Ordnern befinden, die als **Enthaltene Ordner** definiert wurden:

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Wähle **Publish-Filter verwalten** ( ![[lucide-filter.svg#icon]] ).
3. Im Abschnitt **Enthaltene Ordner** wähle **Verwalten**.
4. Wähle aus der Autovervollständigen-Liste die Ordner, die du einbeziehen möchtest.
5. Der Ordner wird der Liste hinzugefügt. Du kannst noch weitere Ordner hinzufügen.
6. Bestätige abschließend mit **Fertig**.

### Daten ignorieren

Wenn Obsidian Publish eine Notiz ignorieren soll, setze ihre [[Eigenschaften|Eigenschaft]] `publish: false`. Die Notiz wird nun nicht mehr angezeigt in der Liste im **Publish**-Dialog.

Notizen und Bilder werden ebenfalls automatisch ignoriert, wenn sie sich in bestimmten Ordnern befinden, die als **Nicht enthaltene Ordner** definiert wurden:

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Wähle **Publish-Filter verwalten** ( ![[lucide-filter.svg#icon]] ).
3. Im Abschnitt **Nicht enthaltene Ordner** wähle **Verwalten**.
4. Wähle aus der Autovervollständigen-Liste die Ordner, die du ausschließen möchtest.
5. Der Ordner wird der Liste hinzugefügt. Du kannst noch weitere Ordner hinzufügen.
6. Bestätige abschließend mit **Fertig**.

> [!note] `publish: true` überschreibt die Filter-Regel **Nicht enthaltene Ordner**
> Wenn in einer Notiz `publish: true` gesetzt ist, wird diese auch dann veröffentlicht, wenn sie sich in einem als **Nicht enthaltene Ordner** definierten Ordner befindet. Das liegt daran, dass `publish: true` eine spezifischere Kontrolle ermöglicht.