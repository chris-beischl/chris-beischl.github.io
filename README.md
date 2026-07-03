# Website — separate public repo for GitHub Pages

This folder is a **standalone static site**, meant to live in its **own public
GitHub repo** (not inside the private bot repo). Multiple pages:

```
/                 index.html          landing page (chris-beischl.github.io/)
/lectern/         lectern/index.html  the Lectern product page  (…/lectern/)
```

No build step, no dependencies beyond Google Fonts from CDN. The landing page
links to the Lectern page with a relative link (`./lectern/`), so it works whether
served from a user page or a project page.

## Deploy (user page — serves at the domain root)

1. Create a **public** repo named `chris-beischl.github.io`.
2. Copy the **contents of this folder** to the repo root (so `index.html` and
   `lectern/index.html` sit at the top level).
3. Repo → Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)`.
4. Live at `https://chris-beischl.github.io/` and `…/lectern/`.

(Alternatively a project repo like `website` serves at
`https://chris-beischl.github.io/website/` and `…/website/lectern/` — the relative
links still work.)

### Custom domain (optional)

Point a subdomain at Pages: add a `CNAME` file at the repo root containing just the
hostname (e.g. `beischl.space` or `lectern.beischl.space`), and a matching DNS
record → `chris-beischl.github.io` via Cloudflare.

## To fill in

- Landing copy is a starting point — tweak the intro/name freely.
- Lectern's **"Add to Discord"** buttons link to `#` — replace with the real
  OAuth2 invite URL once the app's client-id + scopes are set.
- `/lectern` `/privacy` block should link to a full policy page when it exists.
