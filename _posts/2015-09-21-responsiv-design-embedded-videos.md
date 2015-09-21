---
published: false
author: André Borges
comments: true
categories: digital
image: ""
title: "Responsiv Design - Embedded Videos"
---



Jeder der ein Youtube- oder Vimeo-Video in seine responsive Seite einbaut, wird zu dem Problem kommen, dass den Videos eine feste Höhe und Breite mitgegeben wird.

Bei einem responsive Design sieht das ganze dann leider auf kleineren Bidlschirmen wie folgt aus...

![Embedded Video nicht responsive]({{site.baseurl}}/images/videononresponsiv.png)

## Die "umständliche" CSS Lösung
Im Beitrag ["Creating Intrinsic Ratios for Video"](http://alistapart.com/article/creating-intrinsic-ratios-for-video) von Thierry Koblentz wird ausführlich erläutert wie mithilfe von prozentualem padding ein responsives Verhalten von eingebundenen externen Videos geschaffen wird.

## Die "schnelle" Javascript Lösung
Die von Thierry Koblentz beschriebene Lösung wird mit [Fitvid](http://fitvidsjs.com/) als eine schnelle Jquery Plugin Lösung angeboten.

Die Lösung unterstützt sowohl Youtube, als auch Vimeo Videos und noch einige weitere Plattformen. Für nicht unterstützte Plattformen wird ein customSelector angeboten, wodurch man weitere Videohoster hinzufügen kann.

### Wie wird diese eingebunden...
1.  Ihr benötigt die [fitvids.js](https://github.com/davatron5000/FitVids.js/blob/master/jquery.fitvids.js) und falls nicht bereits in Verwendung die [jquery.js](https://jquery.com/download/)


