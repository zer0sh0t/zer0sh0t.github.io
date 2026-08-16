---
layout: page
title: Experience
permalink: /experience/
nav: true
nav_order: 3
---

<style>
  .chronology {
    margin-top: 2rem;
  }
  .chrono-row {
    display: grid;
    grid-template-columns: 11rem 1fr;
    gap: 1.5rem;
    padding: 1.6rem 0;
    border-top: 1px solid var(--global-divider-color);
    text-decoration: none;
    color: inherit;
  }
  .chrono-row:last-child {
    border-bottom: 1px solid var(--global-divider-color);
  }
  .chrono-row:hover {
    text-decoration: none;
  }
  .chrono-period {
    color: var(--global-text-color-light);
    font-size: 0.9rem;
    padding-top: 0.15rem;
    white-space: nowrap;
  }
  .chrono-org {
    font-size: 1.15rem;
    font-weight: 600;
    color: var(--global-text-color);
    transition: color 0.2s ease;
  }
  .chrono-row:hover .chrono-org {
    color: var(--global-theme-color);
  }
  .chrono-org .arrow {
    opacity: 0;
    margin-left: 0.35rem;
    transition: opacity 0.2s ease;
  }
  .chrono-row:hover .chrono-org .arrow {
    opacity: 1;
  }
  .chrono-role {
    display: block;
    color: var(--global-text-color-light);
    font-size: 0.9rem;
    margin-top: 0.1rem;
  }
  .chrono-blurb {
    margin: 0.6rem 0 0 0;
    color: var(--global-text-color);
  }
  @media (max-width: 576px) {
    .chrono-row {
      grid-template-columns: 1fr;
      gap: 0.35rem;
    }
  }
</style>

<div class="chronology">
{% assign roles = site.experience | sort: "importance" %}
{% for role in roles %}
  <a class="chrono-row" href="{{ role.url | relative_url }}">
    <div class="chrono-period">{{ role.period }} &middot; {{ role.location }}</div>
    <div class="chrono-main">
      <span class="chrono-org">{{ role.title }}<span class="arrow">&rarr;</span></span>
      <span class="chrono-role">{{ role.role }}</span>
      <p class="chrono-blurb">{{ role.blurb }}</p>
    </div>
  </a>
{% endfor %}
</div>
