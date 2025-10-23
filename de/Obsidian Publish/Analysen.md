---
aliases:
  - Obsidian Publish/Google Analytics konfigurieren
permalink: publish/analytics
publish: true
---

## Voraussetzungen

Um Analysen auf deiner [[Einführung in Obsidian Publish|Obsidian Publish]]-Webseite zu verwenden, benötigst du eine [[Eigene Domain|eigene Domain]].

> [!important] Wichtig
> Vergewissere dich vor der Aktivierung von Analysen, dass die für dich geltenden Gesetze und Vorschriften eine Nachverfolgung deiner Besucher erlauben. Je nach dem von dir verwendeten Tool musst du deiner Webseite möglicherweise ein Einwilligungs-Banner hinzufügen.

## Google Analytics

Um Google Analytics für deine Obsidian Publish-Webseite zu aktivieren:

1. In der Werkzeugleiste am linken Rand wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. Gib unter **Google Analytics Tracking-Code** deinen Tracking-Code ein.

Um den Google Tag Manager anstelle von Google Analytics zu verwenden, erstelle deinen eigenen JavaScript-Code.

## Plausible, Fathom und andere Analysedienste

Du kannst die meisten Analysedienste über die Datei [[Webseite individualisieren|publish.js]] in deine Webseite einbinden. Ersetze dafür `yourdomain.com` durch deine eigene Domain und `src` mit dem entsprechenden Script des von dir verwendeten Analysedienstes.

Beispiel für [Plausible Analytics](https://plausible.io/):

```js
var analyticsScript = document.createElement('script');
analyticsScript.defer = true;
analyticsScript.setAttribute('data-domain', 'yourdomain.com');
analyticsScript.src = 'https://plausible.io/js/plausible.js';
document.head.appendChild(analyticsScript);
```

Auf dieselbe Weise kannst du [Fathom Analytics](https://usefathom.com/) einbinden. Beachte die Änderung von `data-domain` nach `data-site` — unterschiedliche Analyse-Anbieter verwenden möglicherweise eine abweichende Syntax für ihre Scripte.

```javascript
var fathom = analyticsScript.createElement('script');
analyticsScript.defer = true;
analyticsScript.setAttribute('data-site', 'yourdomain.com');
analyticsScript.src = 'https://cdn.usefathom.com/script.js';
document.head.appendChild(analyticsScript);
```

## Fehlerbehandlung

Um zu prüfen, ob deine Webseite deinen Analysedienst verwendet, deaktiviere alle Werbeblocker-Browser-Erweiterungen, wie z.B. uBlock Origin, die eine Ausführung von Tracking-Scripten verhindern könnten.