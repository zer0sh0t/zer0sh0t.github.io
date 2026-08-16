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
    grid-template-columns: 10rem 1fr 13rem;
    gap: 1.75rem;
    align-items: start;
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
    line-height: 1.5;
  }
  .chrono-location {
    display: block;
    font-size: 0.85rem;
    opacity: 0.8;
  }
  .chrono-thumb {
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: cover;
    border-radius: 6px;
    display: block;
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
  @media (max-width: 768px) {
    .chrono-row {
      grid-template-columns: 1fr;
      gap: 0.5rem;
    }
    .chrono-period {
      padding-top: 0;
    }
    .chrono-location {
      display: inline;
    }
    .chrono-location::before {
      content: " · ";
    }
    .chrono-thumb {
      aspect-ratio: 16 / 9;
      margin-top: 0.4rem;
    }
  }
</style>

<div class="chronology">
{% assign roles = site.experience | sort: "importance" %}
{% for role in roles %}
  <a class="chrono-row" href="{{ role.url | relative_url }}">
    <div class="chrono-period">
      {{ role.period }}
      <span class="chrono-location">{{ role.location }}</span>
    </div>
    <div class="chrono-main">
      <span class="chrono-org">{{ role.title }}<span class="arrow">&rarr;</span></span>
      <span class="chrono-role">{{ role.role }}</span>
      <p class="chrono-blurb">{{ role.blurb }}</p>
    </div>
    {% assign highlight = role.thumb | default: role.img %}
    {% if highlight %}
      <img class="chrono-thumb" src="{{ highlight | relative_url }}" alt="{{ role.title }}" loading="lazy" />
    {% endif %}
  </a>
{% endfor %}
</div>
