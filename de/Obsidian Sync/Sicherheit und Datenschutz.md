---
aliases:
  - Sicherheit/Datenschutz mit Obsidian Sync
  - Zugriffskontrolle für Obsidian Sync
description: Betrachtungen zu Sicherheit und Datenschutz für Obsidian Sync.
mobile: false
permalink: sync/sicherheit
publish: true
---

## Verschlüsselung

Zu deiner Sicherheit verschlüsselt [[Einführung in Obsidian Sync|Obsidian Sync]] deinen [[Lokale und Remote-Vaults|Remote-Vault]] sowie die gesamte Kommunikation mit den Obsidian-Servern.

Wenn du einen neuen Remote-Vault erstellst, hast du zwei Optionen zur Auswahl:

- **Ende-zu-Ende-Verschlüsselung (Standard)** bietet die stärkste Sicherheit, aber erfordert, dass du dein Verschlüsselungspasswort sicher aufbewahrst. Damit wird garantiert, dass niemand - nicht einmal das Obsidian-Team - auf deine Notizen zugreifen kann.
- **Standard-Verschlüsselung** verwendet einen von Obsidian verwalteten Schlüssel, um deine Daten während der Übertragung und auf unseren Servern zu schützen. 

Wir empfehlen allen Benutzern die Ende-zu-Ende-Verschlüsselung als privateste und sicherste Option. Beachte jedoch, dass deine Daten für immer verschlüsselt bleiben und unbrauchbar sind, falls du dein Verschlüsselungspasswort vergisst oder verlierst. Wir können dein Passwort oder die damit verschlüsselten Daten nicht für dich wiederherstellen.

Deine Wahl wirkt sich lediglich auf den Remote-Vault aus, deine lokalen Daten werden nicht verschlüsselt.

### Was bedeutet Ende-zu-Ende-Verschlüsselung?

Ende-zu-Ende-Verschlüsselung bedeutet, dass die Daten verschlüsselt sind ab dem Zeitpunkt, ab dem sie dein Gerät verlassen. Sie können nur mit deinem Verschlüsselungspasswort wieder entschlüsselt werden, sobald sie wieder auf einem deiner Geräte sind.

Wir können deine Daten nicht lesen. Auch potenzielle Lauscher, wie bspw. dein Internet-Anbieter, kann das nicht.

Auch im seltenen Fall eines Datendiebstahls bleiben deine Daten verschlüsselt - niemand kann deine Dateien entschlüsseln, ohne dein Verschlüsselungspasswort zu kennen.

### Was sind die Risiken einer Standard-Verschlüsselung?

Die Standard-Verschlüsselung ist grundsätzlich weniger sicher als die Ende-zu-Ende-Verschlüsselung, kann jedoch eine praktische Alternative bieten, wenn nicht davon auszugehen ist, dass die Daten, die du synchronisieren möchtest, privater Natur sind. Falls dein synchronisierter Vault bspw. auf einer öffentlichen Website [[Einführung in Obsidian Publish|veröffentlicht]] wird, wie diese Hilfeseite, dann ist eine Ende-zu-Ende-Verschlüsselung nicht notwendig.

Die Standard-Verschlüsselung verwendet dieselbe Verschlüsselungsmethode, wie sie von Cloudspeicher-Unternehmen und Software-as-a-Service-Plattformen, wie Google Docs, Dropbox, oder iCloud (ohne Advanced Data Protection), eingesetzt wird. Dein Schlüssel für die Verschlüsselung wird von der Anwendung generiert und verwendet, um deine Daten während der Übertragung und auf unserem Server zu schützen. Da der Schlüssel auf unseren Servern gespeichert wird, kann er zur Entschlüsselung deiner Daten verwendet werden, bspw. wenn unser Unternehmen einer Durchsuchungsanordnung unterliegt oder wenn du über einen Webbrowser auf deine Daten zugreifen möchtest.

Nur die Ende-zu-Ende-Verschlüsselung garantiert, dass Obsidian niemals auf deine Daten zugreifen kann und sollte immer verwendet werden, wenn deine Daten vollständig privat und sicher bleiben sollen.

### Welche Verschlüsselung verwendet Obsidian?

Für die Datensicherheit setzen wir auf Verschlüsselungsprotokolle nach Industriestandards. Konkret verwenden wir [AES-256](https://www.nist.gov/publications/advanced-encryption-standard-aes-0), den derzeit stärksten Verschlüsselungsstandard, der bspw. weit verbreitet im Online-Banking eingesetzt wird. Der Verschlüsselungsprozess umfasst folgende technische Details:

- **Schlüsselerzeugungsfunktion:** salted [scrypt](https://de.wikipedia.org/wiki/Scrypt)
- **Verschlüsselungsalgorithmus:** AES-256 unter Verwendung des [Galois/Counter Mode (GCM)](https://de.wikipedia.org/wiki/Galois/Counter_Mode)

### Kann ich überprüfen, ob meine Daten durchgehend verschlüsselt sind?

Ja. Erfahre mehr in unserem [Leitfaden zur Überprüfung der Ende-zu-Ende-Verschlüsselung](https://obsidian.md/blog/verify-obsidian-sync-encryption/). Hier findest du eine Schritt-für-Schritt-Anleitung, mit der du die Ende-zu-Ende-Verschlüsselung deiner Daten während der Übertragung über unsere Sync-Server vertrauenswürdig überprüfen kannst.

### Hat Obsidian ein externes Sicherheitsaudit durchlaufen?

Ja. Obsidian wurde unabhängig geprüft. Besuche unsere [Sicherheitsseite](https://obsidian.md/security), um die Prüfberichte einzusehen. Regelmäßige Audits durch externe Sicherheitsunternehmen gewährleisten, dass der Quellcode und die Verfahren von Obsidian den höchsten Sicherheitsstandards entsprechen.

### Was passiert, wenn ich mein Verschlüsselungspasswort vergesse?

Solltest du je dein Verschlüsselungspasswort vergessen oder verlieren, kannst du keine weiteren Vaults mit deinem Remote-Vault verbinden. Da dein Verschlüsselungspasswort nirgends gespeichert wird, ist es für immer verloren.

Deine Daten sollten jedoch in der Regel sicher lokal auf deinem Gerät gespeichert sein.

Um Obsidian Sync weiterhin zu verwenden, empfehlen wir, Sync vollständig neu zu konfigurieren, um weitere Geräte hinzufügen zu können:

1. Erstelle eine vollständige Sicherungskopie deines lokalen Vaults auf deinem primären Gerät (i.d.R. dein Computer), für den Fall, das etwas schief geht. Dazu kannst du einfach eine Kopie oder ZIP-Datei deines Vault-Ordners erstellen.
2. Trenne den Remote-Vault auf jedem deiner Geräte über die **Einstellungen → Sync → Remote-Vault → Trennen**.
3. Erstelle über die Sync-Einstellungen [[Obsidian Sync einrichten#Neuen Remote-Vault erstellen|einen neuen Remote-Vault]] auf deinem primären Gerät. Optional kannst du den alten Remote-Vault löschen, da du das Verschlüsselungspasswort dafür ohnehin nicht mehr besitzt. (Das Löschen des bisherigen Remote-Vaults ist unumgänglich, falls du das [[Häufig gestellte Fragen#Wie viele Remote-Vaults stehen mir zur Verfügung?|Vault-Limit]] erreicht hast.)
4. Warte bis die Synchronisierung auf deinem primären Gerät abgeschlossen ist. Beobachte die Synchronisierungsanzeige rechts unten bis ein grünes Häkchen angezeigt wird.
5. Verbinde jedes deiner Geräte mit diesem neu erstellten Remote-Vault. Bei der Verbindung wird eine Warnung über das Zusammenführen der Vaults angezeigt. Das ist normal und du kannst fortfahren. Warte bis die Synchronisierung auf jedem Gerät vollständig abgeschlossen ist, bevor du weiterarbeitest, um das Risiko von Problemen zu verringern.
6. Nun sollten alle deine Geräte mit dem neuen Remote-Vault verbunden sein.

## Hosting

### Wo werden Obsidian's Sync-Server gehostet?

Unsere Rechenzentren werden von [DigitalOcean](https://www.digitalocean.com) betrieben und bieten regionales Hosting für Remote-Vaults an folgenden Standorten:

> [!abstract] Sync-Regionen
> **Automatisch**: Dein Rechenzentrum wird anhand deines IP-Standortes bei der Ersteinrichtung ausgewählt.
> 
> **Asien**: Singapore
> **Europa**: Frankfurt, Deutschland
> **Nordamerika**: San Francisco, USA 
> **Ozeanien**: Sydney, Australien
^sync-geo-regions

### Wie finde ich meinen aktuellen Sync-Server und wo wird er gehostet?

So findest du deinen aktuellen Sync-Server:

1. Öffne die **Einstellungen** → **Sync** → **Debug-Informationen kopieren**.
2. Füge die kopierten Informationen in eine Notiz oder Textdatei ein.
3. Suche nach einer Zeile, die ungefähr so aussieht: `Host server: wss://sync-xx.obsidian.md`

Diese Zeile gibt den Server an, auf dem dein Remote-Vault gehostet wird. Mehr Informationen zu Serverstandorten und Serververfügbarkeit findest du auf unserer [Statusseite](https://status.obsidian.md/).

## Netzwerk und Zugang

### Zugriff auf Obsidian Sync in deinem Netzwerk verwalten

Um den Zugriff auf Obsidian Sync in deinem Netzwerk zu regulieren, musst du die folgenden Domänen verwalten:

`sync-xx.obsidian.md`

Das `xx` steht für eine Zahl zwischen `1` und `100`.

> [!tip] Falls deine Firewall dies unterstützt, empfehlen wir ein Whitelisting für `sync-*.obsidian.md`, um der kontinuierlichen Erweiterung unserer Subdomains Rechnung zu tragen.

## Einschränkungen

Obsidian Sync wurde entwickelt, um deine Notizen privat und sicher zu halten. Um eine schnelle, zuverlässige Synchronisierung sowie effiziente Speicherung über alle Geräte hinweg zu gewährleisten, gehen wir bei der Anwendung von Verschlüsselung bewusst einige Kompromisse ein.

## Deterministische Datei-Hash-Verschlüsselung

Wir verschlüsseln Datei-Hashes deterministisch: Derselbe Dateiinhalt, der denselben Verschlüsselungsschlüssel und Salt verwendet, erzeugt auf dem Server immer denselben verschlüsselten Hash. Das hilft Sync dabei, Duplikate zu erkennen und ein erneutes Hochladen oder Speichern identischer Daten zu vermeiden, was Bandbreite wie auch Speicherplatz spart, insbesondere im Versionsverlauf oder wenn sich große Dateien wiederholen.

Wenn jedoch ein Angreifer einen Sync-Server kompromittiert und über eine separate Möglichkeit verfügt, einen Anwender zum Hochladen von Dateien seiner Wahl zu zwingen, könnte der Angreifer den Anwender zwingen, bestimmte Dateien hochzuladen und feststellen, ob die Datei mit einer zuvor vom Anwender hochgeladenen Datei übereinstimmt.

### Keine kryptographische Verbindung zwischen Pfad und Inhalt

Einige Metadaten sind nicht Ende-zu-Ende-verschlüsselt: Von welchem Gerät eine Datei hochgeladen oder gelöscht wurde, wann sie hochgeladen wurde und die Zuordnung (*mapping*) zwischen verschlüsselten Dateipfaden und verschlüsseltem Inhalt. Diese Daten sind für den Server lesbar, damit Änderungen weitergeleitet, der Versionsverlauf einer Datei bestimmt und Geräte synchron gehalten werden können.

Wenn ein Sync-Server kompromittiert wurde, könnte ein Angreifer diese Zuordnung manipulieren und dafür sorgen, dass der Inhalt einer verschlüsselten Datei unter einem anderen Dateipfad bereitgestellt wird. Dadurch werden deine Klartext-Daten jedoch nicht offengelegt, sie bleiben verschlüsselt.