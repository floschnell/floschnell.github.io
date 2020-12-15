---
layout: page
title: TrainerJS
permalink: /projekte/trainerjs/
category: Projekte
---

## Motivation

Tacx ist ein großer Hersteller von Radtrainern, welcher kürzlich von Garmin aufgekauft wurde. Zur gleichen Zeit wurde eine neue Version der Tacx Software angekündigt, mit welcher man die Unterstützung von alten Radtrainern einstellte. Gleichzeitig gab Tacx bekannt, dass die alte Softwareversion nicht mehr bezogen/genutzt werden könne.

Da ich noch einen alten Tacx Bushido (t1980) besitze und gerade während der Winterzeit diesen gerne benutze, um die Beine fit zu halten, hat mich diese Nachricht traurig gestimmt. Schließlich ist es auch so, dass diese Version des Bushido noch nicht mit dem standardisierten ANT+ Protokoll gesteuert wird, sondern mit einem proprietären Vorgänger. Das hat zur Folge, dass auch populäre Software wie bspw. Zwift den Trainer nicht unterstützen.

Nach der Ankündigung von Tacx, die Unterstützung der alten Trainer an den Nagel zu hängen, habe ich mich auf die Suche gemacht, vielleicht doch etwas über dieses "legacy" ANT Protokoll in Erfahrung zu bringen. Tatsächlich wurde ich auf [den Wiki Seiten des Cyclismo Projekts fündig](https://github.com/fluxoid-org/CyclismoProject/wiki/Tacx-Bushido-Headunit-protocol). Zu der Dokumentation fand ich auch noch passenden Python Code, allerdings war alles schon sehr angestaubt. Abhängigkeiten machten mir zu schaffen und auch die ANT Bibliotheken waren nur geforked und ziemlich "quick & dirty" angepasst worden.

Letztendlich entschied ich mich, eine Webanwendung zu schreiben, mit welcher ich meine im Sommer aufgezeichneten GPX Routen auf dem Radtrainer nachfahren könnte.

## Umsetzung

Zuerst begann ich damit, einen WebUSB Treiber für meinen Cycplus ANT+ Dongle zu schreiben. Dabei stützte ich mich auf eine [bereits existierende Python Bibliothek](https://github.com/half2me/libant). Darauf aufbauend setzte ich das "legacy" ANT Protokoll nach der Dokumentation aus dem Cyclismo Projekt. Tatsächlich konnte ich nun über Chrome und meinen USB Dongle mit dem Radtrainer kommunizieren. Ich empfing Daten zu Distanz, Geschwindigkeit, Leistung und konnte im Rückkanal die aktuelle Steigung an den Trainer senden. Sobald dies möglich war, setzte ich eine Simulationsanwendung auf den Kommunikationscode. Die Simulation kommuniziert über eine einheitliche Schnittstelle mit dem Trainer und so ist es in Zukunft auch leicht möglich, Unterstützung für weitere Trainer hinzuzufügen. Die Strecken und die aktuelle Position des Fahrers werden mit CesiumJS (so etwa das Google Earth für den Browser) visualisiert.

## Ergebnis

Den aktuellen Stand des Projekts findet ihr [im TrainerJS GitHub Repo](https://www.github.com/floschnell/trainerjs). Zu den mittlerweile eingebauten Features zählen:
- Laden von GPX Routen und Aufbereitung der Daten für den Radtrainer
- Einstellung der Steigung am Radtrainer, je nach Position auf der Route
- Verbindung eines ANT+ Pulsmessgerätes
- Aufzeichnung der Geschwindigkeit und Leistungsdaten während der Fahrt und Visualisierung in einem Graphen am unteren Bildschirmrand
- Export der Aufzeichnungen als neue GPX Datei zum Import bei Fitness Portalen wie Strava

[In diesem kurzen Youtube Video](https://www.youtube.com/watch?v=jJdXFX-7fDQ&feature=youtu.be) könnt ihr sehen, was euch nach dem öffnen der Webanwendung im Browser (hier Chrome) erwartet.

<center>
<figure style="max-width:500px" markdown="1">
![test](https://raw.githubusercontent.com/floschnell/trainerjs/main/demo.gif)
<figcaption>Ein kleiner Ausschnitt einer meiner Ausfahrten am Gardasee (in der Ferne sieht man den Lago di Tenno ❤️).</figcaption>
</figure>
</center>