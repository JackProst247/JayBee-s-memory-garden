# JayBee's Memory Garden

A private, romantic memory garden for two invited people.

## Features
- Responsive dreamy garden with floating picture frames, hanging polaroids, flowers and firefly ambience.
- Email + password authentication using Supabase Auth.
- Invite-only allowlist for exactly the two intended accounts.
- Private photo storage with short-lived signed URLs.
- Add memories with a photo, title, date and note.

## Supabase setup
1. Create a Supabase project.
2. Run [supabase/schema.sql](supabase/schema.sql) in the Supabase SQL Editor.
3. Create a Storage bucket named `memories` and set it to **Private**.
4. Turn OFF public sign-ups in Authentication settings.
5. Invite the two intended email addresses from Authentication > Users > Invite user.
6. After each invite is accepted, copy the exact user UUIDs from Authentication > Users and insert both rows into `public.garden_members`. Example SQL is at the end of `supabase/schema.sql`.
7. In `index.html`, replace `YOUR_SUPABASE_PROJECT_URL` and `YOUR_SUPABASE_ANON_KEY` with the Supabase Project URL and anon/public key. Do not use the service_role key.
8. Add the published website URL to Supabase Authentication > URL Configuration > Redirect URLs.

## Publish
Enable GitHub Pages for this repository:
- Settings > Pages
- Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`

The site will then be available at:
`https://jackprost247.github.io/JayBee-s-memory-garden/`

## Privacy
The GitHub repository hosts only frontend code and SQL setup instructions. Do not commit personal photos, passwords, API secrets, or the Supabase service_role key. Photos are stored in a private Supabase bucket and access is controlled by database and Storage policies. The site is not fully private until Supabase is configured and the two accounts are allowlisted.
