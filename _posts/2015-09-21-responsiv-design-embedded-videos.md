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

http://alistapart.com/article/creating-intrinsic-ratios-for-video

## Die "schnelle" Javascript Lösung
Die von Thierry Koblentz beschriebene Lösung wird mit [Fitvid](http://fitvidsjs.com/) als eine schnelle Jquery Plugin Lösung angeboten.

Die Lösung unterstützt sowohl Youtube, als auch Vimeo Videos und noch einige weitere Plattformen. Für nicht unterstützte Plattformen wird ein customSelector angeboten, wodurch man weitere Videohoster hinzufügen kann.

### Wie wird diese eingebunden...
1.  Ihr benötigt die [fitvids.js](https://github.com/davatron5000/FitVids.js/blob/master/jquery.fitvids.js) und falls nicht bereits in Verwendung die [jquery.js](https://jquery.com/download/)

2.  Fügt die Script Dateien eurer HTML-Datei hinzu
~~~html
<script src="path/to/jquery.min.js"></script>
<script src="path/to/jquery.fitvids.js"></script>
<script>
  $(document).ready(function(){
    // Target your .container, .wrapper, .post, etc.
    $("#thing-with-videos").fitVids();
  });
</script>
~~~



