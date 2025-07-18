---
aliases:
  - CSS-Schnipsel
  - Snippets
description: Erfahre, wie du das Aussehen von Obsidian ändern kannst, ohne ein Farbschema zu erstellen.
mobile: true
permalink: snippets
publish: true
---

Erfahre, wie du das Erscheinungsbild von Obsidian in einzelnen Aspekten anpassen kannst, ohne gleich ein ganzes [Theme entwickeln](https://docs.obsidian.md/Themes/App+themes/Build+a+theme) zu müssen.

> [!TIP] Wenn du eine Anleitung für den Einsatz von CSS mit [[Obsidian Publish/Einführung|Obsidian Publish]] suchst, solltest du den Abschnitt über die [[Customize your site|Individualisierung deiner Webseite]] lesen.

CSS (Cascading Style Sheets) ist eine Sprache, mit der man die Darstellung von HTML-Dokumenten beeinflussen kann. Mit Hilfe von CSS-Bausteinen kannst du Teile der Bedienoberfläche von Obsidian ändern, wie bspw. die Größe oder Farbe von Überschriften. Obsidian stellt einige [CSS-Variablen](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables) zur Verfügung, über die sich Bedienelemente leicht deinen Bedürfnissen anpassen lassen.

Obsidian sucht CSS-Bausteine im [[Konfigurationsordner|Konfigurationsordner]] deines Vaults.

## Snippets hinzufügen

Um einen CSS-Baustein in Obsidian ![[lucide-monitor-check.svg#icon]] **Desktop** hinzuzufügen:

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Darstellung → CSS-Bausteine** klicke **Baustein-Ordner öffnen** ( ![[lucide-folder-open.svg#icon]] ).
3. Erstelle im Baustein-Ordner eine CSS-Datei, die dein CSS-Schnipsel enthält.
4. Klicke in Obsidian unter **Darstellung → CSS-Bausteine** auf **Bausteine neu laden** ( ![[lucide-refresh-cw.svg#icon]] ), damit dein Snippet in der Liste erscheint.
5. Aktiviere den CSS-Baustein über den Schalter daneben.

Um einen CSS-Baustein in Obsidian ![[obsidian-icon-smartphone.svg#icon]] **Mobile/Tablet** hinzuzufügen:

1. Öffne einen Dateimanager und navigiere zu deinem Vault. Der Speicherort deines Vaults wird dir angezeigt, wenn du in der _Vault-Verwaltung_ auf den Vault tippst.
2. Öffne den [[Konfigurationsordner|Konfigurationsordner]] und erstelle einen Ordner `snippets`, falls dieser noch nicht existiert.
3. Kopiere deinen CSS-Baustein in diesen Ordner. %%Add your CSS snippet to this folder.%%
4. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ) in Obsidian.
5. Tippe auf **Darstellung** und scrolle bis ganz nach unten.
6. Im Abschnitt **CSS-Bausteine** tippe auf **Bausteine neu laden** ( ![[lucide-refresh-cw.svg#icon]] ), damit dein Snippet in der Liste erscheint.
7. Tippe den Schalter neben deinem CSS-Baustein, um ihn zu aktivieren.

Weiterhin kannst du

- Änderungen an den Darstellungseinstellungen [[Synchronisiere deine Notizen zwischen Geräten|synchronisieren]].
- Eine externe Erweiterung verwenden, um CSS-Schnipsel direkt in Obsidian zu erstellen.

Ist ein CSS-Baustein aktiviert, wird Obsidian Änderungen daran automatisch erkennen und anwenden, sobald du die CSS-Datei speicherst.

> [!TIP] Du musst Obsidian nicht neu starten, damit die Änderungen wirksam werden. Möglicherweise musst du die Anwendung jedoch über die [[Command palette|Befehlspalette]] neu laden ohne zu speichern, um die Änderungen im aktuellen Farbschema bzw. der aktuellen Notiz zu sehen.

## CSS für Obsidian schreiben

Obsidian bietet verschiedene Möglichkeiten, dir die Erstellung von CSS-Bausteinen zu erleichtern.

Die Anwendung verfügt über eine Vielzahl von [CSS-Variablen](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables), mit denen sich Elemente der Bedienoberfläche leicht anpassen lassen und vordefinierte [[Properties#Property types|Eigenschaften]], um das Aussehen von einer oder mehreren Notizen zu ändern.

> [!example] Variablen
> Erstelle eine Datei mit dem Namen `headers.css` und dem folgenden Inhalt, um die Farben der sechs [[Basic formatting syntax#Headings|Überschriftenebenen]] in einen Regenbogen zu verwandeln:
>
> ```css
> body {
>   --h1-color: red;
>   --h2-color: orange;
>   --h3-color: yellow;
>   --h4-color: green;
>   --h5-color: blue;
>   --h6-color: pink;
> }
> ```

> [!example] CSS-Klassen
> Weise der vordefinierten [[Properties|Eigenschaft]] `cssclasses` den Namen einer CSS-Klasse (oder eine Liste von CSS-Klassen) zu, um einer oder mehreren Notizen ein anderes Aussehen zu verleihen.
> 
> **CSS-Baustein**:
> ```css
> .no-inline .inline-title {
>    display: none;
> }
> ```
> 
> **YAML/Properties**:
> ```yaml
> cssclasses:
>  - no-inline
> ```
> 
> Für jede Notiz, die in der Frontmatter-Eigenschaft `cssclasses` den Wert `no-inline` enthält, wird der Seitentitel ausgeblendet. Aktiviere in den Einstellungen **Darstellung → Zeige Titel in Notiz**, um die Wirkung zu sehen, andernfalls ist diese Einstellung ohnehin bereits für den gesamten Vault wirksam.

Wir empfehlen, deinen CSS-Baustein vor der Aktivierung zu validieren, z.B. mit dem [CSS Validation Service](https://jigsaw.w3.org/css-validator/), da ungültiges CSS nicht zuverlässig funktionieren wird.

## Erfahre mehr

- Wenn CSS für dich neu ist, besuche [Grundlegendes zur CSS-Gestaltung](https://developer.mozilla.org/de/docs/Learn_web_development/Core/Styling_basics) von Mozilla.
- Für mehr Informationen zum Stylen von Obsidian siehe:
  - [About styling](https://docs.obsidian.md/Reference/CSS+variables/About+styling)
  - [Build a theme](https://docs.obsidian.md/Themes/App+themes/Build+a+theme)
  - [Build a Publish theme](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/Build+a+Publish+theme)
  - [Obsidian CSS Inspector workflow](https://forum.obsidian.md/t/obsidian-css-inspector-workflow/58178)
