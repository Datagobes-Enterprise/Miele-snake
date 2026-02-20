# Miele-snake
simple snake game in premium Miele theme

## Leaderboard (Supabase)

The leaderboard needs valid Supabase credentials.

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
