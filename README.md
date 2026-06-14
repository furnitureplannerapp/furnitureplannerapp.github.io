# README Update – GitHub Pages Deployment Guide

Update the README section describing the GitHub Pages website and legal documentation to reflect the current state of Furniture Planner.

## GitHub Pages Deployment Guide

The `docs/` directory contains the static public website for Furniture Planner, including:

* Marketing page
* Privacy Policy
* Terms of Use
* Support page
* Subscription information
* Legal information required for App Store distribution

### Publish With GitHub Pages

1. Push the repository to GitHub.
2. Open Repository Settings.
3. Navigate to **Pages**.
4. Set the source to:

   * Branch: `main`
   * Folder: `/docs`
5. Save and wait for deployment to complete.

### Production URLs

Marketing URL

https://furnitureplannerapp.github.io/

Privacy Policy

https://furnitureplannerapp.github.io/privacy-policy/

Terms of Use

https://furnitureplannerapp.github.io/terms-of-use/

Support

https://furnitureplannerapp.github.io/support/

## App Store Connect Configuration

Use the following URLs in App Store Connect:

| Field              | URL                                                   |
| ------------------ | ----------------------------------------------------- |
| Marketing URL      | https://furnitureplannerapp.github.io/                |
| Privacy Policy URL | https://furnitureplannerapp.github.io/privacy-policy/ |
| Support URL        | https://furnitureplannerapp.github.io/support/        |
| Terms of Use URL   | https://furnitureplannerapp.github.io/terms-of-use/   |

## Localization

English pages are treated as canonical URLs.

Localized versions are available under:

* `/pl/`
* `/de/`
* `/es/`
* `/fr/`

The application should continue linking to the root URLs to ensure stable App Store metadata and external references.

Users may switch language directly on the website.

## Legal Documentation Maintenance

Whenever application functionality changes, review and update:

* Privacy Policy
* Terms of Use
* Subscription information
* Trial limitations
* iCloud synchronization information
* Diagnostic and analytics disclosures

The legal documents must always reflect the actual behavior of the application.

## Firebase Services Disclosure

Furniture Planner currently uses Firebase services for:

### Firebase Analytics

Used to understand how users interact with the application and which features are most frequently used.

### Firebase Crashlytics

Used to collect crash reports and diagnostic information to improve application stability and reliability.

### Firebase Remote Config

Used to:

* Configure maintenance mode
* Configure minimum supported build version
* Display update notifications
* Enable or disable selected features remotely

Firebase is not used to store furniture projects or user-generated furniture designs.

## Data Storage

Furniture Planner stores data using:

* Local device storage
* SwiftData
* UserDefaults
* iCloud (when enabled by the user and available under the active subscription plan)

Furniture projects are not stored in Firebase.

## Subscription Model

Furniture Planner currently offers:

### Free

* Up to 3 projects
* Basic functionality

### Premium

* Unlimited projects
* 3D Preview
* AR Preview
* PDF generation
* Cost estimation
* iCloud synchronization

### Studio

Includes everything from Premium plus:

* Client management
* Company branding
* Production documentation
* CSV exports
* Advanced business features

### Studio Trial

New users receive access to Studio features for the first 3 created projects.

After the trial limit is reached, access falls back to the Free plan unless an active subscription is purchased.

## Website Principles

Keep the website lightweight and maintainable:

* Static HTML/CSS
* No backend
* No user authentication
* No project storage
* Minimal JavaScript

The website should remain suitable for GitHub Pages hosting without additional infrastructure.

## Custom Domain

To add a custom domain:

1. Add a `CNAME` file inside `docs/`
2. Configure DNS according to GitHub Pages documentation
3. Update:

   * App Store Connect URLs
   * Website links
   * Legal documents
   * AppLinks.swift
   * README documentation

## Release Checklist

Before each public release verify:

* Privacy Policy is up to date
* Terms of Use are up to date
* Subscription information is correct
* Trial limitations are correct
* Firebase disclosures are accurate
* Support links are valid
* App Store Connect URLs match production URLs
* GitHub Pages deployment is successful
