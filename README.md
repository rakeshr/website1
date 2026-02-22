# Website1 (Eleventy + GitHub Pages + Decap CMS)

This site is powered by Eleventy and deployed with GitHub Actions.

## Live URLs

- Website: `https://rakeshr.github.io/website1/`
- Admin (CMS UI): `https://rakeshr.github.io/website1/admin/`

## Client Editing Options

### Option 1 (Works now): Edit JSON on GitHub

Edit only:
- `src/_data/site.json`

Steps:
1. Open repository on GitHub.
2. Open `src/_data/site.json`.
3. Click the pencil icon.
4. Update text/image URLs/contact details.
5. Commit changes.

The website auto-updates in 1-2 minutes.

### Option 2 (CMS Screen): Use `/admin`

`/admin` is configured with Decap CMS, but GitHub Pages requires an OAuth bridge for login.

One-time setup needed:
1. Create a GitHub OAuth App.
2. Deploy an OAuth bridge endpoint.
3. Update `src/admin/config.yml`:
   - `base_url`
   - `auth_endpoint`

After that, client can log in and edit using form fields from `/admin`.

Detailed setup guide:
- `docs/CMS_OAUTH_SETUP.md`

## Developer Commands

Install:
- `npm.cmd install`

Run locally:
- `npm.cmd run dev`

Build:
- `npm.cmd run build`
