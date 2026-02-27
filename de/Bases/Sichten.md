---
permalink: bases/sichten
publish: true
---

Mit *Sichten* kannst du die Informationen in einer [[Einführung in Bases|Base]] auf verschiedene Weise organisieren. Eine Base kann mehrere Sichten enthalten, jede mit einer eigenen Konfiguration zum Anzeigen, Sortieren und Filtern von Dateien.

Vielleicht möchtest du eine Base "Bücher" erstellen mit verschiedenen Sichten für eine "Leseliste" und "kürzlich gelesene" Bücher. Die erste Sicht in der Liste von `views` wird standardmäßig geladen. Ziehe Sichten an ihrem Symbol, um die Reihenfolge zu ändern.

## Sichten hinzufügen

Es gibt zwei Möglichkeiten, Sichten zu einer Base hinzuzufügen:

- Klicke auf den Namen der Sicht oben links und wähle **Sicht hinzufügen**.
- Oder öffne die [[Befehlspalette]] und Wähle **Bases: Sicht hinzufügen**.

## Sicht-Einstellungen

Jede Sicht hat ihre eigenen Konfigurationsoptionen. Um Sichten anzupassen:

- Klicke auf den Namen der Sicht oben links und wähle den Pfeil neben der Sicht, die du konfigurieren möchtest.
- Oder öffne die Sicht-Einstellungen mit Rechtsklick auf den Namen der Sicht.

## Layout

Sichten können in verschiedenen Layouts angezeigt werden, als **Tabelle**, **Liste** oder **Karten**. [[Externe Erweiterungen]] können zusätzliche Layouts hinzufügen. Einige Layouts sind noch in Entwicklung und nur im Obsidian-[[Early-Access-Versionen|Insider-Build]] verfügbar.

| Layout                  | Beschreibung                                                                                        | App&nbsp;Version |
| ----------------------- | --------------------------------------------------------------------------------------------------- | ---------------- |
| [[Tabelle\|Tabelle]] | Dateien werden als Zeilen und [[Eigenschaften]] als Spalten dargestellt.                            | 1.9              |
| [[Karten\|Karten]]  | Dateien werden als Karten in einem Raster dargestellt, bspw. zur Erstellung von Bildgalerien.       | 1.9              |
| [[Liste\|Liste]]    | Dateien werden als einfache oder nummerierte [[Formatierungsgrundlagen#Listen\|Liste]] dargestellt. | 1.10             |
| [[Landkarte\|Landkarte]] | Dateien werden als Stecknadel-Markierungen auf einer interaktiven Karte dargestellt.                | 1.10             |

## Filter

Eine Base ohne Filter zeigt alle Dateien deines Vaults an. Mit Filtern kannst du Ergebnislisten eingrenzen, so dass nur Dateien angezeigt werden, die bestimmten Kriterien entsprechen. Du kannst Filter bspw. verwenden, um nur Dateien anzuzeigen, die mit einem bestimmten [[Tags|Tag]] versehen oder in einem bestimmten Ordner enthalten sind. Es stehen eine Reihe von Filtertypen zur Auswahl.

Wähle die Schaltfläche **Filter** oben in einer Base, um die Filter zu bearbeiten.

Filter können auf alle Sichten in der Base oder nur auf eine einzelne angewendet werden. Konfiguriere dazu den Filter in einem der beiden Abschnitte im **Filter**-Menü.

- **Alle Sichten**: Filter werden auf alle Sichten in der Base angewendet.
- **Diese Sicht**: Filter werden auf die aktive Sicht angewendet.

#### Filterkomponenten

Filter bestehen aus drei Komponenten:

1. **Eigenschaft** — ermöglicht die Auswahl einer der im Vault verwendeten [[Eigenschaften|Eigenschaften]], [[Bases Syntax#Datei-Eigenschaften|Dateieigenschaften]] eingeschlossen.
2. **Operator** — definiert, wie die Bedingungen verglichen werden sollen. Die Liste der verfügbaren Operatoren hängt vom [[Eigenschaften#Eigenschaftstypen|Eigenschaftstyp]] ab. 
3. **Wert** — definiert den Wert, mit dem verglichen werden soll. Werte können auch mathematische [[Funktionen|Funktionen]] enthalten.

#### Logische Verknüpfungen

- **Alle folgenden Bedingungen treffen zu** ist eine `UND`-Anweisung (Konjunktion) — es werden nur Ergebnisse angezeigt, für die *alle* Bedingungen der Filtergruppe erfüllt sind.
- **Mindestens eine der folgenden Bedingungen trifft zu** ist eine `ODER`-Anweisung (Disjunktion) — es werden nur Ergebnisse angezeigt, für die *mindestens eine* Bedingung der Filtergruppe zutrifft.
- **Keine der folgenden Bedingungen trifft zu** ist eine `NICHT`-Anweisung (Negation) — Dateien, für welche *mindestens eine* Bedingung der Filtergruppe zutrifft, werden *nicht* angezeigt.

#### Filtergruppen

Mit Filtergruppen kannst du komplexere logische Verknüpfungen definieren.

#### Editor für komplexe Filter

Klicke im **Filter**-Menü auf die Code-Schaltfläche ( ![[lucide-code-xml.svg#icon]] ), um in den Editor für **komplexe Filter** zu wechseln. Damit wird die reine [[Bases Syntax|Base Syntax]] zur Bearbeitung des Filters angezeigt und du kannst komplexere [[Funktionen|Funktionen]] verwenden, die im interaktiven Editor für **einfache Filter** nicht verfügbar sind.

## Ergebnisse sortieren und gruppieren

Öffne das Menü ![[lucide-arrow-up-down.svg#icon]] **Sortieren** und gruppiere die Ergebnisse in einer Sicht.

Du kannst Ergebnisse nach einer oder mehreren Eigenschaften in aufsteigender bzw. absteigender Reihenfolge sortieren. So lassen sich Notizen ganz einfach nach Name, Zeitpunkt der letzten Bearbeitung oder jeder anderen Eigenschaft - einschließlich Formeln - auflisten.

Du kannst Ergebnisse auch nach einer Eigenschaft gruppieren, um ähnliche Elemente in visuell unterscheidbaren Abschnitten zu organisieren. Derzeit unterstützt Obsidian lediglich eine Gruppierung nach einer einzelnen Eigenschaft.

### Eine Sortierung hinzufügen

1. Öffne das Menü **Sortieren** oberhalb der Sicht.
2. Wähle die Eigenschaft, nach der du sortieren (oder gruppieren) möchtest.
3. Wenn du mehrere Sortierungen hast, ziehe sie über das ![[lucide-grip-vertical.svg#icon]] Handle nach oben oder unten, um deren Priorität zu ändern.

Die Optionen zum Sortieren der Ergebnisse sind abhängig vom Eigenschaftstyp:

- **Text**: Sortiere *alphabetisch* (A→Z) oder in *umgekehrter alphabetischer Reihenfolge* (Z→A).
- **Zahl**: Sortiere von *klein nach groß* (0→1) oder *groß nach klein* (1→0).
- **Datum und Uhrzeit**: Sortiere von *alt bis neu* oder *neu bis alt*.

### Eine Sortierung entfernen

1. Öffne das Menü **Sortieren** oberhalb der Sicht.
2. Entferne eine Sortierung oder Gruppierung über die Schaltfläche ![[lucide-trash-2.svg#icon]] daneben.

## Ergebnisse begrenzen, kopieren und exportieren

### Ergebnisse begrenzen

Die Schaltfläche **Ergebnisse** neben dem Sichtnamen zeigt die Anzahl der Ergebnisse in der aktiven Sicht. Wenn du darauf klickst, erscheint das *Ergebnisse*-Menü. Hier kannst du die Anzahl der Ergebnisse begrenzen und auf weitere Aktionen zugreifen.

### In Zwischenablage kopieren

Diese Aktion kopiert die Ergebnisse in die Zwischenablage. Du kannst sie anschließend in eine Markdown-Datei oder in andere Dokumente kopieren, bspw. Excel oder Google Sheets.

### CSV exportieren

Diese Aktion speichert die aktive Sicht in eine CSV-Datei.