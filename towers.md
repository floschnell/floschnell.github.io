---
layout: page
title: Towers
permalink: /projekte/towers/
category: Projekte
---

Aktuell arbeite ich an einer eigenen Version des <mark>Brettspiels Kamisado</mark>, da ich nach einem Projekt suchte, um mich mit [React](https://facebook.github.io/react/) vertraut zu machen. Kamisado eignete sich gut, da es sich hierbei um ein zugbasiertes Spiel handelt und somit nur nach jedem Zug neu gezeichnet werden muss. Zudem gefiel mir die Aussicht auf die Umsetzung einer eigenen KI.

Begonnen hatte ich mit einer Multiplayer Webversion. Hierfür verwende ich zusätzlich das *Redux* Framework, um den Zustand der Anwendung zu verwalten. Zur Synchronisierung der Clients und um die Spiele zu persistieren setze ich zudem Google's *Firebase* Datenbank ein. Um die asynchrone Kommunikation zwischen den Anwendungen gut mit Redux vereinen zu können, verwende ich die *redux-thunk* Middleware - wobei ich bereits darüber nachdenke diese durch *redux-observable* auszutauschen.

Nachdem eine erste Version des Spiels spielbar war, wollte ich diese auch auf meinem Handy nutzen können. Das ging mit der Webversion zwar schon recht gut, allerdings fehlten beispielsweise Push-Notifications. *React-Native* versprach Abhilfe. Durch eine bereits gute Trennung von Logik und Rendering war es möglich viel von meinem bereits geschriebenen Code wiederzuverwenden.

Wenn euch die Umsetzung interessiert, oder ihr euch an der Entwicklung beteiligen wollt, so findet ihr das Projekt unter meinem Github Account: https://github.com/floschnell/towers.

<div class="catalog" markdown="1">
![alt text][towers1] ![alt text][towers2]![alt text][towers3]
</div>

[towers1]: /img/towers/towers1.png "Logo Title Text 2"
[towers2]: /img/towers/towers2.png "Logo Title Text 2"
[towers3]: /img/towers/towers3.png "Logo Title Text 2"