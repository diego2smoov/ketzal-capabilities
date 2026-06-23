# Ketzal Unmanned — Website

Source for [ketzalunmanned.com](https://ketzalunmanned.com).

## Pages

| File | URL (on Netlify) |
|------|------------------|
| `index.html` | `/` — Homepage (capabilities on `main`, experimental on `preview`) |
| `index-capabilities.html` | `/capabilities` or `/production` — frozen capabilities statement (always available) |
| `ketzal-landing.html` | `/ketzal-landing.html` — Landing page source |
| `journal.html` | `/journal.html` |
| `Landing-Pages/` | Sector-specific landing pages |

## Branches

| Branch | What it does | Live URL |
|--------|--------------|----------|
| `main` | **Production** — capabilities overview at `/` | ketzalunmanned.com |
| `preview` | **Sandbox** — experiment with a new homepage | `preview--<site-name>.netlify.app` (enable in Netlify → Branch deploys) |

### Experiment with a new homepage (safe)

```bash
git checkout preview
git pull
# edit index.html freely
git add index.html
git commit -m "Try new hero section"
git push -u origin preview
```

Production (`main`) is untouched. Preview gets its own Netlify URL.

### Revert production to capabilities (instant)

```bash
git checkout main
git pull
cp index-capabilities.html index.html
git add index.html
git commit -m "Restore capabilities homepage"
git push
```

Or one-liner without a commit message prompt: `git checkout main -- index-capabilities.html` then copy to index.html.

### Go live with the new design

When preview looks good, merge into production:

```bash
git checkout main
git pull
git merge preview
git push
```

To undo a bad go-live: restore from `index-capabilities.html` (steps above).

## Local editing

1. Clone the repo:
   ```bash
   git clone https://github.com/diego2smoov/ketzal-capabilities.git
   cd ketzal-capabilities
   ```
2. Open any `.html` file in VS Code and use **Live Preview** (or open directly in a browser).
3. Commit and push when ready — Netlify auto-deploys from `main`.

## Collaboration workflow

1. **Pull before you edit** — `git pull` keeps you in sync with your partner's changes.
2. **Make changes** — edit HTML/CSS directly in the files.
3. **Commit and push**:
   ```bash
   git add .
   git commit -m "Describe what you changed"
   git push
   ```
4. Netlify rebuilds automatically (usually under 1 minute). Check the deploy log in the Netlify dashboard.

For bigger changes, create a branch and open a Pull Request on GitHub so you can review before merging to `main`.

## Deployment

Hosted on **Netlify**, connected to this GitHub repo. Pushes to `main` trigger a new deploy.

To connect (one-time setup in Netlify):
1. Log in at [app.netlify.com](https://app.netlify.com)
2. **Add new site → Import an existing project → GitHub**
3. Select `diego2smoov/ketzal-capabilities`
4. Build settings: publish directory = `.` (root), no build command
5. Under **Domain management**, confirm `ketzalunmanned.com` is attached

## Access

Collaborators with **Write** access can push directly. Ask Diego to invite you at your `@ketzalunmanned.com` email if you need access.