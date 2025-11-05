---
description: Erfahre mehr über häufig auftretende Probleme bei der Verwendung von Obsidian Publish.
mobile: true
publish: true
permalink: publish/fehlerbehandlung
---

Hier findest du Lösungsvorschläge für bekannte Probleme, die bei der Verwendung von [[Einführung in Obsidian Publish|Obsidian Publish]] auftreten können.

Lies bitte zuerst die Abschnitte [[Mediendateien]] und [[Beschränkungen]].

## Allgemeines

Sollte es beim Veröffentlichen zu Fehlern kommen, kann es hilfreich sein, zur Fehleranalyse von dir verwendete [[Externe Erweiterungen]] nacheinander zu deaktivieren.

## Veröffentlichen von Notizen

**Ich erhalte einen Hash-Fehler, wenn ich versuche, eine Notiz zu veröffentlichen.**

Verwendest du ein [[Externe Erweiterungen|Community-Plugin]], dass den Zeitstempel für die letzte Bearbeitung bei der Aktualisierung ändert? Falls ja, könnte es sein, dass die Verwendung dieser Erweiterung zu Konflikten mit Obsidian Publish führt. Bitte melde den Fehler an den Plugin-Entwickler, um das Problem zu beheben.

**Ich erhalte einen seltsamen Netzwerkfehler und habe eine sehr große Publish-Webseite.**

Vermutlich müssen wir deine Datenbank prüfen. Bitte kontaktiere den [[Hilfe und Kontakt#Obsidian Support kontaktieren|Obsidian Support]], damit wir dir helfen können.

## CSS und Themen

**Warum wird das CSS aus meinem [[Konfigurationsordner]] nicht auf die veröffentlichte Webseite angewendet?**

Obsidian Publish berücksichtigt deinen Konfigurationsordner nicht. Erstelle stattdessen eine Datei `publish.css` im Wurzelverzeichnis des Vaults, den du veröffentlichen möchtest. Erfahre mehr dazu im Abschnitt [[Webseite individualisieren]].

**Warum sieht mein CSS auf der Publish-Webseite nicht genauso aus wie in der Anwendung?**

CSS in Obsidian Publish ist nicht genau dasselbe wie in der Anwendung. Wir empfehlen [CSS und Themen speziell für Publish](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/About+Obsidian+Publish+themes) von Grund auf neu zu entwickeln.

Im Allgemeinen gilt jedoch, was in der [[Ansichten und Modi#Leseansicht|Leseansicht]] funktioniert, funktioniert mit hoher Wahrscheinlichkeit auch in Obsidian Publish.

