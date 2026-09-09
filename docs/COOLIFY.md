# Hosting the marketing demo with Coolify

The public demo is a static site. It does not run the desktop service or access visitors' local skills or CLI accounts.

Configure a Coolify Static application from `ldgraham92/skill-desk`, branch `main`, and use `/marketing` as the base directory. The publish directory is `/` relative to that base directory; no build command is required. Set the domain to `https://skilldesk.lgraham.ca` and point its DNS at your Coolify host. Alternatively, configure the repository root and `/marketing` as the publish directory if your Coolify version uses that layout.

Deploying the repository's marketing directory deploys the versioned `index.html` with its inline CSS/JS. Enable deploy-on-push for this application to keep it current as `main` changes. Download links point to GitHub Releases, where desktop installers live.

Do not deploy `scripts/skill_desk.py` as the public site. That service manages local files and belongs on each user's computer.
