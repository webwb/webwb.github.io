---
layout: page
title: Archive
permalink: /archive/
class: archive
navigation: archive
---

<section id="archive">
  <ul>
    {% for post in site.posts %}

      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% capture pyear %}{{ post.previous.date | date: '%Y' }}{% endcapture %}

      {% if year != nyear %}
        <li><h3>{{ post.date | date: '%Y' }}</h3>
        <ul>
      {% endif %}

        {% capture month %}{{ post.date | date: '%B' }}{% endcapture %}
        {% capture nmonth %}{{ post.next.date | date: '%B' }}{% endcapture %}
        {% capture pmonth %}{{ post.previous.date | date: '%B' }}{% endcapture %}

        {% if month != nmonth %}
          <li><h4>{{ post.date | date: '%B' }}</h4>
          <ul>
        {% endif %}

          <li>{{ post.date | date:"%d.%m.%Y" }} <a href="{{ post.url }}">{{ post.title }}</a></li>

        {% if month != pmonth or year != pyear %}
          </ul></li>
        {% endif %}

      {% if year != pyear %}
        </ul>
      {% endif %}

    {% endfor %}
  </ul>
</section>
