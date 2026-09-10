# Conscious Realty — Website Handover

Premium real estate advisory site for Bhaskar Rawat. Single-file build:
everything (HTML, CSS, JS) lives in `index.html`, plus four small SEO support files.

## Files in this package
| File | Purpose |
|------|---------|
| `index.html` | The entire website (HTML + CSS + JS in one file). |
| `favicon.svg` | Browser tab icon (the brand diamond mark). |
| `robots.txt` | Tells search engines they may crawl the site. |
| `sitemap.xml` | Lists the site URL for search engines. |
| `site.webmanifest` | Makes the site installable / sets mobile theme colour. |

Upload **all five files to the same folder** on your host. That's the whole site.

---

## 1. Editing projects (no developer needed)

Open `index.html`, search for:

    ⭐ THIS IS THE ONLY PLACE YOU EDIT PROJECTS

Everything else — cards, filters, and the "View Details" page — builds
automatically from that list. Each project is one `{ … }` block.

- **Add** a project: copy an existing `{ … }` block, paste it, edit the values.
- **Remove** a project: delete its `{ … }` block.
- **Update** a project: change the values.

Field reference is written directly above the list in the file. Key points:
- `priceCr` must be a NUMBER in crore (e.g. `2.85`) — it drives the Budget filter.
- `location` must be one of the filter values: `Gurugram`, `Delhi NCR`, `Bhiwadi`, `Uttarakhand`.
- `category` must be `Residential` or `Commercial` — it drives the Category filter.
- Leave any field as `''` (empty) and it is simply hidden — nothing breaks, nothing is invented.
- `rera` left empty shows "Available on request" on the detail page.

> The three projects currently in the file are **clearly-labelled placeholders**
> ("Project Name 1/2/3", "Developer Name"). Replace them with your real project
> details. No project information has been invented.

## 2. Settings you may want to change

Search `index.html` for `SITE SETTINGS`. There you can set:
- `WHATSAPP_NUMBER` — full international form, digits only (currently `917011981170`).
- `WEB3FORMS_KEY` — makes the contact form email you. Get a free key at
  https://web3forms.com (enter the business email; they email you an access key;
  paste it in). Until then the form falls back to WhatsApp automatically.

## 3. Placeholders still to fill

- **LinkedIn / YouTube links** — search for `YOUR-LINKEDIN-HANDLE` and
  `YOUR-YOUTUBE-HANDLE` (they appear in the contact section and footer) and
  replace with the real profile URLs.
- **Project data** — see section 1 above.
- **Domain** — the SEO tags, `sitemap.xml` and `robots.txt` use
  `https://www.consciousrealty.com/`. If your final domain differs, search
  `index.html`, `sitemap.xml` and `robots.txt` for `consciousrealty.com` and update.

---

## 4. Ownership & control (important — these are account actions, not code)

The brief (section L, points 43–47) asks that you, the client, own every critical
asset so the site can be handed to any developer later. These can't be done inside
the code — they're account setups. Recommended, all free or low-cost:

1. **Domain** — register/hold the domain in an account under YOUR email
   (e.g. GoDaddy, Namecheap, Cloudflare). Never let a developer hold it in theirs.

2. **Source code (GitHub)** — create a GitHub account under YOUR email, create a
   repository (e.g. `conscious-realty-site`), and upload these files. You are then
   the owner; you can grant a developer "collaborator" access and revoke it anytime.
   - Simplest path: github.com → New repository → "uploading an existing file" →
     drag these files in → Commit.

3. **Hosting** — deploy from that GitHub repo using an account under YOUR email:
   - **Cloudflare Pages** or **Vercel** or **Netlify** — all free for a static site
     like this, all connect straight to your GitHub repo and auto-publish on changes.
   - Because it's a plain static site, you can also just upload the five files to
     any basic web host via FTP. No build step is required.

4. **Analytics** — if you add Google Analytics later, create the property under
   YOUR Google account and paste the snippet before `</head>`.

5. **Handover rule of thumb** — domain, repository, hosting and analytics should
   each sit in an account you control. A future developer only ever needs
   *collaborator/deploy* access you can grant and revoke — never ownership.

---

## 5. Notes on the build
- Visual identity (fonts, palette, spacing, animations) is unchanged from your
  original site — this was a content/structure/SEO upgrade, not a redesign.
- "View Details" opens an in-page detail view. In a single-file site this is the
  clean equivalent of a separate detail page and keeps handover simple. If you
  later move to a multi-page or CMS setup, the project data structure is already
  organised to port over directly.
- Tested: no horizontal scroll from 320px up; keyboard-accessible; reduced-motion
  respected; contact form + WhatsApp fallback working.
