---
aliases:
  - 2FA
  - Wiederherstellungs-Codes
permalink: 2fa
---

Wenn du ein [Obsidian-Nutzerkonto](https://obsidian.md/account) hast, kannst du die 2-Faktor-Authentifizierung (2FA) aktivieren, um dein Konto mit einem zweiten Verifizierungsschritt zu schützen.

## 2FA aktivieren

- Melde dich über den Webbrowser in deinem [Obsidian-Nutzerkonto](https://obsidian.md/account/profile) an.
- Gehe in den Abschnitt **Profile** zu **2-factor authentication** und wähle **Enable**.
- Es erscheint ein Popup-Fenster, in dem du aufgefordert wirst, eine Authenticator-App mittels **QR code** oder **setup key** zu verbinden.

> [!hint]- Beliebte Authentifizierungs-Apps
> - [Authy](https://authy.com)
> - [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2)
> - [Microsoft Authenticator](https://www.microsoft.com/de-de/security/mobile-authenticator-app)
> - [iCloud Keychain](https://support.apple.com/de-de/guide/iphone/ipha6173c19f/ios)

- Sobald die Verbindung hergestellt ist, erhältst du von der Authenticator-App einen sechsstelligen Code, den du unter dem Abschnitt **QR code/setup key** in Schritt 3 einfügen musst.
- Gib abschließend dein aktuelles Passwort ein.
- Wähle **Complete set up**, um die Einrichtung abzuschließen.
- Das Popup-Fenster wird durch einen Bestätigungsdialog mit deinen Wiederherstellungs-Codes ersetzt. **Bitte bewahre deine Wiederherstellungs-Codes an einem sicheren Ort auf, da du diese zum Entsperren deines Kontos benötigst!**

Deine 2-Faktor-Authentifizierung ist nun eingerichtet.

> [!warning]- Sicherungskopien von QR code/setup key
> Wenn du zusätzlich zu deinen Wiederherstellungs-Codes eine Sicherungskopie von deinem **QR code** oder **Setup key** aufbewahren möchtest, empfehlen wir dringend, diese in einem passwortgeschützten System zu speichern.

## Wiederherstellungscode generieren

Falls du 2FA aktiviert hast, bevor Wiederherstellungs-Codes verfügbar waren oder wenn du diese neu generieren möchtest, führe die folgenden Schritte aus:

- Melde dich über den Webbrowser in deinem [Obsidian-Nutzerkonto](https://obsidian.md/account/profile) an.
- Wähle neben **2-factor authentication** die Option **Refresh recovery codes**.
- Gib im Popup-Fenster dein **Passwort** und den sechsstelligen **Authentifizierungscode** ein.
- Es erscheint ein Bestätigungsdialog mit deinen Wiederherstellungs-Codes. Du hast zwei Optionen:
    - **Copy recovery codes**: Kopiere die Wiederherstellungs-Codes, um sie an anderer Stelle einzufügen.
    - **Download recovery codes**: Lade eine Datei `obsidian-recovery-codes.txt` mit deinen Wiederherstellungs-Codes herunter.
- Schließe das Fenster über die Schaltfläche **Got it**.

Du kannst einen Wiederherstellungs-Code **einmalig** anstelle des sechsstelligen **Authentifizierungscodes** verwenden. Du kannst deine Wiederherstellungs-Codes jederzeit erneut generieren.

## 2FA deaktivieren

- Melde dich über den Webbrowser in deinem [Obsidian-Nutzerkonto](https://obsidian.md/account/profile) an.
- Gehe in den Abschnitt **Profile** zu **2-factor authentication** und wähle **Disable**.
- Gib dein Obsidian-Passwort ein.
- Gib den sechsstelligen **Authentifizierungscode** ein.
- Wägle **Disable 2FA**.
- Du wirst zurück zur Kontoverwaltung geleitet.

Die Einstellung **2-factor authentication** wird nun wieder die Schaltfläche **Enable** anzeigen, woran du erkennst, dass 2FA deaktiviert wurde.

## Häufig gestellte Fragen

**Ich habe 2FA aktiviert. Werde ich von meinen aktuellen Obsidian-Sitzungen abgemeldet?**
Nein. Die 2FA-Aktivierung führt im Sinne der Benutzerfreundlichkeit nicht dazu, dass du überall abgemeldet wirst. Bei Bedarf kannst du dies manuell über deine Konto-Seite tun und dich anschließend auf allen Geräten erneut anmelden.

**Ich habe 2FA aktiviert und wieder deaktiviert. Ich möchte es gern neu einrichten. Kann ich den ursprünglichen QR-Code oder Setup key verwenden?**
Nein. Du erhältst von deiner Authenticator-App einen neuen **QR-Code** und **Setup key** jedes Mal, wenn du die 2FA-Einrichtung neu startest.

**Ich habe 2FA aktiviert. Nach mehreren Anmeldeversuchen wurde ich jedoch noch nicht danach gefragt - funktioniert es?**
Möglicherweise lässt dein Browser-Cache es so aussehen, als würdest du Änderungen an der Seite vornehmen (z.B. dich an- oder abmelden), obwohl du eigentlich auf zwischengespeicherte Daten zugreifst. Versuche, dich über ein privates Browserfenster anzumelden, um zu überprüfen, ob die 2FA-Einrichtung erfolgreich war.

Wenn dieses Verhalten weiterhin auftritt, reiche bitte einen [Fehlerbericht](https://forum.obsidian.md/c/bug-reports/7) ein.

**Ich habe meine Wiederherstellungs-Codes, Authenticator und alles, was ich zur Anmeldung benötige, verloren. Was kann ich tun?**

Wenn du deine Wiederherstellungs-Codes und deinen Authenticator verloren hast, schreibe bitte eine Mail an [support@obsidian.md](mailto:support@obsidian.md?subject=I%20lost%20my%202FA), damit wir dir helfen können, wieder Zugriff auf dein Nutzerkonto zu erhalten.
