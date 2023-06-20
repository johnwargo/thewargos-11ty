---
title: Home
description: 
layout: index
eleventyNavigation:
  key: Home
  order: 1
categories: []
---

Pork frankfurter beef, cupim pork chop sirloin tail sausage tongue jerky burgdoggen shoulder spare ribs. Beef ribs pig capicola buffalo ball tip beef sausage corned beef prosciutto frankfurter burgdoggen bresaola kevin leberkas. Short loin ground round kielbasa alcatra, cow doner porchetta t-bone fatback. T-bone ham hamburger, landjaeger cupim shoulder bresaola ham hock tenderloin. Spare ribs tenderloin tri-tip, meatball jowl tail turducken chicken doner.

Salami porchetta cupim venison buffalo ham hock prosciutto meatball. Burgdoggen biltong kielbasa frankfurter. Spare ribs jerky ground round, swine ham pork chop drumstick capicola bacon venison turducken flank filet mignon. Bacon doner pastrami shank. Landjaeger bresaola beef ribs, beef t-bone brisket cow frankfurter buffalo biltong tail tri-tip porchetta leberkas salami. Landjaeger flank pastrami short ribs jerky. Kielbasa leberkas beef swine pig.

{% for post in collections.post limit: 5 %}
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

<a href="/articles/" class="button">All Articles</a>