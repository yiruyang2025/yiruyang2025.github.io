---
layout: page
title: People
permalink: /people/
description: Meet our team members and collaborators.
nav: true
nav_order: 5
display_categories: [Lab🇨🇭, Friends and Alumni🌍]
horizontal: false
---

<div class="people">
  {%- if site.data.people -%}
  <!-- Display people by categories -->
  {%- for category in page.display_categories %}
    <h2 class="category">{{ category }}</h2>
    {%- assign categorized_people = site.data.people[category] -%}
    {%- if categorized_people -%}
    <!-- iterate through each group in the category -->
    {% for group in categorized_people %}
      {% if group.name %}
        <h3 class="group-name">{{ group.name }}</h3>
      {% endif %}
      
      <!-- iterate through people in the group -->
      {% if group.people %}
        <div class="grid">
          {% for person in group.people %}
            <div class="grid-item">
              <div class="card hoverable">
                <div class="row no-gutters">
                  <div class="col-sm-4 col-md-3">
                    {% if person.image %}
                    <img src="{{ person.image | prepend: '/assets/img/people/' | relative_url }}" class="card-img img-fluid" alt="{{ person.name }}" />
                    {% endif %}
                  </div>
                  <div class="col-sm-8 col-md-9">
                    <div class="card-body">
                      <h5 class="card-title">{{ person.name }}</h5>
                      <h6 class="card-subtitle mb-2 text-muted">{{ person.position }}</h6>
                      {% if person.email %}
                      <p class="card-text">
                        <small>Email: <a href="mailto:{{ person.email }}">{{ person.email }}</a></small>
                      </p>
                      {% endif %}
                      {% if person.website %}
                      <p class="card-text">
                        <small>Website: <a href="{{ person.website }}" target="_blank">{{ person.website }}</a></small>
                      </p>
                      {% endif %}
                      {% if person.interests %}
                      <p class="card-text">
                        <small><strong>Interests:</strong> {{ person.interests }}</small>
                      </p>
                      {% endif %}
                      {% if person.description %}
                      <p class="card-text">{{ person.description }}</p>
                      {% endif %}
                    </div>
                  </div>
                </div>
              </div>
            </div>
          {% endfor %}
        </div>
      {% endif %}
      <div class="clearfix"></div>
    {% endfor %}
    {%- endif -%}
  {% endfor %}
  {%- endif -%}
</div>
