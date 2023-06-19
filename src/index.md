---
title: Home
description: 
layout: index
eleventyNavigation:
  key: Home
  order: 1
categories: []
pagination:
  data: collections.post
  size: 5
  alias: posts
  reverse: true
---

{% include 'pagination-count.html' %}


{% for post in posts %}
  <article>
    <strong>
    <a href="{{post.url}}">{{ post.data.title }}</a>
    </strong>  
    <p><strong>Date:</strong>
      {{ post.date | readableDate }}
      {% if post.data.categories.length > 0 %}
        |
        <strong>
          Categories:
        </strong>
        {% for cat in post.data.categories %}
          <a href="/categories/{{ cat | slugify }}">{{ cat | strip }}</a>
          {%- unless forloop.last %},
          {% endunless %}
        {% endfor %}
      {% endif %}
    </p>
    <p>
      {% if post.data.description %}
        {{ post.data.description }}
      {% else %}
        {% excerpt post %}
      {% endif %}
    </p>
  </article>
{% endfor %}

<!-- <article>
  <a href="#" class="image filtered"><img src="images/pic01.jpg" alt="" /></a>
  <p>
    <strong>Magna feugiat etiam</strong>
    ipsum dolor tempus amet, magna consectetur. Fusce eu lacus imperdiet.</p>
  <ul class="actions special">
    <li>
      <a href="#" class="button small next">Details</a>
    </li>
  </ul>
</article> -->
