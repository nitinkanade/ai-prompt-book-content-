# AI Prompt Book Content Repository

This repository acts as the free CMS for the Android application **AI Prompt Book** (`in.ni18.aipromptbook`).

It is designed for GitHub Pages hosting and serves JSON prompt data plus WebP image assets that can be consumed directly by the Flutter app.

## Project Overview

AI Prompt Book Content Repository provides a simple static-content API:

- Prompt categories are defined in `categories.json`.
- App content metadata is defined in `version.json`.
- Each category has its own JSON file.
- Images are stored under `images/` using category-specific folders.

Expected GitHub Pages base URL:

```text
https://<github-username>.github.io/ai-prompt-book-content/
```

## Purpose

- Host prompt data for AI Prompt Book.
- Host image assets for category covers and prompt previews.
- Provide content through GitHub Pages without a paid CMS or backend server.

## Content Structure

```text
/
├── README.md
├── version.json
├── categories.json
├── wallpapers.json
├── anime.json
├── fantasy.json
├── characters.json
├── logos.json
├── images/
│   ├── wallpapers/
│   ├── anime/
│   ├── fantasy/
│   ├── characters/
│   └── logos/
└── docs/
```

### `version.json`

Contains high-level content metadata used by the app to detect updates.

Fields:

- `contentVersion`: Increment this number whenever content changes.
- `lastUpdated`: Date of the latest content update in `YYYY-MM-DD` format.
- `totalCategories`: Total number of active categories.
- `totalPrompts`: Total number of prompt records across all active categories.

### `categories.json`

Lists all active categories shown in the app.

Each category includes:

- `id`
- `name`
- `slug`
- `image`
- `promptCount`

### Category JSON Files

Each category file contains an array of prompt records. The Flutter app depends on these exact field names:

- `id`
- `title`
- `category`
- `imageUrl`
- `tool`
- `tags`
- `prompt`

Current category files:

- `wallpapers.json`
- `anime.json`
- `fantasy.json`
- `characters.json`
- `logos.json`

### Image Folders

Images are organized by category:

- `images/wallpapers/`
- `images/anime/`
- `images/fantasy/`
- `images/characters/`
- `images/logos/`

Use relative paths in JSON, for example:

```json
"imageUrl": "images/wallpapers/cyberpunk-city.webp"
```

## GitHub Pages Setup

1. Create a GitHub repository named `ai-prompt-book-content`.
2. Push this repository content to the default branch, usually `main`.
3. Open the repository on GitHub.
4. Go to **Settings** > **Pages**.
5. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
6. Select the `main` branch and the root folder `/`.
7. Click **Save**.

After GitHub Pages finishes deployment, content will be available at:

```text
https://<github-username>.github.io/ai-prompt-book-content/version.json
https://<github-username>.github.io/ai-prompt-book-content/categories.json
https://<github-username>.github.io/ai-prompt-book-content/wallpapers.json
https://<github-username>.github.io/ai-prompt-book-content/images/wallpapers/cyberpunk-city.webp
```

## Updating Content

1. Upload the WebP image to the matching folder under `images/`.
2. Add a new JSON entry to the matching category file.
3. Update `categories.json` if the category prompt count changes.
4. Update `version.json`:
   - Increment `contentVersion`.
   - Update `lastUpdated`.
   - Update `totalPrompts` if needed.
5. Validate the JSON files.
6. Commit and push changes.

## Content Guidelines

- Use WebP images.
- Keep each image under 500 KB.
- Use descriptive titles.
- Provide complete, useful prompts.
- Keep prompts family-friendly.
- Avoid copyrighted characters.
- Avoid trademarked brand references.
- Avoid adult, violent, hateful, or unsafe content.
- Keep content safe for Google Play Store and AdMob policies.

## Future Categories

The structure supports adding future categories without changing the existing API contract.

Planned category ideas:

- Product Photography
- Interior Design
- Architecture
- Fashion
- Social Media
- YouTube Thumbnails
- Tattoos

To add a category, create a new JSON file, add an image folder, add the category to `categories.json`, and update `version.json`.

