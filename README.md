# David Breslin — Portfolio Site

A static site: `index.html`, `style.css`, `script.js`. No build step, no database,
no server-side code — nothing for an attacker to compromise the way the old
Joomla site was.

## Editing content

Everything is in `index.html`, broken into clearly commented sections:

- `HERO` — name, title, metrics strip
- `SUMMARY` — executive summary paragraphs
- `EXPERIENCE` — one `<article class="role">` block per job; copy/paste a
  block to add a new role, edit the text inside to update an existing one
- `SELECTED ENGAGEMENTS` — case-study cards
- `EXPERTISE` — core competency groups
- `TECHNOLOGY STACK` — the layered tech summary
- `EDUCATION & CERTIFICATIONS`
- `CONTACT / FOOTER`

No JavaScript knowledge needed to update text — just edit the HTML directly.
`script.js` only handles the mobile menu and a subtle scroll-reveal effect.

## Adding the blog later

When you're ready for thought-leadership articles, the cleanest path that
keeps things free and simple is a static blog generator (e.g., **Eleventy**
or **Hugo**) that outputs plain HTML pages you can drop into a `/blog`
folder next to this site — no separate CMS or database required. I'm happy
to build that phase when you're ready; just flag it in a future chat.

## Deploying — recommended: GitHub Pages (free)

1. Create a free GitHub account if you don't have one, and a new repository
   (e.g., `davebreslin-site`).
2. Upload `index.html`, `style.css`, and `script.js` to the repository root.
3. In the repo, go to **Settings → Pages**, set the source branch to `main`
   and folder to `/root`, save.
4. GitHub will give you a URL like `https://yourusername.github.io/davebreslin-site`.
   Confirm it works.
5. In the same **Settings → Pages** screen, add `davebreslin.com` as your
   **custom domain**. GitHub will show you the exact DNS records to add.
6. Log into GoDaddy → **My Products → DNS** for davebreslin.com, and add:
   - Four **A records** at the root (`@`) pointing to GitHub Pages' IP
     addresses (GitHub shows these on the Pages settings screen)
   - A **CNAME record** for `www` pointing to `yourusername.github.io`
   - **Do not touch your existing MX records** — that's what keeps your
     GoDaddy email working exactly as it does today.
7. Check the "Enforce HTTPS" box once DNS propagates (can take a few hours).

## Alternative: Netlify (also free, slightly easier drag-and-drop deploys)

1. Create a free Netlify account, click **Add new site → Deploy manually**,
   and drag the three files into the upload box.
2. Netlify gives you a live URL immediately.
3. Go to **Domain settings → Add a custom domain**, enter `davebreslin.com`.
4. Netlify will show you a couple of DNS records to add at GoDaddy (usually
   one A record and one CNAME for `www`) — add only those, and again, leave
   your MX records untouched.

Either option costs nothing to run and takes about 15–20 minutes once your
GitHub or Netlify account is set up.
