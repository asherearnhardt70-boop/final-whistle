# Final Whistle

A responsive sports-trivia website built as a static site for GitHub Pages, with Supabase email/password authentication and score storage.

## Included
- Football, basketball, baseball, soccer, and mixed trivia
- Ten-question rounds, scoring, and answer feedback
- Responsive desktop/mobile layout
- Supabase email/password sign-up and login (after configuration)
- Saved scores and a personal score history/leaderboard

## Connect your Supabase project
The game works without Supabase, but accounts and saved scores stay disabled until you add your own project settings.

1. In Supabase, open your project.
2. Go to **Project Settings → API** (the API Keys section may be labeled **API Keys**).
3. Copy the **Project URL** and the **publishable key** (or legacy anon/public key).
4. In this repository, open `index.html`, click the pencil/edit icon, and find `YOUR_SUPABASE_PROJECT_URL` and `YOUR_SUPABASE_PUBLISHABLE_KEY`.
5. Replace those two placeholder values with your own Project URL and publishable key, then commit the change.

A publishable/anon key is designed to be used in browser code. **Never use or publish a service-role key or any secret key.** Passwords are handled by Supabase Auth and are not stored by this website.

## Create the scores table
1. In Supabase, open **SQL Editor → New query**.
2. Copy the contents of `supabase-setup.sql` into the editor.
3. Click **Run**.

The SQL creates a scores table and enables Row Level Security. Players can insert and read only their own scores. This first version therefore displays a personal scores list, not a public all-player leaderboard. A public leaderboard should be added through a privacy-safe view or database function that does not expose account IDs or emails.

## Publish with GitHub Pages
1. Open this repository's **Settings** tab.
2. Select **Pages** in the left sidebar.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch **main** and folder **/(root)**, then Save.
5. Wait for GitHub Pages to publish. The site URL will appear in Settings → Pages.

The site is a single `index.html`; no local installation or build step is required.
