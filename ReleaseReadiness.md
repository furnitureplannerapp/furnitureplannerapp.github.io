# Release Readiness: Subscriptions and iCloud

This checklist covers the non-code work required before StoreKit subscriptions and iCloud sync are production-ready.

## App Store Connect subscriptions

- Sign the Paid Apps Agreement and complete tax and banking information.
- Create one subscription group for Furniture Planner.
- Add these auto-renewable subscription products:
  - `premium_monthly`
  - `premium_yearly`
  - `ultra_monthly`
  - `ultra_yearly`
- Confirm that Premium products map to the Premium tier and Ultra products map to the Ultra / Studio tier.
- Configure prices, durations, localization, descriptions, and App Review metadata for each product.
- Test purchases, cancellation, pending purchases, restore purchases, upgrades, and downgrades in Sandbox/TestFlight.
- Confirm that debug/mock plan switching is unavailable in App Store release builds.

## Xcode project

- The project has the In-App Purchase capability enabled.
- The shared scheme uses `Furniture Planner/Resources/FurniturePlannerSubscriptions.storekit` for local StoreKit testing.
- The app continues to use StoreKit 2 only.

## iCloud / CloudKit

- Confirm the App ID has iCloud + CloudKit enabled.
- Confirm the CloudKit container is `iCloud.com.marcinkaliniak.furnitureplanner`.
- Verify the app entitlement points to the same CloudKit container.
- Test iCloud account states:
  - signed in,
  - signed out,
  - restricted,
  - temporarily unavailable,
  - offline.
- Test sync across at least two real devices using the same Apple ID.
- In CloudKit Dashboard, validate record types in Development.
- Deploy the CloudKit schema to Production before App Store release.

## Data safety

- Backup/export/import must keep working independently from iCloud sync.
- Local data must not be deleted when iCloud is unavailable or returns an empty remote state.
- Verify last-write-wins behavior with `updatedAt`.
- Verify soft deletes via `deletedAt`.
- Verify custom material textures in backup/import and decide whether CloudKit sync should upload them as assets in a later phase.

## Test matrix

- Fresh install, Free plan, iCloud off.
- Fresh install, Premium purchase, restore purchase.
- Fresh install, Ultra purchase, restore purchase.
- Upgrade Premium to Ultra.
- Downgrade Ultra to Premium.
- App launch offline with last known active subscription.
- iCloud sync on, create/edit/delete project on device A, verify device B.
- iCloud sync disabled, local edits continue to work.
- Backup export/import after subscriptions and iCloud settings exist.
