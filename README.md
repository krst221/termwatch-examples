# termwatch-examples

Example configuration for [TermWatch](https://termwatch.dev) — terminal-native uptime monitoring.

## What this is

This repo shows how to manage your uptime monitors as code using YAML and deploy
them automatically with GitHub Actions. Edit `monitors.yaml`, push, done.

## Setup

1. [Create a TermWatch account](https://termwatch.dev) (`termwatch register`)
2. Fork this repo
3. Add your API key as a repository secret: `Settings → Secrets → TERMWATCH_API_KEY`
4. Edit `monitors.yaml` with your actual URLs
5. Push to main — the workflow deploys automatically

## How it works

- `monitors.yaml` is the single source of truth for your monitors
- Every push to `main` that changes `monitors.yaml` triggers the deploy workflow
- `termwatch validate` catches config errors before they reach production
- `termwatch deploy` syncs the YAML to TermWatch (full sync — monitors not in the file are deleted)

## Free tier

5 monitors, 5-minute check intervals, Slack + email alerts. No credit card required.
