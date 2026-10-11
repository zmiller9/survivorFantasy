[README.md](https://github.com/user-attachments/files/33296170/README.md)
# Survivor Fantasy League

A static website that shows standings and score breakdowns from two CSV files. There is no build step and nothing to install.

## Files

```
index.html          the whole site (HTML, CSS, JavaScript)
data/drafts.csv     who drafted whom
data/events.csv     every scoring event
```

## Data format

**drafts.csv** has one row per draft pick (7 members x 3 picks = 21 rows).

```
member,contestant
Dana,Ivan P.
Dana,Rafe J.
```

**events.csv** has one row per scoring event. Add rows after each episode.

```
episode,contestant,action,points
1,Alex R.,Survives tribal council,1
3,Ivan P.,Wins individual immunity,5
```

Rules to keep in mind:

- Contestant names must match `drafts.csv` exactly, including spelling and punctuation. Unmatched names are skipped and the site shows a warning.
- `episode` and `points` must be numbers. Points can be negative.
- Action names are free text. Keep them consistent (for example always "Wins individual immunity"), because the "By action" chart groups by exact text.
- Member colours follow the order members first appear in `drafts.csv`.

The sample data is made up. Replace both files with your real league.

## Publish for free on GitHub Pages

1. Create a free GitHub account and a new public repository.
2. Click **Add file > Upload files**, then drag in `index.html` and the `data` folder, and commit.
3. Go to **Settings > Pages**. Under "Build and deployment", choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or two your site is live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`.

## Update each week

1. Open `data/events.csv` in your repository and click the pencil icon.
2. Paste in the new rows, or upload a replacement file, and commit.
3. The site refreshes within a minute or two.

## Preview on your computer

Browsers block loading CSV files when you double-click `index.html`. From this folder, run:

```
python3 -m http.server
```

Then open http://localhost:8000.

## Customising

- **Title:** edit the `<h1>` and `<title>` in `index.html`.
- **Colours:** edit the `--paper`, `--ink`, `--ember` values at the top of the stylesheet and the `MEMBER_COLORS` list in the script.
- **Private site:** GitHub Pages is public. For a password, host the same files on Netlify or Cloudflare Pages with access protection.
