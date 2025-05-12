---
layout: profiles
permalink: /people/
title: people
description: members of the lab or group
nav: true
nav_order: 7

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - align: right
    image: prof_pic.jpg
    content: about_einstein.md
    image_circular: false # crops the image to make it circular
    more_info: >
      <p>555 your office number</p>
      <p>123 your address street</p>
      <p>Your City, State 12345</p>
  - align: left
    image: prof_pic.jpg
    content: about_einstein.md
    image_circular: false # crops the image to make it circular
    more_info: >
      <p>555 your office number</p>
      <p>123 your address street</p>
      <p>Your City, State 12345</p>
---另外，这是我的layouts/people.liquid。---
layout: page
---
<div class="post">
  <article>
    {% if page.profiles %}
      {% for profile in page.profiles %}
        <hr>
        <div class="profile float-{% if profile.align == 'left' %}left{% else %}right{% endif %}">
          {% if profile.image %}
            {% assign profile_image_path = profile.image | prepend: 'assets/img/' %}
            {% if profile.image_circular %}
              {% assign profile_image_class = 'img-fluid z-depth-1 rounded-circle' %}
            {% else %}
              {% assign profile_image_class = 'img-fluid z-depth-1 rounded' %}
            {% endif %}
            {% capture sizes %}(min-width: {{ site.max_width }}) {{ site.max_width | minus: 30 | times: 0.3}}px, (min-width: 576px) 30vw, 95vw"{% endcapture %}
            {% include figure.liquid loading="eager" path=profile_image_path class=profile_image_class sizes=sizes alt=profile.image %}
          {% endif %}
          {% if profile.more_info %}
            <div class="more-info">{{ profile.more_info }}</div>
          {% endif %}
        </div>

        <div class="clearfix">
          {% if profile.content %}
            {% capture profile_content %}{% include_relative {{ profile.content }} %}{% endcapture %}
            {{ profile_content | markdownify }}
          {% else %}
            {{ content }}
          {% endif %}
        </div>
      {% endfor %}
    {% endif %}
  </article>
</div>
