---
permalink: web-clipper/interpreter
aliases:
  - Interpreter
publish: true
---

Mit der [[Einführung in Obsidian Web Clipper|Web Clipper]]-Funktion *Interpreter* kannst du in natürlicher Sprache mit einer Webseite interagieren. Interpreter hilft dir beim Erfassen und extrahieren von Daten aus einer Webseite, die du nach Obsidian speichern möchtest. Interpreter kann z.B.:

- Bestimmte Textfragmente extrahieren.
- Die Informationen zusammenfassen oder erklären.
- Text aus einem Format in ein anderes konvertieren.
- Text in eine andere Sprache übersetzen.

Interpreter verwendet Sprachmodelle, um die Informationen auf einer Webseite zu verarbeiten und gibt das Ergebnis mittels [[Variablen|Variablen]] zurück, die du in deine [[Obsidian Web Clipper/Vorlagen|Web Clipper Vorlagen]] einfügen kannst.

![[web-clipper-interpreter-demo.mp4#interface]]

## Beispielhafte Prompts

Prompts verwenden die [[Variablen|Variablen]]-Syntax `{{"dein Prompt"}}`. Du kannst diese Syntax mit jeder natürlichsprachigen Eingabe verwenden. Hier ein paar Beispiele:

- `{{"eine Zusammenfassung der Seite"}}` erstellt eine Zusammenfassung des Webseiteninhalts.
- `{{"eine Zusammenfassung in drei Stichpunkten, übersetzt ins Französische"}}` extrahiert Stichpunkte zur Seite auf Französisch.
- `{{"un resumé de la page en trois points"}}` erstellt Stichpunkte zur Seite mittels französischer Aufforderung.

Die Ausgabe für deine Prompts kann mit Hilfe von [[Filter|Filtern]] weiter bearbeitet werden. Filter werden im Nachhinein auf die Ausgabe des Modells angewendet. `{{"eine Zusammenfassung"|blockquote}}` gibt z.B. die Zusammenfassung als Zitatblock aus.

## Erste Schritte

Interpreter funktioniert mit fast allen Sprachmodell-Anbietern, auch mit solchen, die deine Privatsphäre schützen.

So richtest du die Interpreter-Funktion ein:

1. Öffne die **Web Clipper-Einstellungen** → **Interpreter**.
2. Schalte **Interpreter aktivieren** ein.
3. Konfiguriere deine Anbieter und Modelle, siehe [[Webseiten interpretieren#Modelle|Modelle]].
4. Füge [[Variablen|Prompt-Variablen]] in deine [[Obsidian Web Clipper/Vorlagen|Vorlagen]] ein.
5. Wenn deine Vorlage Prompt-Variablen enthält, erscheint in der Fußzeile des Web Clipper-Dialogs automatisch der Abschnitt **Interpreter**, sobald du eine [[Webseiten speichern|Webseite erfassen]] möchtest. Klicke auf die **Interpreter**-Schaltfläche, damit die Prompt-Variablen verarbeitet werden.

## Funktionsweise

Wenn Interpreter aktiviert ist *und* deine Vorlage [[Variablen#Prompt-Variablen|Prompt-Variablen]] enthält, erscheint im Fenster der Browsererweiterung ein Abschnitt **Interpreter** über der Schaltfläche **Zu Obsidian hinzufügen**. Hier kannst du ein Modell auswählen und den Interpreter über die aktive Webseite laufen lassen.

Wenn du auf **interpretieren** klickst, sendet Interpreter den Seitenkontext mit samt den Prompts aus deiner Vorlage an das Sprachmodell, das du ausgewählt hast. In Abhängigkeit vom gewählten Anbieter ist dies entweder ein externer Aufruf oder ein lokaler Aufruf auf deinem Gerät. Das Modell wertet deine Prompts auf den Seitenkontext an und gibt ein Ergebnis zurück. Interpreter ersetzt dann deine Vorlagen-Variablen durch die Antwortdaten.

Der gesamte Vorgang kann zwischen einigen Millisekunden und mehr als 30 Sekunden dauern, je nach Modell und zu verarbeitender Datenmenge.

## Kontext

Der Begriff *Kontext* bezieht sich auf die Daten der Webseite, auf die Interpreter deine Prompts anwendet. Je weniger Kontext, umso schneller läuft die Interpreter-Funktion. 

Standardmäßig verwendet Interpreter den gesamten HTML-Inhalt einer Webseite als Kontext, was jedoch die Verarbeitungszeit beeinträchtigen und ressourcenintensiver sein kann als notwendig.

Du kannst das Standardverhalten in den **Erweiterten** Interpreter-Einstellungen überschreiben und den Kontext je [[Obsidian Web Clipper/Vorlagen|Vorlage]] definieren.

Für einen gezielteren Kontext, kannst du [[Variablen#Selektor-Variablen|Selektor-Variablen]] (oder andere Variablentypen) verwenden, um Seitenabschnitte zu interpretieren. Du kannst bspw. folgende Selektor-Variable im Interpreter-Kontext deiner Vorlage einfügen:

```
{{selectorHtml:#main}}
```

 Auf diese Weise verwendet Interpreter lediglich Inhalte aus dem `#main`-Element der Webseite, falls dieses existiert. [[Filter#HTML-Verarbeitung|HTML-Filter]] wie `remove_html`, `strip_tags` oder `strip_attr` können nützlich sein, um den Kontextumfang weiter zu reduzieren und damit die Verarbeitung zu beschleunigen.

## Modelle

> [!warning] Datenschutzhinweis
> Durch die Nutzung von Modellen eines Drittanbieters erklärst du dich mit dessen Nutzungsbedingungen und Datenschutzrichtlinien einverstanden. Interpreter sendet Anfragen direkt an den Anbieter, den du ausgewählt hast. Es werden keine Daten zu deinen Anfragen von Obsidian gesammelt oder gespeichert.

### Voreingestellte Anbieter

Interpreter enthält mehrere voreingestellte Anbieter. Um diese zu verwenden, benötigst du in den meisten Fällen einen API-Schlüssel, den du vom Anbieter erhältst, wenn du dich mit deinem dortigen Konto anmeldest. Zudem musst du entscheiden, welche Modelle du verwenden möchtest.

| Anbieter           | API-Schlüssel                                                | Modelle                                                                               |
| ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Anthropic          | [API-Schlüssel](https://console.anthropic.com/settings/keys) | [Modelle](https://docs.anthropic.com/en/docs/about-claude/models)                     |
| Azure&nbsp;OpenAI  | [API-Schlüssel](https://oai.azure.com/portal/)               | [Modelle](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models) |
| DeepSeek           | [API-Schlüssel](https://platform.deepseek.com/api_keys)      | [Modelle](https://api-docs.deepseek.com/quick_start/pricing)                          |
| Google&nbsp;Gemini | [API-Schlüssel](https://aistudio.google.com/apikey)          | [Modelle](https://ai.google.dev/gemini-api/docs/models/gemini)                        |
| Hugging Face       | [API-Schlüssel](https://huggingface.co/settings/tokens)      | [Modelle](https://huggingface.co/models?pipeline_tag=text-generation&sort=trending)   |
| Meta               | [API-Schlüssel](https://llama.developer.meta.com)            | [Modelle](https://llama.developer.meta.com/docs/models)                               |
| Ollama             | *ohne*                                                       | [Modelle](https://ollama.com/search)                                                  |
| OpenAI             | [API-Schlüssel](https://platform.openai.com/api-keys)        | [Modelle](https://platform.openai.com/docs/models)                                    |
| OpenRouter         | [API-Schlüssel](https://openrouter.ai/settings/keys)         | [Modelle](https://openrouter.ai/models)                                               |
| Perplexity         | [API-Schlüssel](https://www.perplexity.ai/settings/api)      | [Modelle](https://docs.perplexity.ai/guides/model-cards)                              |
| xAI Grok           | [API-Schlüssel](https://console.x.ai/team/default/api-keys)  | [Modelle](https://docs.x.ai/docs/models)                                              |

### Modell auswählen

Im Allgemeinen empfiehlt sich die Verwendung von kleineren Modellen mit Web Clipper, da diese schneller sind und für diese Aufgabe dennoch recht gute Ergebnisse liefern. Als kleine bis mittlere Modelle gelten bspw. **Anthropic's Claude Haiku**, **Google Gemini Flash**, **Llama** (mit 3B oder 8B Parametern)[^1] sowie die **Mini**-Modellreihe von OpenAI.

### Benutzerdefinierte Provider und Modelle

So fügst du deinen eigenen Anbieter bzw. dein eigenes Modell hinzu:

1. Öffne die **Web Clipper-Einstellungen** → **Interpreter**.
2. Wähle **+ Anbieter hinzufügen** im Abschnitt Anbieter.
	- Wähle einen vorgeschlagenen Anbieter aus der Auswahlliste **Anbieter** und gib ggf. deinen API-Schlüssel ein.
	- Oder wähle *Benutzerdefiniert* und konfiguriere Anbietername, Basis-URL und API-Schlüssel.
	- Bestätige mit **Speichern**.
3. Wähle **+ Modell hinzufügen** im Abschnitt Modelle.
	- Wähle einen zuvor konfigurierten Anbieter aus der Auswahlliste **Anbieter**.
	- Wähle ein vorgeschlagenes Modell aus der Liste.
	- Oder wähle *Benutzerdefiniert* und konfiguriere Modellname und -ID.
	- Bestätige mit **Speichern**.

Falls du einen benutzerdefinierten Anbieter hinzufügst, empfehlen wir, dessen Chat-Vervollständigungs-Endpunkt für die **Basis-URL** zu verwenden. Dieser endet in der Regel mit `/chat/completions`.

### Lokale Modelle

Interpreter läuft auch mit lokalen Modellen, die einen besseren Datenschutz bieten und auch im Offline-Betrieb verfügbar sind. Du hast verschiedene Möglichkeiten, lokale Modelle zu verwenden. Eine der einfachsten Optionen stellt Ollama dar.

#### Ollama

Mit [Ollama](https://ollama.com/) kannst du Sprachmodelle lokal und privat auf deinem Gerät ausführen.

Nachdem du Ollama heruntergeladen und installiert hast, kannst du es in den Interpreter-Einstellungen als **Anbieter hinzufügen**. Ollama benötigt keinen API-Schlüssel. Wähle dann ein Modell aus der [Modell-Liste](https://ollama.com/search). Wenn du bspw. [Llama 3.2](https://ollama.com/library/llama3.2) verwenden möchtest, wähle **Modell hinzufügen** und gib die folgenden Parameter ein:

- **Anbieter:** `Ollama`
- **Anzeigename:** `Llama 3.2` (gib einen Namen deiner Wahl ein).
- **Modell-ID:** `llama3.2` (Wert muss genau mit der Modell-ID von Ollama übereinstimmen).

**Starte den Ollama-Server**

Damit die Browsererweiterung mit Ollama interagieren kann, musst du beim Serverstart eine entsprechende [Anweisung](https://github.com/ollama/ollama/issues/2308) erteilen, andernfalls erscheint eine `403`-Fehlermeldung. 

Schließe Ollama und führe folgenden Befehl im Terminal aus. Das Protokoll muss auf das deines Browsers geändert werden, falls du nicht Chrome oder Firefox verwendest.

```
OLLAMA_ORIGINS=moz-extension://*,chrome-extension://*,safari-web-extension://* ollama serve
```

Führe dann dein Modell wie gewohnt mit Ollama aus, z.B.:

```
ollama run llama3.2
```

**Kontextlänge**

Das Kontextfenster von Ollama umfasst standardmäßig 2048 Token. Das ist die maximale Anzahl von Token für eine Nachricht und die Antwort. Beim Erfassen von langen Webseiten kann diese Grenze leicht überschritten werden. Ollama schlägt dann stillschweigend fehl und liefert unbrauchbare Ergebnisse.

Du hast folgende Möglichkeiten:

- Erhöhe den Parameter `num_ctx` für Ollama. Beachte, dass ein längerer Kontext auch mehr Speicher benötigt.
- Verwende das [[#Kontext]]-Feld in deiner Vorlage, um gezielter einen Ausschnitt der Webseite zu erfassen oder den Kontext mittels [[Filter|Filtern]] zu verkürzen, z.B. `{{content|slice:0,1000}}`.

[^1]: *3B Parameter* bedeutet, dass das Sprachmodell 3 Milliarden Parameter umfasst. Mit dieser Notation wird also der Umfang der gelernten "Schieberegler" eines KI-Modells angegeben.
