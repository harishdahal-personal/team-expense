# Sathibhai Expense Tracker

A single-page web app for a group of friends who play sport together (built for badminton). It tracks deposits into a shared fund, splits court hire, shuttle, racket and maintenance costs between the players who took part, and flags anyone whose balance is running low so you can ask them to top up.

No build step, no dependencies, no server. Everything is in `index.html`.

## How it works

- **Deposits** add to a player's balance.
- **Expenses** are split equally between the players ticked as taking part. If a player paid out of their own pocket, set "Paid by" to that player and they are credited the full amount.
- **Alerts** flag anyone below the alert level (default 20, change it under Alert settings). Each flagged player gets a suggested top-up covering about 4 weeks of their usual spending, plus a "Copy reminder" button for pasting into your group chat.

## Publish with GitHub Pages

1. Create a new repository on GitHub and upload `index.html` and `README.md`.
2. Open the repository's **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
4. After a minute the site is live at `https://<your-username>.github.io/<repository-name>/`.

## Where the data lives

Data is saved in the browser's local storage on each device. That has two consequences:

- Each person who opens the public link starts with an empty tracker and sees only their own entries. Nothing is uploaded anywhere, so it is safe to make the site public.
- Phones and computers do not share data with each other. To move your data, use **Backup and restore**: download a backup file on one device and restore it on another. Clearing site data in the browser erases the tracker, so keep a backup.

If the group needs one tracker that everyone updates live, it needs a shared backend (for example Firebase or Supabase). The data layer in `index.html` is isolated in the functions `addDoc`, `delDoc`, `patchDoc` and `saveSettings`, so it can be swapped.

## Fonts

The page loads Archivo and IBM Plex from Google Fonts. If they are blocked it falls back to system fonts.
