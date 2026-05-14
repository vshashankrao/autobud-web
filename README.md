# autobud-web

Static site for AutoBud:

- `/` — splash
- `/privacy` — Privacy Policy (App Store metadata)
- `/support` — Support page (App Store metadata)
- `/auth/confirm` — Supabase email confirmation landing
- `/.well-known/apple-app-site-association` — Universal Links (iOS)
- `/.well-known/assetlinks.json` — App Links (Android)

Deployed to Cloudflare Workers (static-assets) at
https://autobud.vshashankrao.workers.dev.

## Updating App Links fingerprints

`assetlinks.json` currently lists the **debug keystore** SHA-256. When the
release keystore is created (for Play Store submission), add its SHA-256 to
the `sha256_cert_fingerprints` array for each package. Both can coexist.

## Updating Universal Links app IDs

`apple-app-site-association` lists both customer and mechanic bundle IDs
under Team ID `9D997PR967`. If either changes, update both files and
re-add the `applinks:` entitlement on the affected target.
