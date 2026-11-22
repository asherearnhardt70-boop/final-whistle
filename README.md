# Final Whistle

A responsive sports-trivia website built as a static site for GitHub Pages, with Supabase email/password authentication and score storage.

## What's included
- Email sign-up and login through Supabase Auth
- Sports trivia categories: Football, Basketball, Baseball, Soccer, and All Sports
- Ten-question rounds, scoring, and feedback
- Saved scores and a top-scores view
- Responsive layout for desktop and mobile

## Supabase setup
The frontend uses the project's **publishable** key. A Supabase publishable/anon key is intended for browser use; never put a service-role or secret key in this repository.

The app expects a table named `scores` with at least:
- `user_id` (uuid, references `auth.users.id`)
- `score` (integer)
- `created_at` (timestamp, optional; used for sorting only if present)

Enable Row Level Security. Users should be allowed to insert and read only their own rows. For a public all-player leaderboard, add a carefully scoped read policy or a server-side view/RPC that exposes only the score and a non-identifying display name. The current client masks other users as “Player”.

## Publish with GitHub Pages
1. Open the repository's **Settings** tab.
2. Select **Pages** in the left sidebar.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch **main** and folder **/(root)**, then Save.
5. Wait for GitHub Pages to publish. The site URL will be shown in Settings → Pages.

The site is a single `index.html`; no local installation or build step is required.
