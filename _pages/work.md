---
layout: page
title: Work
permalink: /work/
nav: true
nav_order: 2
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
  .chrono-org {
    font-size: 1.15rem;
    font-weight: 600;
    color: var(--global-text-color);
    transition: color 0.2s ease;
  }
  a.chrono-row:hover .chrono-org {
    color: var(--global-theme-color);
  }
  .chrono-org .arrow {
    opacity: 0;
    margin-left: 0.35rem;
    transition: opacity 0.2s ease;
  }
  a.chrono-row:hover .chrono-org .arrow {
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
  .chrono-thumb {
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: cover;
    border-radius: 6px;
    display: block;
  }

  /* Education rows: context, not headline. Dimmer, no link, logo instead of media. */
  .chrono-edu .chrono-org {
    font-size: 1rem;
    font-weight: 600;
  }
  .chrono-edu .chrono-blurb,
  .chrono-edu .chrono-period {
    color: var(--global-text-color-light);
  }
  .chrono-edu .chrono-blurb {
    font-size: 0.95rem;
  }
  .chrono-logo {
    width: 100%;
    height: 4.5rem;
    object-fit: contain;
    object-position: center;
    display: block;
    opacity: 0.85;
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
    .chrono-logo {
      height: 3.5rem;
      object-position: left;
      margin-top: 0.4rem;
    }
  }
</style>

{% assign roles = site.experience %}
{% assign education = site.data.education %}
{% assign timeline = roles | concat: education | sort: "order" %}

<div class="chronology">
{% for item in timeline %}
  {% if item.url %}
    <a class="chrono-row" href="{{ item.url | relative_url }}">
  {% else %}
    <div class="chrono-row chrono-edu">
  {% endif %}

    <div class="chrono-period">
      {{ item.period }}
      <span class="chrono-location">{{ item.location }}</span>
    </div>

    <div class="chrono-main">
      <span class="chrono-org">{{ item.title }}{% if item.url %}<span class="arrow">&rarr;</span>{% endif %}</span>
      <span class="chrono-role">{{ item.role }}</span>
      <p class="chrono-blurb">{{ item.blurb }}</p>
    </div>

    {% if item.logo %}
      <img class="chrono-logo" src="{{ item.logo | relative_url }}" alt="{{ item.title }}" loading="lazy" />
    {% else %}
      {% assign highlight = item.thumb | default: item.img %}
      {% if highlight %}
        <img class="chrono-thumb" src="{{ highlight | relative_url }}" alt="{{ item.title }}" loading="lazy" />
      {% endif %}
    {% endif %}

  {% if item.url %}</a>{% else %}</div>{% endif %}
{% endfor %}
</div>
