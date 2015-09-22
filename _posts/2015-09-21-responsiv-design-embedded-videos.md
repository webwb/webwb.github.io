---
layout: post
author: André Borges
comments: true
categories: digital
image: responsiveteaser.jpg
published: true
title: "YOUTUBE & VIMEO-VIDEOS RESPONSIVE EINBINDEN - SO GEHT'S!"
---

Eine responsive Webseite passt sich selbst der Auflösung des Gerätes an. Unabhängig davon, ob es sich um ein Smartphone oder ein Tablet handelt, wird allen Nutzern eine Seite angeboten. Der Vorteil hierbei ist, dass lediglich eine Webseite administriert und angepasst werden muss und nicht für jedes Gerät eine entsprechende Version. Dies wird erreicht, indem sich alle Elemente wie Bilder und Texte skalieren lassen. 

Einen Sonderfall bilden jedoch Videos, die über einen iFrame eingebunden werden.

![Responsivevideos]({{site.baseurl}}/images/responsiveteaser.jpg)

## Das Problem mit eingebundenen Videos von YouTube und Co.
Jeder, der ein YouTube- oder Vimeo-Video in seine responsive Seite einbaut, wird zu dem Problem kommen, dass den Videos eine feste Höhe und Breite mitgegeben wird.

Bei einem responsiven Design sieht das Ganze dann leider auf kleineren Bildschirmen wie folgt aus:
![Embedded Video nicht responsive]({{site.baseurl}}/images/videononresponsiv.jpg)

## Die grundlegende CSS Lösung
Im Beitrag ["Creating Intrinsic Ratios for Video"](http://alistapart.com/article/creating-intrinsic-ratios-for-video) von Thierry Koblentz wird ausführlich erläutert, wie mithilfe von prozentualem Padding ein responsives Verhalten von eingebundenen, externen Videos geschaffen wird.

Eine deutsche Erläuterung hierzu findet ihr bei [Holger Koenemann](http://www.holgerkoenemann.de).

## Die "schnelle" Javascript Lösung
Die von Thierry Koblentz beschriebene Lösung wird mit [Fitvid](http://fitvidsjs.com/) als eine schnelle jQuery Plug-In Lösung angeboten.

Die Lösung unterstützt sowohl YouTube, als auch Vimeo Videos und noch einige weitere Plattformen. Für nicht unterstützte Plattformen wird ein Custom Selector angeboten, wodurch man weitere Video Hoster hinzufügen kann.

### So geht's...
1.  Ihr benötigt die [fitvids.js](https://github.com/davatron5000/FitVids.js/blob/master/jquery.fitvids.js) und falls nicht bereits in Verwendung die [jquery.js](https://jquery.com/download/)

2.  Fügt die Script Dateien eurer HTML-Datei hinzu. In meinem Fall sieht dies wie folgt aus...

    ~~~html
        <script src="/js/jquery-2.1.4.min.js"></script>
        <script src="/js/jquery.fitvids.js"></script>
        <script>
         $(document).ready(function(){
           // Target your .container, .wrapper, .post, etc.
           $(".video").fitVids();
         });
        </script>
    ~~~

3.  Fügt der CSS-Datei eine entsprechende Klasse hinzu

    ~~~css
        .video {
            margin-bottom:20px;
        }
    ~~~

4.  Nun könnt ihr, um die Videos die entsprechende div mit der Klasse "video" setzen.

    ~~~html
        <div class="video">
        <iframe width="740" height="415" 	src="https://www.youtube.com/embed/UF8uR6Z6KLc" frameborder="0" allowfullscreen>     </iframe>
        </div>
    ~~~

Das Ergebnis könnt ihr euch [hier](http://webworkers.io/life/2015/08/25/warum-motivation-das-einzige-ist-das-z-hlt-reden-die-jeder-geh-rt-haben-sollte.html) anschauen.

## Die "sehr schnelle" iFrame Lösung für Anfänger
Du möchtest oder kannst keine Änderungen an deiner Seite durchführen? Hierfür gibt es noch die Möglichkeit dem Embed Code des Videos den entsprechenden Style mitzugeben.

### So geht's...
Einfach den Link zum Video [hier eingeben](http://embedresponsively.com/) und den entsprechenden Code generieren lassen. Diesen könnt ihr dann ganz einfach in eure Seite einfügen.