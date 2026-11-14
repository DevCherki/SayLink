# SayLink setup (mobile-friendly instructions)

## Supabase
1. Open your Supabase project.
2. Open SQL Editor → New query.
3. Paste and run the full file `supabase/migrate_existing.sql`.
4. Keep Storage bucket `saylink-photos` private.

## GitHub from your phone
1. Download and extract this ZIP on your phone.
2. In your `saylink` GitHub repository choose Add file → Upload files.
3. Upload the extracted files and folders (not the ZIP alone), preserving folder names such as `lib` and `supabase`.
4. Commit the upload.

## Build
This project is Flutter. A phone browser alone cannot compile Flutter into an APK locally. Use a trusted cloud Flutter build service or a computer for `flutter pub get` and Android build.

## Configuration
The Supabase URL and publishable client key are already placed in `lib/supabase_config.dart`. The publishable key is intended for client apps and is protected by database RLS. Never put a `sb_secret_` key in this file.

Change `publicBaseUrl` after you deploy the web app. Until then, copied visitor links are not live.
