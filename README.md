# searxng-ping
Live Demo:https://sciresearch1-searxng.hf.space/

Keeps a SearXNG HuggingFace Space alive by pinging it every 6 hours.

## Setup

1. Fork or clone this repo (must be **public** to use free GitHub Actions minutes)
2. Go to **Settings → Secrets and variables → Actions**
3. Add a secret: `SEARXNG_URL` = your HuggingFace Space URL (e.g. `https://YOUR-USERNAME-searxng.hf.space`)

## Workflows

| Workflow | Schedule | Purpose |
|----------|----------|---------|
| `ping.yml` | Every 6 hours | Pings SearXNG to prevent HF Space from sleeping |
| `keepalive.yml` | 1st of every month | Commits a timestamp so GitHub doesn't disable scheduled workflows after 60 days |

## Notes

- HuggingFace free Spaces sleep after ~15 minutes of inactivity — this ping prevents that
- The monthly commit is required because GitHub disables scheduled Actions in repos with no activity for 60 days
- This repo should stay public so it doesn't consume private Actions minutes
