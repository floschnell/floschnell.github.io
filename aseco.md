---
layout: page
title: ASECO
permalink: /projekte/aseco/
category: Projekte
---

## Über Trackmania

Trackmania ist wohl das Spiel, welches ich in meiner Schulzeit am meisten gespielt habe. Das interessante an Trackmania ist, dass es einen Editor beinhaltet, mit welchem man eigene Strecken erstellen und auf diesen dann über das Internet gegen andere Spieler antreten kann. Ich kann mich noch gut daran erinnern, wie ich eine Demo Version des Spiels in einer Zeitschrift entdeckte. Mir gefiel besonders die Kombination an Kreativität und Geschicklichkeit, welche von einem gefordert werden. Zu dieser Zeit modifizierte ich gerne Spiele, da man dadurch ein großes Publikum erreichen konnte und meist nur kleine Veränderungen in der Spielmechanik zu einem ganz neuen Spielgefühl führen konnten.

## Die Anfänge

Es kam die Zeit, als die Entwickler von Trackmania eine XML-RPC Schnittstelle zu ihrer Dedicated Server Software hinzufügten. Dadurch konnten Drittanbieter (oder eben die Spieler) auf den aktuellen Spielstatus zugreifen oder auch den Spielverlauf beeinflussen. Da ich mich in meiner Freizeit auch viel mit der Entwicklung von Webseiten beschäftigte, kannte ich mich gut mit PHP aus. Ich begann also mit sehr einfachen Skripten und spielte mit der API, bis ich die Idee bekam, dass man doch die besten Rennzeiten aufzeichnen und über alle Server hinweg vergleichen/synchonisieren könne. Da Spieler eigene Strecken erstellen und mit anderen teilen konnten, gab es sehr viele Strecken und aber keine Informationen darüber, wer bereits wie schnell das Ziel erreicht hatte.

## FAST

Zu Beginn lief die Dedicated Server Software zusammen mit dem Skript zur Aufzeichnung der Bestzeiten auf meinem lokalen Computer. Ich war überrascht, wie populär mein Server in kürzester Zeit wurde und so stand mein Rechner ständig unter Last. Mir war klar, dass andere Spieler bessere Resourcen als ich hatten und so gab ich meinem Tool einen Namen (FAST) und verteilte es über Foren, MSN und ICQ (!). Bald begannen andere Spieler meine Entwicklung durch das Melden von Fehlern, Ideen oder gar durch Erweiterungen zu unterstützen. Zurückblickend war das wohl mein erster Kontakt mit *Open Source Software*. Zuerst schloss ich mich mit einem Franzosen namens "Slig" zusammen. Eine Zeit entwickelten wir zusammen, bis der Zeitpunkt kam, an dem Nadeo (die Entwickler von Trackmania) einen Teil ihrer Schnittstelle änderten. Deshalb und auch weil die Software schnell gewachsen war, entschied ich mich dazu die Anwendung komplett neu zu schreiben. Slig wollte unseren Fortschritt nicht verwerfen und entwickelte weiter an einer zweiten (... dritten und vierten) Version von FAST.

<figure markdown="1">
<img alt="Servercontroller History" src="/img/aseco/servercontroller-timeline.jpg">
<figcaption>Die <a target="blank" href="http://doc.maniaplanet.com/dedicated-server/tools/">online Dokumentation von ManiaPlanet</a> enthält eine schöne Grafik, welche zeigt, wie sich die verschiedenen Programme entwickelt haben.</figcaption>
</figure>

## ASECO

Als ich das Tool neu geschrieben hatte, nannte ich es ASECO (um eine Verwechslung mit seinem Vorgägner zu vermeiden) und begann erneut es in Foren anzubieten. Da Spieler bereits zuvor Erweiterungen für FAST geschrieben hatten, integrierte ich von Beginn an ein Plugin-System, welches es anderen Entwicklern leichter machte, eigene Funktionen einzubinden. Ein Autor der größten Erweiterung "RASP" hieß "AssemblerManiac". Da AssemblerManiac immer öfter nach neuen Integrationsmöglichkeiten fragte, tauschten wir uns viel aus und entwickelten bald gemeinsam an neuen Versionen.

## ManiaLive

Da ich während meines Studiums ein Semester im Ausland verbringen wollte, schickte ich auch Bewerbungen an einige Spielefirmen. Natürlich fragte ich auch bei Nadeo an und hatte bald ein Telefonat mit Florent Castelnerac, welcher mir anbot in Paris mit an einem neuen Tool zu arbeiten. Somit half ich während meines Praxissemesters bei der Entwicklung von "ManiaLive", welches im Prinzip eine von Nadeo entwickelte Alternative zu den bestehenden Tools darstellt. Erneut lernten wir aus den bisherigen Problemen und konzentrierten uns daher haupstächlich auf die Architektur und Erweiterbarkeit. Außerdem integrierten wir PHP Multithreading (für Hintergrundaufgaben), eine Plugin Verwaltung mit Versionierung, eine schöne UI und sogar eine Art Fenstermanager.

<figure style="max-width:600px" markdown="1">
![alt text](/img/aseco/manialive.png)
<figcaption>So sieht ManiaLive aus der Perspektive eines Spielers aus. Hier wurden zwei Screenshots zusammengefügt, um die Möglichkeiten des Fenstermanagers zu demonstrieren.</figcaption>
</figure>

## Danke

Sehr gerne erinnere ich mich an die Zeit zurück, als ich mit den Spielern aus der Trackmania Community zusammen Software schrieb. Vor allem von **Slig**, **AssemblerManiac**, **MrA**, **TheM**, **Eyez** und insbesondere **MrD** habe ich in diesen Jahren viel Unterstützung erhalten und gelernt.