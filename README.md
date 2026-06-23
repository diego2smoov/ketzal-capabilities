# Ketzal Unmanned — Website

Source for [ketzalunmanned.com](https://ketzalunmanned.com).

## Partner guide

**Start here → [PARTNER-GUIDE.md](PARTNER-GUIDE.md)**

Diego and Noah: bookmark that file on GitHub. It has live preview URLs, git workflow, and revert steps.

## Quick links

| What | URL |
|------|-----|
| Production | https://ketzalunmanned.com |
| Capabilities backup | https://ketzalunmanned.com/capabilities |
| Design mirror | https://ketzalunmanned.com/preview |
| Sandbox (push to `preview` branch) | https://deploy-preview-1--ketzalcapability.netlify.app |
| GitHub repo | https://github.com/diego2smoov/ketzal-capabilities |

## Pages

| File | URL (on Netlify) |
|------|------------------|
| `index.html` | `/` — Homepage |
| `index-capabilities.html` | `/capabilities` or `/production` — frozen capabilities statement |
| `index-preview.html` | `/preview` — mirror of homepage |
| `privacy-policy.html` | `/privacy` |
| `terms-of-use.html` | `/terms` |
| `contact-thanks.html` | `/contact-thanks` |
| `ketzal-landing.html` | `/landing` |
| `journal.html` | `/journal.html` |
| `Landing-Pages/` | Sector-specific landing pages |

## Branches

| Branch | Purpose |
|--------|---------|
| `main` | Production — live at ketzalunmanned.com |
| `preview` | Sandbox — experiment before merging to `main` |

Pushes to `main` auto-deploy via Netlify. See [PARTNER-GUIDE.md](PARTNER-GUIDE.md) for full workflow.

## Revert to capabilities homepage

```bash
git checkout main
git pull
cp index-capabilities.html index.html
git add index.html
git commit -m "Restore capabilities homepage"
git push
```