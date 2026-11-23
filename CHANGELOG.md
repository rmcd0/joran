# Changelog

All notable changes to Joran. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [1.1.1] - 2026-11-23

### Fixed

- Headings now get an `id` (`##`, `###`, `####`), as `docs/writing.md` promised: the Eleventy plugin ignored the `.prose h2` selector. Existing ids are kept in view, so a heading never duplicates one, and an id that would start with a digit gets `h-` in front.
- `npm run check:links` now also checks links to a heading on the same page (`#a-section`), not only on other pages.

## [1.1.0] - 2026-11-23

### Added

- Terminal: your own commands, written as text replies in your dictionary (`term.commands.<name>` in `content/i18n/<lang>.json`, HTML allowed). They answer in the page language, show in `help` and complete with Tab. See `docs/features.md`.

### Fixed

- Scripts cache: the version in `main.js?v=` now covers every script it loads (`terminal.js`, `search.js`…), so a changed module is no longer served from the browser cache. With `npm start` the version is recomputed on each rebuild.

## [1.0.0] - 2026-11-22

First public release.

### Added

- Content and theme separated: `content/` for the user, `theme/` updatable with `npm run update-theme`.
- Settings in `content/site.config.js`, merged over defaults and validated at build time; changes show at once while `npm start` runs.
- Journal with type and language filters, grouping by year, shareable filtered addresses; tags; content types configurable (`post`, `project`, `politics` or your own), with an `empty` hint per type.
- Full-text search in the sidebar, ranked, with the matching passage; `searchFullText` and `searchMaxChars` options.
- Interface in English and French: one language, or two with a language switch (`/fr/` pages), switched on or off in one line; any other language through a dictionary in `content/i18n/`. Translations linked by `translationKey`, `hreflang`.
- Palettes `joran` (warm paper by day, midnight purple with pink gradients by night), `lake` and `mono`; light, dark and automatic modes with `light-dark()`; design tokens; unlayered `content/assets/custom.css`.
- Home page with featured cards (any number, or none), testimonials, contact; sidebar `Recent` list (any number, or none).
- Responsive images with Eleventy Image (WebP, `srcset`, dimensions, lazy loading, animated GIFs, SVG kept) and generated 1200 px share images.
- SEO and sharing: canonical, Open Graph, social cards, JSON-LD, Atom feed, sitemap, robots.txt, web manifest.
- IndieWeb: microformats (`h-entry`, author `h-card`), `rel="me"` links.
- Playful extras, each with its own switch: hidden terminal (`ls`, `cd`, `open`, `grep`…), secret rain theme, blinking cursor, 88×31 badge, webring.
- Footer parts with their own switches: build date, commit link, measured page weight with a CO₂ estimate, privacy note, badge, webring, RSS button, "Made with Joran".
- Honest privacy note chosen from the statistics settings: "0 cookies · 0 trackers", "0 cookies · anonymous visit stats" or "Privacy & cookies". Statistics: GoatCounter, Plausible, Umami, or any service through `analytics.custom`.
- Faster navigation: pages are fetched in advance when the pointer rests on a link (Speculation Rules), `features.prefetch`.
- Accessibility: skip link, landmarks, labelled controls, keyboard-friendly search and terminal, visible focus, reduced motion respected.
- Front matter checks for posts with plain-language messages; drafts visible in development only.
- Scripts: `new`, `check`, `check:links`, `check:html`, `test:empty`, `test:configs`, `update-theme`.
- GitHub Actions: Pages deployment with automatic address and path prefix; checks on Node 22, 24 and 26; Dependabot.
- Deployment examples for Apache, nginx, SSH/rsync, Netlify and Cloudflare Pages.
- Documentation in `docs/`.

[Unreleased]: https://github.com/rmcd0/joran/compare/v1.1.1...HEAD
[1.1.1]: https://github.com/rmcd0/joran/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/rmcd0/joran/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/rmcd0/joran/releases/tag/v1.0.0
