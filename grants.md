---
layout: page
title: Grants
eyebrow: Organization selection and updates
subtitle: A record of organizations and recommendations as the fund’s work develops.
permalink: /grants/
description: Updates about organizations connected to the Panou Fund’s initiatives and the status of grant recommendations.
---

<style>
  .grants-list { display: grid; gap: 22px; }
  .grant-entry { padding: clamp(22px, 4vw, 34px); border-left: 4px solid var(--teal); background: var(--cream); }
  .grant-entry-label { margin: 0 0 12px; color: var(--orange); font: 750 11px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; letter-spacing: .14em; text-transform: uppercase; }
  .grant-tags { display: flex; flex-wrap: wrap; gap: 8px; list-style: none; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; }
  .grant-tags li { padding: 4px 10px; border: 1px solid var(--line); border-radius: 999px; background: var(--paper); color: var(--teal); font-size: 11px; font-weight: 650; line-height: 1.5; }
  .grant-tags li:first-child { border-color: var(--teal); background: var(--teal); color: #fff; }
  .grant-entry h2 { margin: 20px 0 12px; color: var(--ink); font: 400 clamp(26px, 3vw, 33px)/1.25 Georgia, serif; }
  .grant-entry-copy { margin: 0; color: #334948; }
  @media (max-width: 767px) { .grant-entry { border-left-width: 3px; } .grant-tags { gap: 7px; } }
</style>

<div class="grants-list" aria-label="Grant and fund updates">
  {% for entry in site.data.grants %}
  <article class="grant-entry">
    <p class="grant-entry-label">{{ entry.label | escape }}</p>
    <ul class="grant-tags" aria-label="Tags">
      {% for tag in entry.tags %}
      <li>{{ tag | escape }}</li>
      {% endfor %}
    </ul>
    <h2>{{ entry.title | escape }}</h2>
    <p class="grant-entry-copy">{{ entry.content | escape }}</p>
  </article>
  {% endfor %}
</div>
