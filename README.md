# SEO bundle for Cairn

This bundle contains three files to drop into your GitHub repo
`stirlingcraig-cyber/Scottish-Pension-Aid-and-Retirement-Assistant`:

- **index.html** — your existing homepage, with SEO tags added (page title,
  meta description, canonical link, Open Graph/Twitter preview tags,
  structured data, and a `<noscript>` fallback so search engines and link
  previews that don't run JavaScript still see real text). No existing
  functionality was removed — only additions plus a slightly reworded
  `<title>`.
- **about.html** — a new, static "About" page. It adds a second indexable
  page and the kind of trust signal (who runs it, what it isn't, a scam
  warning) that matters for money-related sites.
- **sitemap.xml** — tells search engines both pages exist.

## 1. Upload the files

1. Go to your repo on GitHub:
   `https://github.com/stirlingcraig-cyber/Scottish-Pension-Aid-and-Retirement-Assistant`
2. Click **Add file → Upload files**.
3. Drag in `index.html`, `about.html` and `sitemap.xml` — when GitHub asks
   whether to replace `index.html`, say yes.
4. Scroll down, add a commit message such as "Add SEO tags, sitemap and
   about page", and click **Commit changes** (commit straight to `main`
   unless you use a different default branch).
5. Wait a minute or two, then visit your site and confirm it still works,
   and that `/about.html` loads too.

## 2. Verify with Google Search Console

1. Go to https://search.google.com/search-console and sign in with the
   Google account you want to manage this in.
2. Choose **URL prefix** (not Domain — Domain verification needs DNS
   access you don't have on github.io) and enter:
   `https://stirlingcraig-cyber.github.io/Scottish-Pension-Aid-and-Retirement-Assistant/`
3. Pick the **HTML tag** verification method. Google gives you a line like:
   `<meta name="google-site-verification" content="abc123...">`
4. Open `index.html` in your repo, find the commented-out line near the
   top of `<head>`:
   ```html
   <!-- <meta name="google-site-verification" content="PASTE-YOUR-CODE-HERE"> -->
   ```
   Replace it with Google's real tag (remove the `<!--` and `-->`), commit,
   and wait for the page to redeploy.
5. Back in Search Console, click **Verify**.
6. Once verified, open **Sitemaps** in the left menu, enter `sitemap.xml`,
   and submit it.
7. Open **URL Inspection**, paste your homepage URL, and click
   **Request Indexing**. Do the same for the `about.html` URL.

## 3. Register with Bing

1. Go to https://www.bing.com/webmasters and sign in.
2. Use **Import from Google Search Console** to bring your verified site
   and sitemap across in one step. Bing results also power DuckDuckGo,
   Ecosia and Yahoo.

## 4. What's deliberately not included

- **robots.txt** — this only has any effect at the root of a domain
  (`stirlingcraig-cyber.github.io/robots.txt`), which belongs to a
  different repo, not this one. Nothing on your site is blocked by
  default, so you don't need one.
- Extra content pages for individual topics (State Pension age, lost
  pensions, Pension Wise, etc.) — these would help a lot, but need real
  written content rather than boilerplate. Worth doing as a follow-up once
  you're ready to write them; ask and I can draft them.

## 5. Checking progress

- Search `site:stirlingcraig-cyber.github.io` in Google to see what's
  indexed so far.
- In Search Console, check **Pages** for indexing issues and
  **Performance** for which searches are showing your site.
- Indexing and ranking typically take anywhere from a few days to a few
  months — this is normal.
