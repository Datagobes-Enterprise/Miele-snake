# Miele-snake
simple snake game in premium Miele theme

## Leaderboard (Supabase)

The leaderboard needs valid Supabase credentials.

Note: GitHub secret names are `SUPABASE_URL` and `SUPABASE_ANON_KEY`; `YOUR_SUPABASE_URL` and `YOUR_SUPABASE_ANON_KEY` are template placeholders in `index.html`.

Config is read in this order:
1. `window.SUPABASE_URL` and `window.SUPABASE_ANON_KEY`
2. `localStorage` keys: `mieleSnakeSupabaseUrl`, `mieleSnakeSupabaseAnonKey`
3. Fallback placeholders in `index.html`

If config is missing/invalid, the leaderboard shows:
`Leaderboard unavailable (Supabase not configured)`

Quick browser setup for local testing:

```js
localStorage.setItem('mieleSnakeSupabaseUrl', 'https://YOUR_PROJECT.supabase.co');
localStorage.setItem('mieleSnakeSupabaseAnonKey', 'YOUR_ANON_KEY');
location.reload();
```

### GitHub Pages deploy note

GitHub secret updates do **not** trigger a Pages deploy by themselves.
After changing `SUPABASE_URL` or `SUPABASE_ANON_KEY`, run the workflow manually (`Actions` → `Deploy Snake Game` → `Run workflow`) or push a commit touching `index.html`.

The deploy workflow now fails fast if Supabase secrets are missing/invalid, instead of publishing a broken build.
