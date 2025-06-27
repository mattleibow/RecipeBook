---
layout: default
title: All Tags
permalink: /tags/
---

<div class="text-center mb-5">
    <h1 class="display-4 mb-3">All Recipe Tags</h1>
    <p class="lead">Explore recipes by theme, cuisine, ingredients, and cooking style</p>
</div>

<div class="row">
    <div class="col-md-10 mx-auto">
        {% assign all_tags = site.pages | where_exp: "page", "page.tags" | map: "tags" | join: "," | split: "," | uniq | sort %}
        
        {% if all_tags.size > 0 %}
        <div class="row">
            {% for tag in all_tags %}
            {% assign tag_count = 0 %}
            {% for recipe in site.pages %}
                {% if recipe.tags contains tag %}
                    {% assign tag_count = tag_count | plus: 1 %}
                {% endif %}
            {% endfor %}
            {% if tag_count > 0 %}
            <div class="col-lg-3 col-md-4 col-sm-6 mb-3">
                <div class="card h-100">
                    <div class="card-body text-center">
                        <h5 class="card-title">
                            <a href="{{ '/tags/' | append: tag | append: '/' | relative_url }}" class="text-decoration-none">
                                {{ tag | capitalize }}
                            </a>
                        </h5>
                        <p class="card-text text-muted">{{ tag_count }} recipe{% if tag_count != 1 %}s{% endif %}</p>
                    </div>
                </div>
            </div>
            {% endif %}
            {% endfor %}
        </div>
        {% else %}
        <div class="text-center">
            <p class="text-muted">No tags found.</p>
        </div>
        {% endif %}
        
        <div class="text-center mt-4">
            <a href="{{ '/' | relative_url }}" class="btn btn-outline-primary">Back to Home</a>
        </div>
    </div>
</div>