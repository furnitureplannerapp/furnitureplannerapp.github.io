# GitHub Pages Deployment Guide

The `docs/` directory contains the static release/legal website for Furniture Planner.

## Publish With GitHub Pages

1. Push the repository to GitHub.
2. Open repository settings.
3. Go to Pages.
4. Set source to the `main` branch and `/docs` folder.
5. Save and wait for GitHub Pages to publish.

Expected URLs:

- Marketing URL: `https://furnitureplannerapp.github.io/`
- Privacy Policy URL: `https://furnitureplannerapp.github.io/privacy-policy/`
- Terms URL: `https://furnitureplannerapp.github.io/terms-of-use/`
- Support URL: `https://furnitureplannerapp.github.io/support/`

## App Store Connect Fields

Use these URLs in App Store Connect:

- Privacy Policy URL: `https://furnitureplannerapp.github.io/privacy-policy/`
- Support URL: `https://furnitureplannerapp.github.io/support/`
- Marketing URL: `https://furnitureplannerapp.github.io/`
- Terms URL: `https://furnitureplannerapp.github.io/terms-of-use/`

## Localized Pages

English root pages are the fallback. Localized versions live in:

- `/pl/`
- `/de/`
- `/es/`
- `/fr/`

The app links to the root URLs so App Store metadata has stable canonical links. Users can switch language from the website header.

## Custom Domain Later

To add a custom domain:

1. Add a `CNAME` file inside `docs/` with the domain.
2. Configure DNS according to GitHub Pages documentation.
3. Update `AppLinks.swift`, App Store Connect URLs and this guide.

## Release Notes

Keep this website lightweight:

- No backend.
- No analytics or tracking scripts.
- No heavy JavaScript framework.
- Update legal text before public release if subscription, sync or diagnostic behavior changes.
