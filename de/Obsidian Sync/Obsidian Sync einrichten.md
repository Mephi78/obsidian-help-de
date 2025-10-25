---
aliases:
  - Obsidian Sync/Obsidian Sync auf einem anderen Gerät einrichten
cssclasses:
  - soft-embed
description: Erfahre, wie du Obsidian Sync einrichtest, um deine Notizen geräteübergreifend zu synchronisieren.
mobile: true
permalink: sync/einrichten
publish: true
---

Du hast ein Obsidian Sync-Abo erworben und stehst in den Startlöchern. Wir zeigen dir, wie du Obsidian Sync einrichtest und für deinen Alltag konfigurierst.

- **Obsidian Sync-Neuling?** Siehe [[#Erstmalige Einrichtung von Obsidian Sync]]
- **Zweites Gerät verbinden?** Siehe [[#Remote-Vault auf anderem Gerät synchronisieren]]
- **Änderungen notwendig?** Siehe [[#Remote-Vaults verwalten]]

## Erstmalige Einrichtung von Obsidian Sync

Zunächst werden wir einen neuen [[Lokale und Remote-Vaults|Remote-Vault]] erstellen und mit einem vorhandenen lokalen Vault verbinden. Du brauchst keinen neuen, leeren lokalen Vault erstellen, um Obsidian Sync zu verwenden.

> [!info] Wird dein aktueller Vault bereits mit iCloud, OneDrive, Dropbox oder einem vergleichbaren Dienst synchronisiert? Falls **ja** oder falls du **unsicher** bist, lies bitte die [[Frequently asked questions#Can I use a third-party sync with Obsidian Sync?|FAQ]] und [[Umstellung auf Obsidian Sync]], bevor du weitermachst.

### Voraussetzungen

- Ein Obsidian-Nutzerkonto. Falls du noch keines besitzt, [registriere dich jetzt](https://obsidian.md/auth?returnto=%2Faccount%2Fpublish#signup).
- Ein aktives Obsidian Sync-Abo. Falls du noch keines besitzt, erwirb ein Abo über [dein Obsidian-Nutzerkonto](https://obsidian.md/account/sync).
- **Empfohlen**: Einrichten eines [[Sichere deinen Vault|Backup-Systems]] für deine Obsidian-Dateien. Eine Synchronisierung ersetzt kein Backup.

### Obsidian-Konto anmelden

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Allgemein → Nutzerkonto** klicke neben **Dein Nutzerkonto** auf **Anmelden**.
3. Gib im Feld **E-Mail** deine Mailadresse ein.
4. Gib dein **Passwort** ein.
5. Bestätige mit **Anmelden**.

### Obsidian Sync aktivieren

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Wähle **Obsidian-Erweiterungen**.
3. Aktiviere **Sync**.

### Neuen Remote-Vault erstellen

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Obsidian-Erweiterungen** wähle **Sync**.
3. Neben **Remote-Vault** klicke **Wählen**.
4. Wähle **Neuen Vault erstellen**.
5. Gib in **Vault-Name** den Namen deines Remote-Vaults ein.
6. Wähle unter **Region** eine [[#Regionale Sync-Server|Server-Region]] für deinen Remote-Vault. 
7. Gib ein **Passwort für Verschlüsselung** ein. Damit wird ein durchgängig verschlüsselter Vault erstellt. Das Passwort ist unabhängig von deinem Obsidian-Nutzerkonto und kann für jeden deiner Vaults unterschiedlich sein. Für mehr Informationen siehe [[Obsidian Sync/Sicherheit und Datenschutz]].
8. Bestätige mit **Erstellen**.

### Remote-Vault verbinden

1. Neben deinem neu erstellten Vault wähle **Verbinden**.
2. Gib das **Passwort für Verschlüsselung** ein, falls du zuvor eins zugewiesen hast für die [[Obsidian Sync/Sicherheit und Datenschutz#Was bedeutet Ende-zu-Ende-Verschlüsselung?|Ende-zu-Ende-Verschlüsselung]].
3. Wähle **Vault entsperren**.
4. **Noch nicht synchronisieren.** Prüfe zunächst deine [[#Obsidian Sync konfigurieren|Sync-Einstellungen]].
    - Wenn du die Synchronisierung sofort starten möchtest, lies [[#Synchronisierung starten|hier]] weiter.
5. Schließe den Dialog, der dich zum **Ordner ausschließen** und **Synchronisierung starten** auffordert und fahre mit dem nächsten Schritt fort.

#### Obsidian Sync konfigurieren

1. Öffne **Einstellungen** → **Sync**.
2. Füge den **Namen des Gerätes** hinzu, falls noch nicht geschehen, um deine Logdateien leichter lesbar zu machen.
3. Entscheide, ob du eine **Selektive Synchronisierung** und die **Vault-Konfiguration synchronisieren** möchtest.
4. Wenn du die Sync-Einstellungen änderst, musst du Obsidian neu starten, damit die Änderungen greifen.
5. Gehe nach dem Neustart von Obsidian zurück in die **Sync**-Einstellungen.

#### Synchronisierung starten

Nach dem Verbinden mit einem Remote-Vault kannst du die Schaltfläche **Synchronisierung starten** betätigen, um die Synchronisierung zu starten.

Nach dem Ändern der Sync-Einstellungen und Neustart von Obsidian wird stattdessen die Schaltfläche **Fortfahren** angezeigt. Betätige diese, um die Synchronisierung zu starten.

> [!done] Status der Synchronisierung
> Sobald die Synchronisierung abgeschlossen ist, erscheint ein grüner Kreis mit Häkchen ( ![[obsidian-icon-sync-synced.svg#icon]] ) rechts unten in der ![[lucide-monitor-check.svg#icon]] Anwendung  bzw. in der rechten Seitenleiste der ![[obsidian-icon-smartphone.svg#icon]] App. Im Sync-Log erscheint die Meldung "Fully Synced".
>
> Für mehr Informationen zum Sync-Status siehe [[Status-Symbole und Benachrichtigungen]].
^obsidian-sync-status

Um weitere Geräte mit dem neu erstellten und synchronisierten Remote-Vault zu verbinden, fahre mit [[Obsidian Sync einrichten#Remote-Vault auf anderem Gerät synchronisieren|Remote-Vault auf anderem Gerät synchronisieren]] fort.

 Mehr Informationen zur Synchronisierung von Einstellungen und Dateien findest du im Abschnitt [[Konfiguration und selektive Synchronisierung]].

## Remote-Vault auf anderem Gerät synchronisieren

Wir gehen davon aus, dass du bereits einen [[#Neuen Remote-Vault erstellen|Remote-Vault erstellt]] und [[#Synchronisierung starten|Daten in diesen hochgeladen]] hast. Jetzt möchtest du deine anderen Geräte mit diesem Remote-Vault verbinden. 

### Synchronisieren über die Vault-Verwaltung

Wenn du eine neu installierte Obsidian-Instanz öffnest, erscheint die [[Vaults verwalten|Vault-Verwaltung]]. Um einen neuen lokalen Vault zu erstellen mit den Inhalten aus einem Remote-Vault, führe die folgenden Schritte aus.

1. In der **Vault-Verwaltung** wähle abhängig vom Gerät eine der folgenden Optionen:
	1. ![[lucide-monitor-check.svg#icon]] **Desktop**: Neben **Obsidian Sync verbinden**wähle **Anmelden**.
	2. ![[obsidian-icon-smartphone.svg#icon]] **Mobile/Tablet**: Wähle **Setup Obsidian Sync**.
2. Melde dich an deinem Obsidian-Konto an:
	1. Wenn du [[2-factor authentication|2FA]] aktiviert hast, gibt deinen 2FA-Code ein.
3. Du wirst aufgefordert, den Remote-Vault zu wählen, mit dem du dein Gerät synchronisieren möchtest. Wähle **Verbinden**.
4. Gib einen beliebigen Namen für den lokalen Vault ein, in dem die Daten aus dem Remote-Vault gespeichert werden sollen. Hinweis: Falls du [[Obsidian URI]]s verwendest, solltest du denselben Namen verwenden wie für den lokalen Vault auf dem anderen Gerät. 
5. Wähle **Erstellen**.
6. Das Fenster zum Löschen von Vaults wird kurz angezeigt, während Obsidian Sync eine Verbindung zum Server herstellt und dein Abo verifiziert. Anschließend wird der Dialog **Verbindung einrichten** angezeigt. 
	1. Wir empfehlen dringend, diesen Dialog zu schließen und zuerst die [[#Obsidian Sync konfigurieren|Sync-Einstellungen]] anzupassen.
	2. Denke daran, nach dem Ändern der Sync-Einstellungen Obsidian neu zu starten.

### Synchronisieren über die Obsidian-Einstellungen

Wenn du auf diesem Gerät bereits einen lokalen Vault erstellt hast und diesen mit einem Remote-Vault verbinden möchtest, sind die Schritte ähnlich wie bei der [[#Erstmalige Einrichtung von Obsidian Sync|erstmaligen Einrichtung von Obsidian Sync]].

![[Obsidian Sync einrichten#Obsidian-Konto anmelden]]

![[Obsidian Sync einrichten#Obsidian Sync aktivieren]]

#### Remote-Vault verbinden

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Obsidian-Erweiterungen** wähle **Sync**.
3. Neben **Remote-Vault** klicke **Wählen**.
4. Wähle **Verbinden** neben dem Remote-Vault, mit dem du den lokalen synchronisieren möchtest.
5. Gib das **Passwort für Verschlüsselung** ein, falls du zuvor eins zugewiesen hast.
6. Du wirst aufgefordert, die Synchronisierung zu starten. Es empfiehlt sich, zunächst die Sync-Einstellungen zu überprüfen und ggf. anzupassen. Falls du den gesamten Vault ohne Anpassungen synchronisieren möchtest, kannst du **Synchronisierung starten** betätigen. 

> [!warning] Wenn dein lokaler Vault bereits Notizen enthält (nicht empfohlen), erhältst du vor der Ausführung eine Warnmeldung, dass diese Notizen zusammengeführt werden. Konflikte werden nach [[Obsidian Sync/Fehlerbehandlung#Conflict resolution|Obsidian Sync's Konfliktlösungsregeln]] aufgelöst.

![[Obsidian Sync einrichten#Obsidian Sync konfigurieren]]

![[Obsidian Sync einrichten#Synchronisierung starten]]

## Remote-Vaults verwalten

Du  hast einen Remote-Vault erstellt und eine Verbindung dazu hergestellt. Möglicherweise hast du diesen auch mit mehreren Geräten synchronisiert. In diesem Abschnitt widmen wir uns der Frage, wie du deine Remote-Vaults verwalten kannst.

### Verbindung zu Remote-Vault trennen

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Obsidian-Erweiterungen** wähle **Sync**.
3. Klicke **Trennen** neben dem zu trennenden Remote-Vault.

Die Verbindung zum Remote-Vault wurde nun aufgehoben und dieses Gerät wird nicht länger synchronisiert.

### Remote-Vault löschen

> [!tip] Deleting a remote vault will not delete your local data on your device.

1. Öffne die **Einstellungen** ( ![[lucide-settings.svg#icon]] ).
2. Unter **Obsidian-Erweiterungen** wähle **Sync**.
3. Wähle **Verwalten** neben **Remote-Vault**. Es erscheint ein Dialog mit einer Liste deiner Remote-Vaults.
4. Wähle das Papierkorb-Symbol ( ![[lucide-trash-2.svg#icon]] ) neben dem Remote-Vault, den du löschen möchtest.
5. Bestätige die Sicherheitsabfrage mit **Löschen**.
6. Dein Remote-Vault wurde gelöscht.

> [!info] Wenn kein Papierkorb-Symbol sichtbar ist, musst du möglicherweise zunächst die Verbindung zum Remote-Vault trennen. Sobald die Verbindung getrennt ist, klicke **Wählen**, um die Liste der Remote-Vaults anzuzeigen.

### Regionale Sync-Server

Obsidian Sync lässt dich einen Standort für deinen Remote-Vault wählen. Falls du Obsidian `1.4.16` oder älter verwendest, wird die Region automatisch für dich ausgewählt.

Falls du unsicher bist, welche Region für deinen aktuellen Vault eingestellt ist, findest du in [[Obsidian Sync/Sicherheit und Datenschutz#Where can I find my current Sync server and where is it hosted?|Where can I find my current Sync server and where is it hosted?]] eine Anleitung.

![[sync-regional-sync-servers.png#interface|300]]

Nachdem du eine Region gewählt hast, kann dein Remote-Vault **nicht** auf einen anderen Server verschoben werden, ohne deine Daten erneut hochzuladen. Um die Region zu ändern, folge der [[Sync-Regionen|Anleitung für Sync-Regionen]].

![[Obsidian Sync/Sicherheit und Datenschutz#^sync-geo-regions]]

## Nächste Schritte

Nach der Einrichtung von Obsidian Sync möchtest du möglicherweise:

- Erkunden, wie du [[Konfiguration und selektive Synchronisierung|spezifische Dateien und die Einstellungen synchronisieren]] kannst.
- Erfahren, was passiert, wenn sich dein Remote-Vault [[Versionsverlauf|füllt]].
- Mit anderen Obsidian Sync-Nutzern gemeinsam an einem [[Zusammenarbeit in einem freigegebenen Vault|freigegebenen Vault]] arbeiten.
- Die [[Frequently asked questions|Sync FAQ]] nach Antworten auf häufig gestellte Fragen durchsuchen.
