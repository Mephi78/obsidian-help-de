---
permalink: installation
---

Obsidian ist für alle gängigen Desktop- und mobilen Plattformen erhältlich. Diese Möglichkeiten hast du, um Obsidian herunterzuladen und zu installieren.

## Installation unter Windows

1. Öffne [Download - Obsidian](https://obsidian.md/download) in deinem Browser.
2. Unter **Windows** klicke **Universal**, um die Installationsdatei herunterzuladen.
3. Öffne die Installationsdatei und folge den Anweisungen.
4. Öffne Obsidian, wie du auch jede andere Anwendung öffnen würdest.

## Installation unter macOS

1. Öffne [Download - Obsidian](https://obsidian.md/download) in deinem Browser.
2. Unter **Mac** klicke **Universal**, um die Installationsdatei herunterzuladen.
3. Öffne die Installationsdatei.
4. Im Fenster, das sich öffnet, ziehe Obsidian in den Programme-Ordner.
5. Öffne Obsidian, wie du auch jede andere Anwendung öffnen würdest.

## Installation unter Linux

Unter Linux hast du verschiedene Möglichkeiten zur Installation von Obsidian. Folge den Anweisungen für den von dir verwendeten Paket-Manager.

### Installation mit AppImage

1. Öffne [Download - Obsidian](https://obsidian.md/download) in deinem Browser.
2. Unter **Linux** klicke **AppImage**, um die Installationsdatei herunterzuladen.
3. Öffne ein Terminal und wechsle in das Verzeichnis mit der heruntergeladenen Installationsdatei.
4. Führe im Terminal den folgenden Befehl aus, um Obsidian zu öffnen:

   ```bash
   chmod u+x Obsidian-<version>.AppImage
   ./Obsidian-<version>.AppImage
   ```
Hinweis: Auf Chromebooks muss das `libnss3-dev` Paket installiert werden, andernfalls dürftest du die Fehlermeldung `error while loading shared libraries: libnss3.so: cannot open shared object file: No such file or directory` erhalten.

### Installation mit Flatpak

1. Öffne ein Terminal und führe den folgenden Befehl aus, um Obsidian zu installieren:

   ```bash
   flatpak install flathub md.obsidian.Obsidian
   ```

2. Öffne Obsidian anschließend mit diesem Befehl:

   ```bash
   flatpak run md.obsidian.Obsidian
   ```

### Installation mit Snap

1. Öffne [Download - Obsidian](https://obsidian.md/download) in deinem Browser.
2. Unter **Linux** klicke **Snap**, um die Installationsdatei herunterzuladen.
3. Öffne ein Terminal und wechsle in das Verzeichnis mit der heruntergeladenen Installationsdatei.
4. Um das Snap Paket zu installieren, führe im Terminal den folgenden Befehl aus (`--dangerous` ist erforderlich für die Installation von lokal heruntergeladenen Paketen ohne Signatur des Snap-Herstellers Canonical; `--classic` erlaubt Obsidian, deine Notizen auch außerhalb der Sandbox zu speichern):

   ```bash
   snap install obsidian_<version>_<arch>.snap --dangerous --classic
   ```

5. Öffne Obsidian, wie du auch jede andere Anwendung öffnen würdest.

## Installation auf Android

1. Finde Obsidian im [Google Play Store](https://play.google.com/store/apps/details?id=md.obsidian).
2. Tippe auf **Installieren**, um die App zu installieren.
3. Öffne Obsidian, wie du auch jede andere App öffnen würdest.

Optional kannst du das APK für Android auf der [Download - Obsidian](https://obsidian.md/download) Seite herunterladen.

## Installation auf iPhone oder iPad

1. Finde Obsidian im [App Store](https://apps.apple.com/us/app/obsidian-connected-notes/id1557175442).
2. Tippe **Laden**, um die App herunterzuladen.
3. Öffne Obsidian, wie du auch jede andere App öffnen würdest.
