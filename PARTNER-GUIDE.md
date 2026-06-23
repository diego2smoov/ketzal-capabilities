# Ketzal Website — Partner Guide

Quick reference for Diego and Noah. Bookmark this page on GitHub:

**https://github.com/diego2smoov/ketzal-capabilities/blob/main/PARTNER-GUIDE.md**

---

## Live URLs

| What | URL |
|------|-----|
| **Production site** (capabilities statement — do not break) | https://ketzalunmanned.com |
| **Capabilities backup** (always available) | https://ketzalunmanned.com/capabilities |
| **New design preview** | https://ketzalunmanned.com/preview |
| **Sandbox preview** (updates when you push to `preview` branch) | https://deploy-preview-1--ketzalcapability.netlify.app |
| **GitHub repo** | https://github.com/diego2smoov/ketzal-capabilities |
| **Open PR** (review before going live) | https://github.com/diego2smoov/ketzal-capabilities/pull/1 |

---

## First-time setup

```bash
git clone https://github.com/diego2smoov/ketzal-capabilities.git
cd ketzal-capabilities
```

Open the folder in VS Code (or Cursor). Use **Live Preview** to edit locally before pushing.

---

## Editing the new homepage (safe — production unchanged)

Always work on the **`preview`** branch:

```bash
git checkout preview
git pull

# edit index.html
git add index.html
git commit -m "Describe what you changed"
git push
```

Wait ~1 minute, then refresh:

**https://deploy-preview-1--ketzalcapability.netlify.app**

Production at ketzalunmanned.com stays on the capabilities page until we deliberately merge.

---

## Daily rules

1. **`git pull` before you edit** — avoids conflicts with your partner's changes.
2. **Edit on `preview` branch** for the new homepage experiments.
3. **Only merge to `main`** when both of you agree the new design is ready to go live.
4. **Write clear commit messages** — e.g. `"Update hero headline"` not `"fixes"`.

---

## Go live with the new design

When you're both happy with the preview:

```bash
git checkout main
git pull
git merge preview
git push
```

Or merge [PR #1](https://github.com/diego2smoov/ketzal-capabilities/pull/1) on GitHub.

---

## Revert to capabilities statement

If production needs to go back immediately:

```bash
git checkout main
git pull
cp index-capabilities.html index.html
git add index.html
git commit -m "Restore capabilities homepage"
git push
```

Live site reverts in about a minute.

---

## Key files

| File | Purpose |
|------|---------|
| `index.html` | Homepage — capabilities on `main`, new design on `preview` |
| `index-capabilities.html` | Frozen backup of the live capabilities page |
| `index-preview.html` | Serves https://ketzalunmanned.com/preview |
| `ketzal-landing.html` | Older landing page variant |
| `journal.html` | Journal page |
| `Landing-Pages/` | Sector-specific landing pages |
| `assets/` | Images |

---

## Netlify dashboard

- **Site:** https://app.netlify.com (look for `ketzalcapability`)
- **Deploys tab** — see build status after each push
- **Domain** — ketzalunmanned.com points at `main` branch deploys

---

## Need help?

Ping Diego, or open a GitHub Issue on the repo.