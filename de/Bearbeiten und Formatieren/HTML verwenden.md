---
aliases:
  - Fortgeschrittene Themen/HTML-Bereinigung
  - Bearbeiten und formatieren/HTML-Formatierung
publish: true
---

Obsidian unterstützt HTML, damit du deine Notizen nach Belieben gestalten oder sogar [[Webseiten einbetten|Webseiten einbetten]] kannst. Die Verwendung von HTML birgt jedoch Risiken. Um Schaden durch bösartigen Code zu verhindern, *bereinigt* Obsidian jeglichen HTML-Code in deinen Notizen.

> [!example] Beispiel
> Das `<script>`-Element ermöglicht es normalerweise, JavaScript-Code auf deinem Client auszuführen, sobald dieser geladen wird. Würde Obsidian HTML nicht bereinigen, könnte ein Angreifer dich dazu verleiten, Text in eine Notiz zu kopieren, der JavaScript-Code enthält, welcher sensible Informationen von deinem Gerät extrahiert und an den Angreifer zurück sendet.

Da Markdown die Formatierung von Text jedoch nur in eingeschränktem Umfang unterstützt, bietet Obsidian mit dem *bereinigten* HTML eine weitere Möglichkeit, um deine Notizen aufzupeppen. Unten sind einige beliebte Verwendungen für HTML aufgeführt.

> [!info] Erfahre mehr über die Verwendung von `<iframe>` im Abschnitt [[Webseiten einbetten]].

### Kommentare

Obwohl [[Formatierungsgrundlagen#Kommentare|Markdown-Kommentare]] die bevorzugte Variante darstellen, versteckte Kommentare in deine Notizen einzufügen, kannst du auch `<!-- HTML-Kommentare -->` verwenden. Das ist für manche Konvertierungsprogramme notwendig, wie bspw. [Pandoc](https://pandoc.org), die nur eingeschränkte Unterstützung für Markdown-Kommentare bieten.

### Unterstreichen

Wenn du einen Eintrag in deiner Notiz <u>schnell unterstreichen</u> möchtest, verwende `<u>zu unterstreichender Text</u>`.

### Durchstreichen

Verwende `<s>durchzustreichender Text</s>`, um <s>deinen Text</s> zu streichen.

### Span/Div

Die HTML-Tags `span` und `div` können verwendet werden, um eigene CSS-Klassen aus einem [[CSS-Bausteine|CSS-Baustein]] oder benutzerdefinierte Stile auf Textabschnitte anzuwenden. Mit `<span style="font-family: cursive">Text in anderer Schriftart</span>` kannst du bspw. die <span style="font-family: cursive">Schriftart ändern</span>.
