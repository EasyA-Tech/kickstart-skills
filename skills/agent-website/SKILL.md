---
name: agent-website
description: Maintain public websites for Kickstart agent tokens hosted inside the agent's Fly Sprite. Use when creating, repairing, redesigning, or verifying the `site/` workspace, or when the user mentions the agent website, homepage, landing page, or public site.
metadata:
  author: easya-tech
  version: "1.0"
---

# Agent Website

Use this skill to maintain the public website that lives inside the agent's Sprite.

## Quick Start

1. Inspect the current website workspace:
   - `site/README.md`
   - `site/start.sh`
   - `site/public/`
2. Preserve the runtime contract:
   - the public server must bind to `0.0.0.0:8080`
   - `site/start.sh` is the canonical launcher
3. Make the requested site change.
4. Self-check that the homepage still loads and reflects the latest mission/product state.

## Runtime Contract

- The website lives in `site/`.
- The platform-managed wrapper will run `site/start.sh`.
- You may replace the starter stack with any framework or server you want.
- If you change frameworks, keep `site/start.sh` working.
- If the website is stale, broken, or inconsistent with the mission, fix it.

## Preferred Workflow

1. Read `site/README.md` and the current site files before editing.
2. Decide whether the current stack is still the simplest workable option.
3. Update content, styling, or framework files as needed.
4. Keep changes focused on the website lane. Do not edit unrelated runtime files unless the task explicitly requires it.
5. Verify the homepage and any changed paths after edits.

## Common Tasks

### Refresh content

- Update the headline, mission, roadmap, or calls to action.
- Reflect product changes promptly after major mission progress.

### Repair a broken site

- Fix startup issues in `site/start.sh`.
- Ensure the live process still serves on `0.0.0.0:8080`.
- Prefer the smallest fix that restores service.

### Replace the starter site

- You may switch to React, Next standalone, Express, or another stack.
- Keep the project self-contained under `site/`.
- Make sure `site/start.sh` remains the stable entrypoint.

## Guardrails

- Do not expose private keys, API tokens, or other secrets through the public site.
- Do not remove the ability to start the site from `site/start.sh`.
- Do not change the serving port away from `8080`.

## Additional Resources

- For the detailed runtime contract, see [references/runtime.md](references/runtime.md)
