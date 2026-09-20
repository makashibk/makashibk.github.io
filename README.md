<div align="center">

# SEO Tools

**The home page for a small collection of free SEO tools: a robots.txt validator, an SEO log file analyzer, and a Chrome SEO extension.**

[**Visit the site**](https://makashibk.github.io/)

![GitHub Pages](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-1a73e8?logo=github&logoColor=white)
![Static site](https://img.shields.io/badge/build-none%20(plain%20HTML)-brightgreen)
![License](https://img.shields.io/badge/license-MIT-green)
![Privacy](https://img.shields.io/badge/analytics-none-brightgreen)

</div>

---

## About

This repository is the source for [makashibk.github.io](https://makashibk.github.io/), the landing page that links to all of MakashibK's SEO tools in one place. It is a single, static `index.html` file with inline CSS and a small amount of vanilla JavaScript. There is no framework, no build step, and no dependencies to install.

## The tools

| Tool | Type | What it does | Links |
|---|---|---|---|
| **Robots.txt Validator & Tester** | Web tool | Fetch a live robots.txt or paste your own, pick a crawler, test any URL, and see which rule allows or blocks it | [Open](https://makashibk.github.io/robots-txt-validator/) · [Source](https://github.com/makashibk/robots-txt-validator) |
| **SEO Log File Analyzer** | Web tool | Analyze server log files to see which bots crawl your site, which URLs they request, and where they hit errors | [Open](https://makashibk.github.io/seo-log-file-analyzer/) · [Source](https://github.com/makashibk/seo-log-file-analyzer) |
| **SEO Extension for Chrome** | Chrome extension | Audit any page in one click: meta tags, indexability, schema, social tags, HTTP headers, images, and links, with Excel export | [Source and install steps](https://github.com/makashibk/chrome-seo-extension) |

## Features of the site

- **Live search.** Type in the search box to filter the tools. Press **Enter** to open the first match, or press **/** anywhere on the page to jump to the search box.
- **Light and dark mode.** Follows your operating system setting automatically.
- **Responsive.** On phones the sidebar becomes a slide-out drawer, and the cards stack into one column.
- **Accessible.** Skip link, visible keyboard focus, labelled controls, and reduced-motion support.
- **Built to be found.** Descriptive `<title>` and meta description, canonical URL, Open Graph and Twitter tags, and JSON-LD structured data (a `WebSite` plus an `ItemList` of `SoftwareApplication` entries for each tool).
- **Fast.** One HTML file, inline styles, and no JavaScript libraries. The only external requests are Google Fonts.

## Project structure

```
.
├── index.html      # the entire site: markup, styles, and script
├── README.md
└── LICENSE
```

## Run it locally

No install is needed. Either open `index.html` in your browser, or serve the folder so paths behave like the live site:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

The site is published with GitHub Pages from the `main` branch.

1. The repository must be named exactly **`makashibk.github.io`** (`<username>.github.io`) so it is served at the root of the domain.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select **`main`** and **`/ (root)`**, and click **Save**.
4. Every push to `main` redeploys the site within a couple of minutes. Do a hard refresh (Ctrl+Shift+R) if you don't see changes.

## Customizing

Everything lives in `index.html`.

### Add a new tool

1. **Card.** Copy any `<article class="tool-card">…</article>` block inside the `#cards` section. Update the title, the description, the three check rows, and the two links in `card-foot`. Keep the `data-primary` attribute on the main action, since the search box uses it when you press Enter.
2. **Search keywords.** Edit the card's `data-search` attribute with words people might type, such as tool names, file types, and topics.
3. **Sidebar.** Add a matching link under the **Tools** heading in the `<nav>`.
4. **Structured data.** Add another `ListItem` to the `ItemList` in the JSON-LD block near the top of the file, and bump the `position` number.
5. **Icon color.** Use `tile-blue`, `tile-purple`, or `tile-orange` on the icon tile, or define a new tint in the `:root` variables.

### Change names and URLs

The GitHub username `makashibk` and each tool's repository name appear in several places. Search the file for `makashibk` and update every match, including the JSON-LD, the canonical link, and the Open Graph URL.

### Change colors and fonts

Colors are CSS variables at the top of the `<style>` block, with a separate set for dark mode inside `@media (prefers-color-scheme: dark)`. The heading font is Google Sans Flex, the body font is Roboto, and both fall back to system fonts if they fail to load.

## Privacy

- No analytics, cookies, trackers, or third-party scripts.
- The page loads its fonts from Google Fonts, so your browser makes a request to Google's font servers when you visit.
- Links go to GitHub and to the tool pages. Nothing you type in the search box leaves your browser.

## Feedback and contributions

Found a broken link, a typo, or something that looks wrong on your device? [Open an issue](https://github.com/makashibk/makashibk.github.io/issues). Pull requests are welcome. Please keep the site dependency-free and describe what you changed and why.

For problems with a specific tool, please open the issue in that tool's own repository, linked in the table above.

## License

Released under the [MIT License](LICENSE).
