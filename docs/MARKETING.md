# Deploy the marketing website

The public website is `marketing/index.html`, a self-contained page with fictional example workflows. It needs no Python, Node, desktop service, CLI credentials, skill folders, or persistent storage.

## Coolify

1. Choose the Skill-Desk Git repository and the `main` branch.
2. Set **Build Pack** to **Static**.
3. Set **Base Directory** to `/marketing`. This field takes a directory, not `/index.html`.
4. Keep the default Nginx web server. If a document/index filename is requested, use `index.html`.
5. Set your public domain, save, and deploy the latest commit.

No install, build, or start command is needed. Do not run the Python desktop service or attach local skill folders to this deployment. If changing an existing application's build pack is unavailable, create a Static application with these settings and move the domain to it after stopping the old deployment.

See [Coolify's Static build pack instructions](https://coolify.io/docs/applications/build-packs/static).

## Verify the deployment

The browser title should be “Meet Skill-Desk · Interactive demo”, with the heading “Good workflows. Always within reach.” The demo says that nothing is installed and AI responses are illustrated examples. You should see synthetic examples, not a personal skill catalog.

Hard-refresh after deployment. If the previous page remains, confirm the deployed commit and purge any configured proxy/CDN cache. A redeployment replaces the current website; it does not erase old Git commits, release binaries, or cached copies.

## Other static hosts

Upload only the contents of `marketing/` to the public document root. For a single-file upload, use `marketing/index.html`. Never upload a development checkout, private skill exports, or local application state.

Edit `marketing/index.html`, then run `python scripts/sync_ui_assets.py`. It refreshes shared theme assets and the public root copy. The desktop service uses `web/app.html`; its empty catalog is populated locally at runtime.
