---
permalink: plugins/graph
---

Die Graph-Ansicht ist eine [[Core plugins|Standard-Erweiterung]], die Beziehungen zwischen den Notizen in deinem Vault sichtbar macht.

Um die Graph-Ansicht zu öffnen, klicke **Graph-Ansicht öffnen** ( ![[lucide-git-fork.svg#icon]] ) im [[Ribbon|Seitenleisten-Menü]].

- Die Knoten oder Kreise repräsentieren deine Notizen.
- Kanten repräsentieren [[Internal links|interne Verlinkungen]] zwischen zwei Knoten bzw. Notizen.

Je mehr Referenzen auf eine Notiz zeigen, desto größer wird der Knoten dargestellt, der diese Notiz repräsentiert.

Interagiere mit den Knoten im Graphen:

- Fahre mit der Maus über die Kreise, um alle Verbindungen einer Notiz hervorzuheben.
- Klicke auf eine Notiz im Graphen, um diese zu öffnen.
- Öffne mit Rechtsklick auf eine Notiz das Kontextmenü, um weitere Aktionen auf diese Notiz anzuwenden.

Navigiere im Graphen:

- Vergrößere oder verkleinere die Ansicht mit dem Scrollrad deiner Maus oder mit den Tasten `+` und `-` auf der Tastatur.
- Bewege den Graphen per Drag & Drop oder mit den Pfeiltasten deiner Tastatur.

Du kannst dabei `Shift` gedrückt halten, um die Navigation zu beschleunigen.

## Einstellungen

Öffne die Graph-Einstellungen per Klick auf das Zahnrad-Symbol ( ![[lucide-settings.svg#icon]] ) oben rechts in der Graph-Ansicht.

Klicke **Voreinstellungen wiederherstellen** ( ![[lucide-rotate-ccw.svg#icon]] ) oben rechts, um die Einstellungen der Graph-Ansicht wieder auf die Standardwerte zurückzusetzen.

### Filter

Dieser Abschnitt regelt, welche Knoten im Graphen angezeigt werden.

- **Suche Dateien** lässt dich Notizen nach bestimmten Suchkriterien filtern. Erfahre später mehr darüber, wie du [[Search|fortgeschrittene Suchfilter erstellen]] kannst.
- **Tags** lässt dich deine Tags (Kategorien) als separate Knoten anzeigen.
- **Anhänge** bestimmt, ob Dateien angezeigt werden sollen, die keine Notizen sind.
- **Nur existierende Dateien zeigen** lässt dich im Vault nicht existierende Dateien ausblenden. Da es möglich ist, Notizen zu verlinken, die noch nicht existieren, kann dir diese Einstellung helfen, die Graph-Ansicht einzugrenzen auf solche Dateien, die bereits vorhanden sind.
- **Verwaiste Dateien** regelt die Anzeige von nicht verlinkten Dateien.

### Gruppen

Erstelle unterscheidbare Gruppen von Notizen, indem du ihnen Farben zuweist.

Um eine neue Gruppe zu erstellen:

1. Klicke **Neue Gruppe**.
2. Im Suchfeld tippe einen Suchbegriff für die Notizen ein, die du gruppieren möchtest.
3. Klicke auf den farbigen Kreis daneben, um der neuen Gruppe eine Farbe zuzuweisen.

Erfahre später mehr darüber, wie du [[Search|fortgeschrittene Suchfilter erstellen]] kannst.

### Anzeige

Dieser Abschnitt steuert, wie Knoten und Kanten im Graphen dargestellt werden.

- **Pfeile** verwandelt die Darstellung auf Wunsch in einen gerichteten Graphen.
- **Grenze Text-Transparenz** gibt an, bei welcher Vergrößerung der Dateiname am Knoten angezeigt bzw. ausgeblendet wird.
- **Knotengröße** die Größe der Kreise, die deine Notizen repräsentieren.
- **Kantenstärke** bestimmt die Linienstärke der Verknüpfungen.
- **Animieren** startet eine [[#Starte eine Zeitraffer-Animation|Zeitraffer-Animation]].

### Kräfte

Dieser Abschnitt bestimmt die Kräfte, die auf jeden Knoten im Graphen wirken.

- **Zentrierkraft** steuert, wie kompakt der Graph dargestellt wird. Je größer der Wert, umso kreisförmiger wird die Darstellung.
- **Abstoßungskraft** steuert, wie stark ein Knoten andere Knoten abstößt, um Überlappungen zu vermeiden.
- **Linkkraft** bestimmt die Zugkraft auf jede Verknüpfung. Wenn du dir einen Link als ein Gummiband vorstellst, steuert die Zugkraft, wie straff oder locker das Band ist.
- **Linkabstand** regelt die Länge der Kanten zwischen den Knoten.

## Starte eine Zeitraffer-Animation

Notizen und Anhänge erscheinen in chronologischer Reihenfolge basierend auf ihrem Erstellungszeitpunkt.

![[obsidian-graph-view.png#interface]]

## Lokaler Graph

Um einen lokalen Graphen zu öffnen, nutze den Befehl **Lokalen Graphen öffnen**. Während die Graph-Ansicht alle Dateien in deinem Vault enthält, zeigt der lokale Graph nur Dateien, die mit der aktiven Notiz verknüpft sind.

Der lokale Graph hat dieselben [[#Einstellungen|Einstellungsmöglichkeiten]] wie die Graph-Ansicht. Zusätzlich hast du weitere Filtermöglichkeiten. Du kannst wählen, ob eingehende, ausgehende und Links zwischen benachbarten Knoten angezeigt werden sollen oder nicht. Über den Schieberegler wird die Darstellungstiefe für den lokalen Graphen angepasst. Jede Tiefenstufe fügt der Ansicht Dateien hinzu, die mit den Notizen in der vorherigen Tiefenebene verknüpft sind.
