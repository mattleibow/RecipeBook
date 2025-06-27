# Recipe Story Writing Guidelines

This repository contains a collection of recipe stories that are meant to be inclusive, timeless, and part of a continuous narrative. Each recipe is generated daily and should follow these guidelines to maintain consistency and accessibility.

## Folder Structure

Recipes are organized in a year/month/day structure:
```
YYYY/MM/DD/recipe-name.md
```

Example:
```
2024/01/01/fudgy-brownies.md
2024/01/02/cinnamon-pancakes.md
2024/01/03/comfort-soup.md
```

## Story Writing Requirements

### 1. Continuous Narrative
- Each recipe should connect to the overall story arc
- Reference previous recipes or experiences when appropriate
- Build character development and emotional growth
- Maintain consistency with established relationships and settings

### 2. Non-Specific Dates and Times
**Avoid using:**
- Specific days of the week (Monday, Tuesday, Sunday, etc.)
- Specific months or seasons (January, October, spring, winter, etc.)
- Specific times of day (morning, evening, afternoon)
- Relative time references (yesterday, tomorrow, last week, next month)

**Instead use:**
- Generic time references ("time had passed", "recently", "one day")
- Descriptive but non-specific settings ("a crisp morning", "a quiet evening")
- Emotional or situational context rather than temporal markers

### 3. Inclusive and Universal Appeal
- Avoid location-specific references that might exclude readers
- Use universal themes of comfort, healing, connection, and growth
- Make the emotional journey relatable to people from all backgrounds
- Focus on feelings and experiences that transcend cultural boundaries

### 4. Recipe Story Structure

Each recipe should include:

1. **Title** - Descriptive and appealing
2. **Story Section** - The narrative connecting to the broader story
3. **Ingredients** - Clear, organized ingredient lists
4. **Instructions** - Step-by-step cooking directions
5. **Tips** - Helpful advice for success
6. **Closing Note** - A warm, encouraging message

### 5. Daily Generation
- A new recipe is generated every day
- Each day builds upon the previous day's story
- Maintain emotional continuity while introducing new recipes
- Balance familiar comfort with new culinary adventures

## Writing Style Guidelines

- Write in first person to maintain intimacy
- Use warm, conversational tone
- Include sensory details (aromas, textures, sounds)
- Focus on the emotional journey alongside the cooking process
- End with hope, comfort, or connection

## Example Opening Patterns

**Good:**
- "Time had passed since my last baking adventure..."
- "As I stood in my familiar kitchen..."
- "Something had shifted in my understanding of comfort food..."

**Avoid:**
- "Last Tuesday morning..."
- "Three weeks after Christmas..."
- "On a cold January evening..."

Remember: These stories should feel timeless and accessible to anyone, anywhere, at any time of year.

## Tag Management System

This repository uses a comprehensive tag cloud system for recipe discovery and navigation. When working with recipes, always maintain the tagging system:

### 6. Recipe Tagging Requirements

**When creating or editing recipes, always:**
- Add appropriate tags to the recipe frontmatter in the `tags:` field
- Use existing tags when possible to maintain consistency
- Create new tag pages when introducing new tags
- Update existing tag pages when adding recipes with existing tags

**Tag categories to consider:**
- **Recipe types**: dessert, pasta, bread, soup, stew, salad, etc.
- **Cooking methods**: braised, baked, grilled, steamed, slow-cooked, etc.
- **Story themes**: comfort, healing, community, family, connection, etc.
- **Primary ingredients**: chocolate, herbs, mushrooms, spices, etc.
- **Cultural cuisines**: Italian, Thai, Moroccan, Korean, French, etc.
- **Dietary considerations**: vegetarian, healthy, hearty, light, etc.
- **Occasions**: celebration, breakfast, tea-time, etc.

**Tag page structure:**
- Each tag has its own page at `/tags/{tag}/index.md`
- Tag pages automatically list all recipes with that tag
- Use lowercase, hyphenated naming for tag files (e.g., `slow-cooked.md`)
- Ensure the tag page layout uses `layout: tag` and includes `tag: {tagname}`

**When adding new recipes:**
1. Review the story and recipe to identify 6-10 relevant tags
2. Check if tag pages exist in the `/tags/` directory
3. Create new tag pages for any new tags introduced
4. Verify tags are properly formatted in recipe frontmatter as YAML array

**Tag maintenance:**
- Keep tag names consistent across recipes
- Use descriptive but concise tag names
- Avoid overly specific tags that would only apply to one recipe
- Prefer existing tags over creating new ones when possible