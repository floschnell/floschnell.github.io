---
layout: page
title: RadlNavi
permalink: /projekte/radlnavi/
category: Projekte
---

## Motivation

Vor kurzem bin ich auf die Initiative MunichWays gestoßen. Ein laufendes Projekt der Initiative ist die Kartographierung und Bewertung Münchner Straßen und Radwege bezüglich ihrer Fahrradtauglichkeit und Sicherheit. Eine Visualiserung der Bewertungen könnt ihr [hier finden](https://usocialmaps.carto.com/builder/dfd7b295-73a7-4dfe-85e6-933dd7fe5787).

Da ich in der Vergangenheit schon mit OpenStreetMaps und Routing gespielt hatte, wusste ich um das Open Source Projekt OSRM (Open Source Routing Machine) und dass dies mit OpenStreetMaps Daten gefüttert werden kann.

Während Freizeitplatformen wie Komoot gut für die Outdoornavigation auf dem Land sind und Google Maps immer vorrangig die schnellsten Strecken findet, hatte ich das Gefühl, dass aktuell eine gute Fahrradnavigation für München fehlt, welche eine sichere und stressfreie Navigation fokussiert. Somit entstand das [RadlNavi](https://www.radlnavi.de).

## Funktionsweise

Zuerst begann ich damit, die OpenStreetMaps (OSM) Daten mit den MunichWays Bewertungen anzureichern. Der Python Code, [welchen ihr in meinem GitHub Repo finden könnt](https://github.com/floschnell/munichways-routing), lädt zuerst das GeoJSON von der Carto Anwendung herunter und versucht dann die Bewertungen auf Straßenteile in den OSM Daten zu übertragen. Der Prozess zieht sich etwas (waren bei meinem 2015er MacBook Pro ~30 Minuten), ist aber voll automatisiert. Die Datei `out.pbf` dient nun als Datenbasis für die OSRM. Ferner habe ich ein Lua Profil geschrieben, welches OSRM nutzt, um die Gewichtungen der Route zu berechnen. In dem von mir erstellten Lua Profil werden nun die Straßenbewertungen mit einbezogen. Außerdem werden kleinere, weniger befahrene Straßen bevorzugt.

## Vergleich

Der Vergleich mit zwei populären Routingdiensten zeigt deutlich, dass die Routen unter Berücksichtigung verschiedener Kriterien berechnet werden. Bei der gewählten Nord-Süd Route (von der *Münchner Freiheit* zum *Wettersteinplatz*) macht für mich die *RadlNavi* Route am meisten Sinn. Eine ähnliche Route wäre ich intuitiv selbst auch gefahren. Beim *RadlNavi* könnt ihr außerdem mit eurer Maus unten im Einstellungsbereich auf die unterschiedlichen Farbbalken fahren. Je nachdem leuchtet dann der zugehörige Streckenteil auf. So könnt ihr sehen, welcher Teil der Route beleuchtet ist oder wo euch die Strecke ein Stück über einen unbefestigten Weg führt.

<div class="catalog" markdown="1">
<p>
<figure style="max-width:320px;float:left;margin-right:2em">
<img alt="Route berechnet mit RadlNavi" src="/img/radlnavi/route-radlnavi.png" />
<figcaption>Die mit RadlNavi.de berechnete Route verläuft größtenteils direkt an der Isar auf dem Radweg.</figcaption>
</figure>

<figure style="max-width:320px;float:left;margin-right:2em">
<img alt="Route berechnet mit Google Maps" src="/img/radlnavi/route-gmaps.png" />
<figcaption>Die Google Maps Route führt über die Leopoldstraße am Stadtzentrum vorbei und nur ein ganz kurzes Stück an der Isar entlang.</figcaption>
</figure>

<figure style="max-width:320px;float:left;margin-right:2em">
<img alt="Route berechnet mit Komoot" src="/img/radlnavi/route-komoot.png" />
<figcaption>Komoot führt einen zuerst über die anstrengende Loepoldstraße und anschließend durch die Münchner Innenstadt.</figcaption>
</figure>
</p>
</div>