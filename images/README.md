# Recipe Images Guide

This directory contains images for the recipe stories to make them more engaging and easier to follow.

## Directory Structure

Images are organized to match the recipe structure:

```
images/
└── YYYY/
    └── MM/
        └── DD/
            └── recipe-name/
                ├── featured.svg    # Main recipe image (displayed at top)
                ├── step-1.svg      # Step instruction images
                ├── step-2.svg
                └── ...
```

## Image Types

### Featured Images
- **Filename**: `featured.svg`
- **Purpose**: Main recipe image displayed at the top of each recipe
- **Size**: Recommended 600x400 pixels
- **Format**: SVG preferred for crisp display at all sizes

### Step Images
- **Filename**: `step-N.svg` (where N is the step number)
- **Purpose**: Visual aids for specific cooking steps
- **Size**: Recommended 400x300 pixels
- **Format**: SVG preferred

## Adding Images to Recipes

### Automatic Featured Images
Featured images are automatically displayed if they exist. Just place a `featured.svg` file in the recipe's image directory.

### Manual Step Images
Add step images in the recipe markdown using:

```markdown
<div class="recipe-step-image">
<img src="{{ '/images/YYYY/MM/DD/recipe-name/step-N.svg' | relative_url }}" alt="Step description" class="img-fluid">
</div>
```

## Creating Images

The current sample images are simple SVG illustrations that:
- Use food-appropriate colors
- Include the recipe title
- Show key visual elements of the dish
- Are clean and appetizing in appearance

For production use, consider:
- High-quality food photography
- Consistent styling and lighting
- Step-by-step process photos
- Ingredient photos when helpful

## Technical Details

- Images are automatically copied to the Jekyll `_site` during build
- CSS styling provides responsive display and pleasant shadows
- Images gracefully degrade if missing (won't break the layout)
- All paths use Jekyll's `relative_url` filter for GitHub Pages compatibility