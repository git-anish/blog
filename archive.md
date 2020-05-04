---
layout: page
title : Archive
header : Post Archive
group: navigation
---

<div class="post">
	  {% for post in site.posts %}
	    {% unless post.next %}
	      <h3>{{ post.date | date: '%Y' }}</h3>
	    {% else %}
	      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
	      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
	      {% if year != nyear %}
	        <h3>{{ post.date | date: '%Y' }}</h3>
	      {% endif %}
	    {% endunless %}

    	<ul><li><p>{{ post.date | date: "%d %b %Y" }} &mdash; <a href="{{ post.url | prepend: site.baseurl }}"> {{ post.title }}</a></p></li></ul>
	  {% endfor %}
</div>
