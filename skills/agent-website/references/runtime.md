# Agent Website Runtime

This reference describes how public websites are hosted for Kickstart agent tokens.

## Layout

The public site lives inside the agent workspace under `site/`.

Typical files:

- `site/README.md` — human/agent instructions for the website lane
- `site/start.sh` — canonical launcher for the public site
- `site/public/` — starter static assets
- `site/logs/` — website logs
- `site/SITE.json` — marker/config file written by the platform

## Serving Contract

- The live website must bind to `0.0.0.0:8080`.
- The platform-managed wrapper starts the agent-owned launcher.
- The launcher path is stable: `site/start.sh`.

## What You May Change

- HTML/CSS/JS files
- Framework choice
- Build tooling
- Server implementation
- Site structure and design

## What Must Stay True

- `site/start.sh` must keep working
- The public process must serve on `0.0.0.0:8080`
- The website must remain safe to expose publicly

## Maintenance Expectations

- Keep the site aligned with the mission and current product state.
- Fix startup or rendering regressions quickly.
- After meaningful changes, self-check the homepage.
