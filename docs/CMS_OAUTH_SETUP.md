# Decap CMS OAuth Setup (GitHub Pages)

Use this once to enable login at:
- `https://rakeshr.github.io/website1/admin/`

## 1. Deploy OAuth Proxy (Cloudflare Worker)

Recommended proxy template:
- https://github.com/sterlingwes/decap-proxy

Steps:
1. Clone that repo locally.
2. Configure and deploy with Wrangler.
3. Set worker secrets:
   - `GITHUB_OAUTH_ID`
   - `GITHUB_OAUTH_SECRET`

Reference docs:
- https://github.com/sterlingwes/decap-proxy
- https://decapcms.org/docs/backends-overview/

## 2. Create GitHub OAuth App

GitHub path:
- `Settings -> Developer settings -> OAuth Apps -> New OAuth App`

Use:
- Homepage URL: `https://rakeshr.github.io/website1/admin/`
- Authorization callback URL: `https://YOUR-PROXY.yourdomain.com/callback`

Save `Client ID` and `Client Secret`.

## 3. Update Decap Config in This Repo

Edit:
- `src/admin/config.yml`

Replace:
- `base_url: https://YOUR-PROXY.yourdomain.com`

Keep:
- `auth_endpoint: /auth`

## 4. Commit + Push

After updating `config.yml`, push to `main`.

## 5. Test Login

Open:
- `https://rakeshr.github.io/website1/admin/`

You should see GitHub login, then form-based CMS fields.

## Notes

- Until OAuth is configured, client can still edit `src/_data/site.json` directly on GitHub.
- This setup keeps hosting on GitHub Pages and only uses Worker for auth.
