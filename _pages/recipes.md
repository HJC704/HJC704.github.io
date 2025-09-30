---
layout: page
permalink: /recipes/
title: recipes
nav: true
nav_order: 6
---

<div class="recipes-page">
  <div class="recipes-page__intro">
    <p>
      I really enjoy cooking, very much the same as doing research, because my favorite recipes represent my research philosophy:
    </p>

    <div class="pull-quote">
      <p class="pull-quote__line">"The fresh ingredients often require only the simplest cooking methods."</p>
      <span class="pull-quote__cite">— <span class="pull-quote__cite-source">A Bite of China</span> <span class="pull-quote__cite-work">Season 1 (2012), narration</span></span>
    </div>

    <p>
      The recipes greatly comfort a child from Hunan, China when he misses his hometown.
    </p>

  </div>

  <div class="recipes-page__list">
    {% for recipe in site.data.recipes %}
      <article class="recipe-card">
        <div class="recipe-card__media{% unless recipe.image %} recipe-card__media--placeholder{% endunless %}">
          {% if recipe.image %}
            <img
              src="{{ '/assets/img/recipes/' | append: recipe.image | relative_url }}"
              alt="{{ recipe.name }}"
              loading="lazy"
            >
            <a
              class="recipe-card__view"
              href="{{ '/assets/img/recipes/' | append: recipe.image | relative_url }}"
              target="_blank"
              rel="noopener"
              aria-label="Open full photo of {{ recipe.name }}"
            >
              View photo
            </a>
          {% else %}
            <span class="recipe-card__placeholder-icon"><i class="fa-solid fa-utensils"></i></span>
          {% endif %}
        </div>

        <div class="recipe-card__content">
          {% if recipe.cuisine or recipe.difficulty or recipe.time %}
            <div class="recipe-card__meta">
              {% if recipe.cuisine %}
                <span class="recipe-card__chip">{{ recipe.cuisine }}</span>
              {% endif %}
              {% if recipe.time %}
                <span class="recipe-card__chip recipe-card__chip--muted">
                  <i class="fa-regular fa-clock"></i> {{ recipe.time }}
                </span>
              {% endif %}
              {% if recipe.difficulty %}
                <span class="recipe-card__chip recipe-card__chip--muted">
                  <i class="fa-solid fa-signal"></i> {{ recipe.difficulty }}
                </span>
              {% endif %}
            </div>
          {% endif %}

          <h3 class="recipe-card__title">{{ recipe.name }}</h3>
          {% if recipe.name_en %}
            <p class="recipe-card__subtitle">{{ recipe.name_en }}</p>
          {% endif %}

          <p class="recipe-card__description">{{ recipe.description }}</p>
        </div>
      </article>
    {% endfor %}

  </div>
</div>
