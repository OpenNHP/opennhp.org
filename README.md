# OpenNHP Official Website

The official website for [OpenNHP](https://github.com/OpenNHP/opennhp) - The Zero Trust Network-Infrastructure Hiding Protocol for the AI era.

🌐 **Live Site**: [opennhp.org](https://opennhp.org)

## Overview

This repository contains the source code for the OpenNHP project website, built with [Hugo](https://gohugo.io/) static site generator with multi-language support. The website showcases the vision, specifications, open-source ecosystem, research, and community around the Network-Infrastructure Hiding Protocol (NHP).

## Languages

| Language | URL | Status |
|----------|-----|--------|
| English | [opennhp.org](https://opennhp.org) | ✅ Complete |
| 简体中文 | [opennhp.org/zh-cn/](https://opennhp.org/zh-cn/) | ✅ Complete |
| 繁體中文 | [opennhp.org/zh-tw/](https://opennhp.org/zh-tw/) | ✅ Complete |
| 日本語 | [opennhp.org/ja/](https://opennhp.org/ja/) | ✅ Complete |
| Deutsch | [opennhp.org/de/](https://opennhp.org/de/) | ✅ Complete |
| Français | [opennhp.org/fr/](https://opennhp.org/fr/) | ✅ Complete |
| Español | [opennhp.org/es/](https://opennhp.org/es/) | ✅ Complete |

First-time visitors are auto-redirected to the best match for their browser language (`navigator.languages`). The logic lives in an inline script at the top of [`layouts/partials/head.html`](layouts/partials/head.html) and is silent on storage failures (private browsing). Once a visitor manually picks a language from the footer switcher, the choice is stored in `localStorage` (`opennhp_lang`) and honored site-wide on subsequent loads — auto-detection never overrides an explicit choice.

## Pages

| Page | Description |
|------|-------------|
| **Homepage** | Hero section with project overview, features, and ecosystem preview |
| **Vision** | The "Dark Forest" Internet concept and why NHP matters in the AI era |
| **Specification** | IETF Internet-Draft and CSA Zero Trust specification details |
| **Demo** | Live demo showing how NHP hides server ports from unauthorized users |
| **Open Source** | OpenNHP Core, StealthDNS, NHP-FRP, and JS Agent projects |
| **Research** | Academic papers and collaboration opportunities |
| **Community** | Discord, GitHub Discussions, and contribution guidelines |
| **Blog** | Articles on AI security and the Dark Forest Internet |

## Tech Stack

- **[Hugo](https://gohugo.io/)** - Static site generator with i18n support
- **HTML5** - Semantic markup
- **CSS3** - Custom properties, Grid, Flexbox, animations
- **JavaScript** - Vanilla JS for interactions
- **Fonts** - Inter, Outfit, JetBrains Mono (Google Fonts)
- **GitHub Actions** - Automated build and deployment

## Project Structure

```
website/
├── hugo.toml                  # Hugo configuration (languages, build settings)
├── content/
│   ├── en/                    # English content (default, served at site root)
│   │   ├── _index.html        # Homepage
│   │   ├── vision.html
│   │   ├── specification.html
│   │   ├── demo.html
│   │   ├── opensource.html
│   │   ├── research.html
│   │   ├── community.html
│   │   └── blog/
│   ├── zh-cn/                 # Simplified Chinese
│   ├── zh-tw/                 # Traditional Chinese
│   ├── ja/                    # Japanese
│   ├── de/                    # German
│   ├── fr/                    # French
│   └── es/                    # Spanish
├── data/
│   └── exploits.yaml          # Timeline stories for vision page
│                              #   (per-entry: date, icon, localized titles/
│                              #    descs/links for all 7 languages)
├── layouts/
│   ├── _default/
│   │   ├── baseof.html        # Base template (head, body, scripts)
│   │   └── single.html        # Single page layout
│   ├── blog/
│   │   ├── list.html          # Blog listing layout
│   │   └── single.html        # Blog post layout
│   ├── index.html             # Homepage layout
│   ├── partials/
│   │   ├── head.html          # <head> meta, fonts, favicon, lang-detect
│   │   ├── nav.html           # Navigation bar
│   │   ├── footer.html        # Footer with language switcher
│   │   ├── exploit-card.html  # One card in the vision-page timeline
│   │   └── background.html    # Particle/grid background effects
│   └── shortcodes/
│       └── exploits-timeline.html  # Renders timeline from data/exploits.yaml
├── i18n/
│   ├── en.yaml                # English UI strings (nav, footer, timeline)
│   ├── zh-cn.yaml             # Simplified Chinese UI strings
│   ├── zh-tw.yaml             # Traditional Chinese UI strings
│   ├── ja.yaml                # Japanese UI strings
│   ├── de.yaml                # German UI strings
│   ├── fr.yaml                # French UI strings
│   └── es.yaml                # Spanish UI strings
├── static/
│   ├── css/styles.css         # Main stylesheet
│   ├── js/main.js             # JavaScript interactions
│   ├── assets/images/         # Images
│   ├── assets/icons/          # Favicons
│   ├── CNAME                  # Custom domain
│   ├── robots.txt
│   └── llms.txt
├── .github/workflows/
│   └── hugo.yml               # GitHub Actions build & deploy
├── LICENSE
└── README.md
```

### Data-driven timeline

The "VISIBILITY = VULNERABILITY" section on `/vision/` renders from [`data/exploits.yaml`](data/exploits.yaml) via the [`exploits-timeline` shortcode](layouts/shortcodes/exploits-timeline.html). Adding a new story is a single YAML entry — titles/descs/date labels/link labels all live per-language in the same record. The shortcode sorts by date desc, shows the newest 4 cards, and hides the rest behind a localized toggle button (`show_older_findings` / `hide_older_findings` in each `i18n/*.yaml`). The per-card renderer is [`layouts/partials/exploit-card.html`](layouts/partials/exploit-card.html) and falls back to English for any missing translation.

## Design Theme

The website uses a "Dark Forest" theme inspired by the project's vision:

- **Color Palette**: Deep blues, purples with bright green accents
- **Typography**: Modern, technical aesthetic
- **Effects**: Particle animations, grid backgrounds, glow effects
- **Responsive**: Mobile-first design

## Local Development

### Prerequisites

- [Hugo](https://gohugo.io/installation/) (v0.159+)

### Run locally

```bash
# Start the development server with live reload
hugo server -D

# Build the site
hugo
```

Then visit `http://localhost:1313`

### Adding a new language

1. Add the language block in `hugo.toml` under `[languages]` — it will automatically show up in the footer switcher and in the first-visit auto-detect list once the code is added to the `SUPPORTED` array in [`layouts/partials/head.html`](layouts/partials/head.html).
2. Create `content/<lang-code>/` and translate the 10 content files from `content/en/`.
3. Add UI strings in `i18n/<lang-code>.yaml` (nav, footer, `show_older_findings` / `hide_older_findings`).
4. Add the new language's keys (`titles`, `descs`, `date_labels`, link `labels`) to every entry in [`data/exploits.yaml`](data/exploits.yaml). Missing entries fall back to English.

## Deployment

The site is automatically built and deployed via GitHub Actions on every push to `main`. The workflow:

1. Installs Hugo
2. Builds the site with `hugo --gc --minify`
3. Deploys to GitHub Pages

> **Note**: GitHub Pages source must be set to **"GitHub Actions"** in repo Settings > Pages.

## Links

- **Main Project**: [github.com/OpenNHP/opennhp](https://github.com/OpenNHP/opennhp)
- **Documentation**: [docs.opennhp.org](https://docs.opennhp.org)
- **IETF Draft**: [draft-opennhp-saag-nhp](https://datatracker.ietf.org/doc/html/draft-opennhp-saag-nhp)
- **Discord**: [OpenNHP Discord](https://discord.gg/CpyVmspx5x)

## Contributing

Contributions to the website are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally with `hugo server`
5. Submit a pull request

## License

This website is released under the [Apache 2.0 License](LICENSE).

---

Built with ❤️ — Ad Majorem Dei Gloriam
