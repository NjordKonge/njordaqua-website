# njordaqua-website
The njord aqua webpage

## Custom Domain Setup (njordaqua.dk via GoDaddy)

The repository includes a `CNAME` file pointing to `njordaqua.dk`, which tells GitHub Pages to serve the site on that domain.

You also need to configure DNS records in your GoDaddy account:

### 1. Enable GitHub Pages
In the repository on GitHub, go to **Settings → Pages** and make sure the source branch is set (e.g. `main`) and the custom domain field shows `njordaqua.dk`.

### 2. Add DNS records in GoDaddy
Log in to GoDaddy, open **DNS Management** for `njordaqua.dk`, and add the following records:

**A records** (point the apex/root domain to GitHub Pages):

| Type | Name | Value            | TTL  |
|------|------|------------------|------|
| A    | @    | 185.199.108.153  | 600  |
| A    | @    | 185.199.109.153  | 600  |
| A    | @    | 185.199.110.153  | 600  |
| A    | @    | 185.199.111.153  | 600  |

**CNAME record** (point `www` to the GitHub Pages domain):

| Type  | Name | Value                          | TTL  |
|-------|------|--------------------------------|------|
| CNAME | www  | njordkonge.github.io           | 600  |

> Replace `njordkonge.github.io` with your actual GitHub Pages domain if the organisation/user name differs.

### 3. Wait for DNS propagation
DNS changes can take up to 48 hours to propagate worldwide, though they often take effect within a few minutes. Once propagated, GitHub Pages will automatically provision a free HTTPS certificate for `njordaqua.dk`.
