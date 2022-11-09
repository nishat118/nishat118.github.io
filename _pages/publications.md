---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<!-- {% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %} -->

You can also find my articles on <a href="https://scholar.google.com/citations?hl=en&user=UZKkHBUAAAAJ" target="_blank">my Google Scholar profile</a>. (* indicates equal contribution)

{% include base_path %}

{% assign publicationsByYear = site.publications | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in publicationsByYear reversed %}
  <h1 style="margin: 1.5em 0px -0.5em; padding: 0px; color: brown;">{{ year.name }}</h1>
  {% assign publicationsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
  {% for month in publicationsByMonth reversed %}
    {% for post in month.items reversed %}
      {% if post.venue != "arXiv" %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}
  {% endfor %}
{% endfor %}


