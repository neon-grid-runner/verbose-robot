---
layout: page
title: archive
permalink: /archive/
---

{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% capture month %}{{ post.date | date: '%B' }}{% endcapture %}
  
  {% if year != prev_year %}
## {{ year }}
    {% assign prev_year = year %}
  {% endif %}
  
  {% if month != prev_month %}
### {{ month }}
    {% assign prev_month = month %}
  {% endif %}
  
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y-%m-%d" }}
{% endfor %} 
