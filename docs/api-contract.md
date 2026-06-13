# API Contract

The Android app depends on stable JSON field names.

## Category Prompt Record

Every record in a category JSON file must include:

```json
{
  "id": 1,
  "title": "Prompt Title",
  "category": "category-slug",
  "imageUrl": "images/category/image-name.webp",
  "tool": "Midjourney",
  "tags": [
    "tag-one",
    "tag-two"
  ],
  "prompt": "Complete family-friendly AI image prompt."
}
```

Do not rename these fields unless the Flutter app is updated at the same time.

## Category File Rules

- Use an array at the top level.
- Keep `id` values unique within each category file.
- Keep `category` equal to the matching category slug.
- Use relative paths for `imageUrl`.
- Use WebP images.

## Version Rules

Update `version.json` whenever content changes.

- Increment `contentVersion`.
- Update `lastUpdated`.
- Keep `totalCategories` and `totalPrompts` accurate.

