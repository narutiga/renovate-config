# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for my repositories.

## Usage

Add a `renovate.json` at the repo root:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>narutiga/renovate-config"]
}
```

## What it does

- Weekly updates (early Monday, Asia/Tokyo), all non-major updates grouped into a single PR
- Automerge for minor/patch once CI passes — **except** 0.x versions and majors, which require manual review
- npm packages must be at least 3 days old before updating (supply-chain protection)
- Security updates run anytime, labelled `security`
- Monthly lock file maintenance (automerged)
- Based on `config:best-practices` (pinning, GitHub Actions digest pinning, dependency dashboard)

> **Note:** repos must have a PR-triggered CI workflow before enabling Renovate — automerge with zero checks merges immediately.
