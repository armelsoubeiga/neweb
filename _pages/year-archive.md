---
layout: archive
permalink: /year-archive/
title: "Blog posts"
author_profile: true
redirect_from:
  - /wordpress/blog-posts/
---

You will find an archive of my old blog posts related to artificial intelligence on the link :

[http://armelsoubeiga.pythonanywhere.com/](http://armelsoubeiga.pythonanywhere.com/)

| :boom: DANGER              |
|:---------------------------|
| You will find an archive of my old blog posts related to artificial intelligence on the link :
[http://armelsoubeiga.pythonanywhere.com/](http://armelsoubeiga.pythonanywhere.com/) |


--------------------------

{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}
