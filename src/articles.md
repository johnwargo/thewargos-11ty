---
title: Articles
description: 
layout: generic
eleventyNavigation:
  key: Articles
  order: 2
categories: []
pagination:
  data: collections.post
  size: 20
  alias: posts
  reverse: true
---

Swine spare ribs porchetta prosciutto buffalo brisket andouille ham hock. Ground round rump beef chislic pastrami cow shank filet mignon jowl short ribs hamburger sausage turducken. Meatball ham filet mignon chuck jerky. T-bone shoulder pastrami, strip steak jerky shank porchetta ground round.

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

{% include "pagination-nav.html" %}