---
title: Collection Test
layout: archive
permalink: /test_collection/
collection: test_collection
entries_layout: grid
classes: wide
---

Test collection test page.

<div class="entries-{{ page.entries_layout }}">
  {% include documents-collection.html collection=page.collection sort_by=page.sort_by sort_order=page.sort_order type=page.entries_layout %}
</div>

<p>Something else</p>
<ul>
    {% assign sorted = (site.test_collection | sort: 'date') | reverse %}
    {% for item in sorted %}
      {% if item.custom == false %}
        <li>{{ item.title }} - {{ item.date }}</li>
      {% endif %}
    {% endfor %}
</ul>

<div>
  <ul>
  {% for member in site.data.gillespediatags %}
    <li>{{ member.tag }}    
      <ul>
          {% assign sorted = (site.test_collection | sort: 'date') | reverse %}
          {% for item in sorted %}
            {% for color in item.categories %}
              {% if color == member.tag %}
                <li>{{ item.title }} - {{ item.date }}</li>
              {% endif %}
            {% endfor %}
          {% endfor %}
      </ul>
    </li>
  {% endfor %}
  </ul>
</div>