---
published: false
author: André Borges
comments: true
categories: life
image: ""
title: "Seo - Nützliche Tools..."
---


## Schritt 1: Die handwerkliche Umsetzung der Seite prüfen
Im ersten Schritt sollte die Seite zunächst auf handwerkliche Fehler geprüft werden. Ein Beispiel hierfür ist z.B. ob alle Bilder eine Webseite alternative Texte bekommen haben. Dies hilft Google beispielsweise diese Bilder und damit auch die Webseite besser zu kategorisieren. 

### HTML
Ein HTML-Check kann über folgende Seite erfolgen:
https://validator.w3.org/

Nach einigen Korrekturen sollten hier keine Fehler mehr auftauchen.

### CSS
Ein CSS-Check kann über folgende Seite erfolgen:
http://jigsaw.w3.org/css-validator/

## Performance
Ein wichtiger Faktor für die Nutzer beim Aufruf der Seite, aber auch der Bewertung der eigenen Seite durch Google ist die Geschwindigkeit der Seite.
Um eine Vebesserung der Performance durchzuführen, kann das PageSpeed Tool von Google verwendet werden. Neben einer Auswertung bietet es auch Hinweise auf Verbesserungsmöglichkeiten.
https://developers.google.com/speed/pagespeed/insights/

> Checkliste
- Favicon (16/16) erstellen
- Mobile-Touch-Icon erstellen
- Erreichbar mit und ohne www (Redirect)
- Individuelle Fehlerseite

## Schritt 2: Seite auf Metatags und sonstige Punkte prüfen
Im zweiten Schritt prüfen wir, welche weitere Optimierungen wir auf der Seite durchführen können.

http://www.seitenreport.de
http://www.seoworkers.com/tools/analyzer.html
http://seositecheckup.com/
http://seobility.net/de
http://seoptimer.com
https://www.dareboost.com/home
http://www.seitwert.de/seitwert.php
http://www.qualidator.com/
https://moz.com/tools

### Seitenreport
Die Seite http://www.seitenreport.de bietet eine Analyse der Seite an.
Wichtige Hinweise (die sonst andere nicht haben):
- Prüfung auf den Language-Key

### Seoworkers
http://www.seoworkers.com/tools/analyzer.html

### Seositecheckup
Eine sehr ausführliche Möglichkeit seine Seite zu prüfen. http://seositecheckup.com/

### Seobility
asdasd

### Seoptimer
Erstellt eine schöne To-Do-Liste http://seoptimer.com


## Seite in Verzeichnisse eintragen

### DMOZ
Ein wichtiges globales Verzeichnis ist http://www.dmoz.org.
Hier sollte eure Seite in der korrekten Kategorie mit dem entsprechenden Titel und einer aussagekräftigen Beschreibung eingepflegt werden.

Hinweis: Alle Vorschläge werden händisch geprüft, weshalb ein Eintrag in diesem Verzeichnis sehr lange dauern kann.

### Wikipedia
Durch das sehr gute Ranking von Wikipedia bietet es sich an, eine Verlinkung der eigenen Seite zu platzieren, sofern sinnvoll und möglich.

## Nice-to-have

#### WOT-Rating
Das Plugin WOT zeigt Nutzern ob es sich bei einer Seite, um eine vertrauenswürdige Seite handelt.
Sein Unternehmen kann man unter https://www.mywot.com/ angeben.

### Google Analytics
Um die Statistiken der eigenen Seite tracken zu können, verwenden die meisten Seitenbetreiber Google Analytics. Da das Unternehmen aus Amerika stammt kann es durch Analyse-Daten umfangreiche Persöhnlichkeitsprofile der User anfertigen.

Für einen datenschutzkonformen Einsatz bietet Google Analytics die Funktion _anonymizeIp() an, mit der die IP Adressen vor der Übermittlung an Google anonymisiert werden.

### Sitemap erstellen
Eine Sitemap hilft Suchmaschinen den kompletten Inhalt der Webseite zu erfassen.
Die Erstellung einer Sitemap kann manuell erfolgen oder mit einem Tool wie
https://www.xml-sitemaps.com/.

Die erstellte Sitemap kann dann entsprechend in das root-Verzeichnis gelegt werden und im [Google Webmaster Tool](https://www.google.com/webmasters/tools/home) eingetragen werden.

Hinweis: Auch Bing bietet die Möglichkeit über das Dashboard die eigene Sitemap einzureichen.

### Google Suche
Mit dem Tool können Daten die über schema.org an Google übergeben werden sollen, überprüft werden.
https://developers.google.com/structured-data/testing-tool/

Helfen kann auch...
https://www.google.com/webmasters/markup-helper/u/0/

## Domainhandling
Um die Linkpopularität zu steigern, sollte eine htaccess Datei eingerichtet werden. Zum einen sollte kein Unterschied zwischen dem Aufruf mit und ohne www existieren. Zum anderen sollte eine Domain als die Hauptdomain genutzt werden.

## Suchbegriffe analysieren und Inhalte verbessern
Der Inhalt einer Seite muss so gestaltet sein, das Google die Inhalte der Seite entsprechend für relevant hält. Daher lohnt es sich einen Blick in das Google Webmastertool zu werfen und relevante Suchbegriffe zu ermitteln.

https://www.google.com/webmasters/tools/search-analytics?hl=de&authuser=0&siteUrl=<domain>

## Caching
Nutzer sollten bereits geladene Ressourcen nicht erneut laden müssen. Hierfür bietet sich ein Caching an.

Beispiel einer htaccess Datei
~~~xml
## EXPIRES CACHING ##
<IfModule mod_expires.c>
ExpiresActive On
ExpiresByType image/jpg "access 1 year"
ExpiresByType image/jpeg "access 1 year"
ExpiresByType image/gif "access 1 year"
ExpiresByType image/png "access 1 year"
ExpiresByType text/css "access 1 month"
ExpiresByType text/html "access 1 month"
ExpiresByType application/pdf "access 1 month"
ExpiresByType text/x-javascript "access 1 month"
ExpiresByType text/css "access plus 1 year"
ExpiresByType application/x-shockwave-flash "access 1 month"
ExpiresByType image/x-icon "access 1 year"
ExpiresDefault "access 1 month"
</IfModule>

<IfModule mod_headers.c>
 <FilesMatch "\.(js|css|xml|gz)$">
   Header append Vary: Accept-Encoding
 </FilesMatch>
</IfModule>

<ifModule mod_gzip.c>
mod_gzip_on Yes
mod_gzip_dechunk Yes
mod_gzip_item_include file .(html?|txt|css|js|php|pl)$
mod_gzip_item_include handler ^cgi-script$
mod_gzip_item_include mime ^text/.*
mod_gzip_item_include mime ^application/x-javascript.*
mod_gzip_item_exclude mime ^image/.*
mod_gzip_item_exclude rspheader ^Content-Encoding:.*gzip.*
</ifModule>

<IfModule mod_deflate.c>
SetOutputFilter DEFLATE
AddOutputFilterByType DEFLATE text/html text/css text/plain text/xml text/x-js text/js 
</IfModule>
## EXPIRES CACHING ##
~~~
