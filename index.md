---
title: XD-embedded
author: Esben Haabendal
---


# Resources

* [What is XD-embedded](what-is-xd-embedded.html)
* [XD-embedded Quickstart](quickstart.html)


# Blog

{% for post in site.posts limit:20 %}
* [{{ post.date | date_to_string }} {{ post.title }}]({{ post.url }}){% endfor %}
