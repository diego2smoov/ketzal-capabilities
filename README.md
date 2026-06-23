# Ketzal Unmanned — Website

Source for [ketzalunmanned.com](https://ketzalunmanned.com).

## Pages

| File | URL (on Netlify) |
|------|------------------|
| `index.html` | `/` — Capabilities overview (live homepage) |
| `ketzal-landing.html` | `/ketzal-landing.html` — Main landing page |
| `journal.html` | `/journal.html` |
| `Landing-Pages/` | Sector-specific landing pages |

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