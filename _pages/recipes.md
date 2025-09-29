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
      I really enjoy cooking, very much the same as doing research. It's not only because my favourate recipes represents my research philosophy:
    </p>

  <div class="pull-quote">
    <q>“高端的食材，往往只需要最朴素的烹饪方式。”</q><br>
    <q>"The finest ingredients often require only the simplest cooking methods."</q>
    <span class="cite">— A Bite of China <span class="work">Season 1 (2012), narration</span></span>
  </div>
    
  <p>
      but they also comfort a child from Hunan, China when he misses his hometown.
  </p>

    <p>
      I like seafood the best, so the recipes includ lots of seafood dishes that carry memories,
      rituals, and small experiments from my kitchen. I revisit and refine them often—feel free to explore,
      remix, and make them your own.
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
