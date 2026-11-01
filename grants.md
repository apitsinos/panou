---
layout: page
title: Grants
eyebrow: Organization selection and updates
subtitle: A record of organizations and recommendations as the fund’s work develops.
permalink: /grants/
description: Updates about organizations supported by the Panou Fund and the status of grant recommendations.
---

{% include grants-styles.html %}

<div class="grants-list" aria-label="Grant and fund updates">
  {% assign grants = site.grants | sort: "weight" %}
  {% for entry in grants %}
  <article class="grant-entry">
    <p class="grant-entry-label">{{ entry.label | escape }}</p>
    <ul class="grant-tags" aria-label="Tags">
      {% for tag in entry.tags %}
      <li>{{ tag | escape }}</li>
      {% endfor %}
    </ul>
    <h2><a class="grant-entry-link" href="{{ entry.url | relative_url }}">{{ entry.title | escape }}</a></h2>
    <p class="grant-entry-copy">{{ entry.excerpt | strip_html | normalize_whitespace | truncatewords: 44 | escape }}</p>
    <a class="grant-entry-action" href="{{ entry.url | relative_url }}">Read update <span aria-hidden="true">→</span></a>
  </article>
  {% endfor %}
  {% unless grants.size > 0 %}
  <p class="grant-entry-copy">Updates will appear here as the fund’s work develops.</p>
  {% endunless %}
</div>
