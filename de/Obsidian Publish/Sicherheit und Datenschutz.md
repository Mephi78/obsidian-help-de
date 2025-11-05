---
aliases:
  - Zugriffskontrolle für Obsidian Publish
  - Sicherheit/Datenschutz in Obsidian Publish
permalink: publish/sicherheit
publish: true
---

Du entscheidest, welche deiner Notizen auf deiner [[Einführung in Obsidian Publish|Obsidian Publish]]-Webseite veröffentlicht werden. Der Rest deiner Notizen verbleibt sicher in deinem lokalen Vault.

Nur veröffentlichte Notizen werden an die Obsidian-Server gesendet. Notizen, die du entpublizierst, werden auch vom Obsidian-Server gelöscht.

## Passwortschutz

Für eine verbesserte Zugriffskontrolle auf deine Publish-Webseite kannst du ein Webseiten-Passwort einrichten. Besucher werden dann beim Zugriff auf deine Webseite zur Passworteingabe aufgefordert. Sobald du das Passwort entfernst, wird die gesamte Webseite wieder für die Öffentlichkeit sichtbar.

> [!warning] Ein gezielter Passwortschutz für einzelne veröffentlichte Notizen wird derzeit nicht unterstützt.

### Webseiten-Passwort hinzufügen

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. Unter **Sonstige Seiteneinstellungen** klicke neben **Passwörter** auf **Verwalten**.
4. Wähle **Neues Passwort**.
5. Gib ein **Passwort** für deine Webseite ein.
6. (Optional) Gib in **Spitzname** einen Namen ein, z.B. den der Person, der du den Zugriff auf deine Webseite geben möchtest.
7. Bestätige mit **Dieses Passwort hinzufügen**.

### Webseiten-Passwort entfernen

1. [[Obsidian Publish einrichten#Obsidian Publish öffnen|Öffne den Publish-Dialog]].
2. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
3. Unter **Sonstige Seiteneinstellungen** klicke neben **Passwörter** auf **Verwalten**.
4. Neben dem Passwort, das du entfernen möchtest, klicke auf **Entfernen** ( ![[lucide-x.svg#icon]] ).

## Datensammlung
### Besucherdaten

Standardmäßig sammelt Obsidian Publish **keine** Besucherdaten, speichert keine Cookies und verarbeitet keine persönlichen Informationen. Du kannst jedoch Analytics verwenden oder mit  [[Webseite individualisieren|eigenen Scripten]] Benutzerdaten sammeln.

Als Eigentümer der Webseite bist du selbst verantwortlich, die in deiner Region geltenden Datenschutzverordnungen (z.B. DSGVO) einzuhalten. Dazu gehört die Bereitstellung von Besucherbenachrichtigungen und Zustimmungsdialogen mit Hilfe der `publish.js` und die Bereitstellung von Datenschutzbestimmungen auf deiner Webseite.

## Zugang

Obsidian hält einen Vertrag mit [Cloudflare](https://www.cloudflare.com) für die Bereitstellung unserer Publish-Webseiten. Die Server werden in San Francisco, Kalifornien gehostet.

### Zugriff auf Obsidian Publish in deinem Netzwerk verwalten

Um den Zugang zu Obsidian Publish in deinem Netzwerk zu regeln, musst du folgende Domains verwalten:

- Frontend: `publish.obsidian.md`
- Backend: `publish-main.obsidian.md`

Darüber hinaus verwenden die Backend-Dienste folgende Subdomains: `publish-xx.obsidian.md`, wobei `xx` eine Zahl von `1` bis `100` sein kann.

> [!tip] Falls deine Firewall dies unterstützt, empfehlen wir ein Whitelisting für `publish-*.obsidian.md`, um der kontinuierlichen Erweiterung unserer Subdomains Rechnung zu tragen.
