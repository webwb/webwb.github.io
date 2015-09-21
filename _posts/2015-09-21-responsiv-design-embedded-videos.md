---
layout: post
author: André Borges
comments: true
categories: digital
image: responsiveteaser.jpg
published: true
title: "YOUTUBE & VIMEO-VIDEOS RESPONSIVE EINBINDEN - SO GEHT'S!"
---


Eine responsive Webseite passt sich selber der Auflösung des Gerätes an. Unabhängig ob es sich um ein Smartphone oder ein Tablet handelt - allen Nutzern wird eine Seite angeboten. Der Vorteil hierbei ist, dass lediglich eine Webseite administriert und angepasst werden muss und nicht für jedes Gerät eine entsprechende Version. Dies wird erreicht, in dem sich alle Elemente wie Bilder und Texte skalieren lassen. 

Einen Sonderfall bilden jedoch Videos die über ein iFrame eingebunden werden.

![Responsivevideos]({{site.baseurl}}/images/responsiveteaser.jpg)


## Das Problem mit eingebundenen Videos von Youtube und Co.
Jeder der ein Youtube- oder Vimeo-Video in seine responsive Seite einbaut, wird zu dem Problem kommen, dass den Videos eine feste Höhe und Breite mitgegeben wird.

Bei einem responsive Design sieht das ganze dann leider auf kleineren Bildschirmen wie folgt aus:
![Embedded Video nicht responsive]({{site.baseurl}}/images/videononresponsiv.jpg)

## Die "umständliche" CSS Lösung
Im Beitrag ["Creating Intrinsic Ratios for Video"](http://alistapart.com/article/creating-intrinsic-ratios-for-video) von Thierry Koblentz wird ausführlich erläutert wie mithilfe von prozentualem padding ein responsives Verhalten von eingebundenen externen Videos geschaffen wird.

## Die "schnelle" Javascript Lösung
Die von Thierry Koblentz beschriebene Lösung wird mit [Fitvid](http://fitvidsjs.com/) als eine schnelle Jquery Plugin Lösung angeboten.

Die Lösung unterstützt sowohl Youtube, als auch Vimeo Videos und noch einige weitere Plattformen. Für nicht unterstützte Plattformen wird ein customSelector angeboten, wodurch man weitere Videohoster hinzufügen kann.

### Wie wird diese eingebunden...

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

4.  Nun könnt ihr um die von euch eingebundenen Videos die entsprechende div mit der Klasse "video" setzen.

    ~~~html
        <div class="video">
        <iframe width="740" height="415" 	src="https://www.youtube.com/embed/UF8uR6Z6KLc" frameborder="0" allowfullscreen>     </iframe>
        </div>
    ~~~
