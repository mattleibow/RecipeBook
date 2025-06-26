---
layout: default
title: Recipe Journey
---

<div class="text-center mb-5">
    <h1 class="display-3 mb-3">Welcome to My Recipe Journey</h1>
    <p class="lead">A collection of great recipes organized as daily story-driven cooking adventures</p>
    <p class="text-muted">Follow along as each recipe tells a story of comfort, healing, and connection through the magic of cooking.</p>
</div>

<div class="row">
    <div class="col-md-8 mx-auto">
        <h2 class="mb-4">Latest Recipe Stories</h2>
        
        {% assign recipe_files = site.pages | where_exp: "page", "page.path contains '2024/'" | where_exp: "page", "page.path contains 'fudgy-brownies.md' or page.path contains 'cinnamon-pancakes.md'" | sort: "path" | reverse %}
        
        {% for recipe in recipe_files limit: 3 %}
        <div class="card mb-4 shadow-sm">
            <div class="card-body">
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
                <p class="text-muted small">
                    {% if recipe.date %}
                        {{ recipe.date | date: "%Y/%m/%d" }}
                    {% else %}
                        {% assign date_parts = recipe.path | split: '/' %}
                        {% if date_parts.size >= 3 %}
                            {{ date_parts[0] }}/{{ date_parts[1] }}/{{ date_parts[2] }}
                        {% endif %}
                    {% endif %}
                </p>
                <p class="card-text">
                    {% assign story_start = recipe.content | split: '## A Story' | last | split: '##' | first | strip_html | truncate: 200 %}
                    {{ story_start }}
                </p>
                <a href="{{ recipe.url | relative_url }}" class="btn btn-primary">Read Recipe Story</a>
            </div>
        </div>
        {% endfor %}
        
        <div class="text-center mt-4">
            <a href="{{ '/recipes' | relative_url }}" class="btn btn-outline-primary btn-lg">View All Recipe Stories</a>
        </div>
    </div>
</div>

<div class="row mt-5">
    <div class="col-md-10 mx-auto">
        <div class="bg-light p-4 rounded">
            <h3>About This Journey</h3>
            <p>Each recipe in this collection is more than just a list of ingredients and instructions—it's a story. These tales of comfort, healing, and connection are designed to be timeless and universal, speaking to the shared human experience of finding solace and joy in the kitchen.</p>
            <p>Whether you're looking for comfort during difficult times, seeking to connect with others, or simply wanting to explore new flavors, these recipe stories invite you to be part of a continuous narrative of culinary discovery and emotional growth.</p>
        </div>
    </div>
</div>