---
layout: page
title: Tags
permalink: /tags/
class: tags
---
<script>
// http://stackoverflow.com/a/901144
function getParameterByName(name) {
  name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
  var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
  results = regex.exec(location.search);
  return results === null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
}

window.onload = function() {
  var tag = getParameterByName('tag');
  if (tag && document.getElementById('tag-' + tag)) {

    var tags = document.getElementsByTagName('li');
    for (var i=0; i<tags.length; i++) {
      if ( tags[i].className === 'tag') {
	      tags[i].style.display = "none";
      }
	  }

    document.getElementById('tag-' + tag).style.display = 'block';
    document.getElementById('seeAllTags').style.display = 'block';
    document.getElementById('tagTitle').innerHTML = 'Posts tagged with: ' + tag;

  }
};
</script>

{% capture site_tags %}
  {% for p in site.tags %}
    {{ p[0] }}
  {% endfor %}
{% endcapture %}

{% assign sortedtags = site_tags | split:' ' | sort %}

<h2 id="tagTitle">Searching ...</h2>
<section>
{% if site.tags %}
  <ul>
    {% for tag in sortedtags %}
      <li class="tag" id="tag-{{ tag }}">
          <h4><i class="fa fa-tag"></i>&nbsp;&nbsp;{{ tag }}</h4>
      <ul>
        {% for post in site.tags[tag] %}
          <li>{{ post.date | date:"%d.%m.%Y" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
      </ul>
      </li>
    {% endfor %}
  </ul>
{% endif %}

<a id="seeAllTags" href="/tags/">all Tags</a>

</section>





