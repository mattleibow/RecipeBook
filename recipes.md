---
layout: default
title: All Recipe Stories
permalink: /recipes/
---

<div class="text-center mb-5">
    <h1 class="display-4 mb-3">All Recipe Stories</h1>
    <p class="lead">Every recipe tells a story. Explore the complete collection of culinary adventures.</p>
</div>

<div class="row">
    <div class="col-md-10 mx-auto">
        {% assign recipe_files = site.pages | where_exp: "page", "page.path contains '2024/'" | where_exp: "page", "page.path contains 'fudgy-brownies.md' or page.path contains 'cinnamon-pancakes.md'" | sort: "path" %}
        
        {% for recipe in recipe_files %}
        <div class="card mb-4 shadow-sm">
            <div class="card-body">
                <div class="row">
                    <div class="col-md-8">
                        <h3 class="card-title">
                            <a href="{{ recipe.url | relative_url }}" class="text-decoration-none">
                                {% if recipe.title %}
                                    {{ recipe.title }}
                                {% else %}
                                    {% assign title = recipe.content | split: '# ' | last | split: newline | first %}
                                    {{ title }}
                                {% endif %}
                            </a>
                        </h3>
                        <p class="card-text">
                            {% assign story_start = recipe.content | split: '## A Story' | last | split: '##' | first | strip_html | truncate: 150 %}
                            {{ story_start }}
                        </p>
                    </div>
                    <div class="col-md-4 text-end">
                        <p class="text-muted small mb-2">
                            {% if recipe.date %}
                                Recipe {{ recipe.date | date: "%Y/%m/%d" }}
                            {% else %}
                                {% assign date_parts = recipe.path | split: '/' %}
                                {% if date_parts.size >= 3 %}
                                    Recipe {{ date_parts[0] }}/{{ date_parts[1] }}/{{ date_parts[2] }}
                                {% endif %}
                            {% endif %}
                        </p>
                        <a href="{{ recipe.url | relative_url }}" class="btn btn-primary">Read Story</a>
                    </div>
                </div>
            </div>
        </div>
        {% endfor %}
        
        {% if recipe_files.size == 0 %}
        <div class="text-center">
            <p class="text-muted">No recipe stories found. Check back soon for new culinary adventures!</p>
        </div>
        {% endif %}
        
        <div class="text-center mt-4">
            <a href="{{ '/' | relative_url }}" class="btn btn-outline-primary">Back to Home</a>
        </div>
    </div>
</div>