# SayLink — phone-friendly starter (Flutter + Supabase)

SayLink is a consent-based photo-link app scaffold with separate user accounts and private galleries.

## This package is configured for your Supabase project
- Project URL: `https://bhalgjmgipqaiwiwuapi.supabase.co`
- Uses the project's `sb_publishable_...` client key in `lib/supabase_config.dart`.
- Never add an `sb_secret_` key or service-role key to Flutter, web code, GitHub, or an APK.

## First setup in Supabase
1. You already ran the initial SQL from the earlier instructions.
2. Now run `supabase/migrate_existing.sql` in Supabase SQL Editor. It bridges the earlier `links(user_id, token)` table to the app's `links(owner_id, slug)` fields.
3. Keep the `saylink-photos` bucket private. This milestone does not upload photos yet.

## Run / build
Install Flutter stable on a computer or use a trusted cloud Flutter build environment. From this folder:

```bash
flutter pub get
flutter run
```

For a web deployment, first replace `publicBaseUrl` in `lib/supabase_config.dart` with the deployed HTTPS domain. The public visitor route `/l/{slug}` is not implemented yet, so generated links are placeholders until that page is built and deployed.

## Included in this milestone
- Email/password registration and sign-in.
- User profile creation / repair on sign-in.
- Authenticated dashboard.
- Create, copy, activate and deactivate unique personal links.
- Row Level Security for each user's profile and links.

## Not included yet
- Public visitor consent/camera page.
- Secure, one-time upload token and server-side Edge Function.
- Private gallery and signed image URLs.
- AdMob integration.

A visitor must explicitly agree before the browser requests camera access. Show a visible camera preview and capture only after consent. Never capture secretly or bypass browser permission.
