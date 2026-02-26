---
permalink: teams/sicherheit
---

Auf unserer [Sicherheitsseite](https://obsidian.md/security) findest du Informationen darüber, welche Ansätze Obsidian zum Schutz deiner Daten verfolgt. Dort findest du auch die Auswertungen von Sicherheitsaudits, die von unabhängigen Dritten durchgeführt wurden.

## Überlegungen

Obsidian ist als Standalone-Anwendung konzipiert, die offline funktioniert. Die Anwendung unterstützt auch benutzerdefinierte Erweiterungen und Designs. Darüber hinaus bieten wir offizielle und inoffizielle Unterstützung für verschiedene Synchronisierungsdienste.

Wenn du keine externen Erweiterungen, Designs, [[Einführung in Obsidian Sync|Obsidian Sync]] oder [[Einführung in Obsidian Publish|Obsidian Publish]] verwendest, greifen deine Standardverfahren zur Sicherung von Anwendungen. Falls du jedoch eine dieser Funktionen einsetzen möchtest, empfehlen wir eine gründliche Prüfung deren Eignung für deinen Arbeitsplatz.

## Community-Plugins und Themen

[[Externe Erweiterungen|Community-Plugins]] und [[Themen]], die über unser Release-Repository eingereicht werden, durchlaufen einen Prüfprozess. Erfahre mehr zu diesem Thema im Abschnitt [[Plugin-Sicherheit]]. 

Für [[CSS-Bausteine]] gibt es jedoch keinen Community Store. Diese Dateien werden in der Regel über die [Obsidian Community](https://obsidian.md/community) und öffentliche GitHub Repositories bezogen und nicht durch uns geprüft.

Obsidian verlangt die Bündelung von Assets in CSS-Bausteinen und Themen. Eine Ausnahme bilden die [Google Fonts](https://fonts.google.com/), um die Leistung auf Mobilgeräten aufrechtzuerhalten, wo die Auswirkungen des Asset Bundling stärker spürbar sind.

## Netzwerk und Zugriff

Obwohl wir zunächst den lokalen Ansatz priorisieren, führt Obsidian in Abhängigkeit der von dir verwendeten Dienste und Funktionen auch Netzwerkaufrufe durch. Diese Netzwerkverbindungen kannst du über eine Domänen-Firewall oder eine Anwendungs-Sperre deaktivieren.

Obsidian baut Netzwerkverbindungen über den HTTPS Port 443 auf.

Nachfolgend werden Netzwerkverbindungen aufgelistet, die Obsidian verwendet.

### Verbindungen zu Obsidian

- **Early-Access-Aktualisierungen**: Verwendet `releases.obsidian.md`.
- **Konto- und Lizenzverwaltung**: Wenn du über die Einstellungen auf deinen Obsidian-Account zugreifst und eine Kommerzielle Lizenz aktivierst, wird `api.obsidian.md` aufgerufen.
- **Obsidian Sync**: Zur geräteübergreifenden Synchronisierung deiner Notizen.
	- Ruft `sync-xx.obsidian.md` auf, `xx` ist eine Zahl zwischen 01 und 100.
- **Obsidian Publish**: Zum Veröffentlichen deiner Notizen.
    1. Backend: `publish-main.obsidian.md` und `publish-xx.obsidian.md`, `xx` ist eine Zahl.
    2. Frontend: `publish.obsidian.md`.

### Verbindungen zu GitHub

Obsidian sendet Netzwerkanfragen an `github.com` und `raw.githubusercontent.com`.

- **Öffentliche Releases**: Wenn automatische Aktualsisierungen aktiviert sind, überprüft Obsidian GitHub auf öffentliche Releases.
- **Themen und Plugins von Drittanbietern**:
    - Alle 12 Stunden nach dem Start der Anwendung prüft Obsidian eine auf GitHub gehostete Datei danach, ob du "veraltete Plugins" installiert hast. Diese Funktion hilft, um bestimmte Versionen von Plugins, die nach aktuellem Wissensstand Fehlfunktionen verursachen, eine potenzielle Gefährdung oder ein Sicherheitsrisiko darstellen, aus der Ferne zu deaktivieren.
    - Aktivierte Plugins können zudem Netzwerkverkehr außerhalb der Kontrolle von Obsidian oder GitHub generieren.

### Weitere Verbindungen

- **Eingebettete Online-Inhalte**: Beim Öffnen von Notizen mit eingebetteten Online-Inhalten, wie bspw. Bilder (`![cat](https://upload.wikimedia.org/wikipedia/commons/0/0b/Cat_poster_1.jpg)`).
- **DNS-Anfragen**: Wenn ein Hostname vor dem Herstellen einer Verbindung aufgelöst werden muss, einschließlich DNS über HTTPS. Siehe [Chromium-Dokumentation](https://source.chromium.org/chromium/chromium/src/+/main:net/dns/public/doh_provider_entry.cc;l=120?q=chrome.cloudflare-dns.com&ss=chromium).

## Häufig gestellte Fragen

### Kontosicherheit

**Unterstützt Obsidian Single Sign-On (SSO)?**
Obsidian bietet keine SSO-Unterstützung. In den meisten Fällen musst du dich zur Arbeit mit Obsidian nicht anmelden, lediglich bei der Verwendung von [[Einführung in Obsidian Publish|Obsidian Publish]] oder [[Einführung in Obsidian Sync|Obsidian Sync]].

**Unterstützt Obsidian die Multi-Faktor-Authentifizierung (MFA)?**
Obsidian unterstützt die [[2-Faktor-Authentifizierung|2-Faktor-Authentifizierung]] (2FA) für Obsidian-Benutzerkonten, jedoch nicht für das Öffnen und Verwenden der Basis-Anwendung. Wenn du [[Einführung in Obsidian Sync|Obsidian Sync]] oder [[Einführung in Obsidian Publish|Obsidian Publish]] verwendest und 2FA aktiviert hast, wirst du beim erstmaligen Anmelden in der Anwendung zur Eingabe deines 2FA-Schlüssels aufgefordert.

### Bewertungen und Zertifizierungen

**Akzeptiert ihr Security Assessments durch unser Unternehmen?**
Wir verlangen einen Mindestbestellwert, bevor wir die Teilnahme an einer Sicherheitsbewertung in Betracht ziehen. Diese Assessments sind oft zeitaufwendig und möglicherweise nicht auf Offline-Anwendungen wie Obsidian anwendbar, da sie in der Regel auf cloudbasierte Dienste ausgerichtet sind.

Du kannst den Mindestbestellwert umgehen, indem du dich zu einer Vorauszahlung verpflichtest. Wende dich gern an den [[Hilfe und Kontakt#Obsidian Support kontaktieren|Obsidian Support]], um dich über diese Option zu informieren.

**Verfügt ihr über anerkannte Zertifizierungen in Bezug auf Informationssicherheit oder Qualitätsstandards wie ISO27001, NIST, COBIT oder andere ISO bzw. CSA Zertifizierungen?**
Derzeit nicht. Möglicherweise werden wir dies in Zukunft in Betracht ziehen, aktuell liegt unser Fokus jedoch auf [Sicherheitsaudits](https://obsidian.md/security).
