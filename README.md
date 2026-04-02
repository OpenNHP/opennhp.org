# OpenNHP Official Website

The official website for [OpenNHP](https://github.com/OpenNHP/opennhp) - The Zero Trust Network-Infrastructure Hiding Protocol for the AI era.

🌐 **Live Site**: [www.opennhp.org](https://www.opennhp.org)

## Overview

This repository contains the source code for the OpenNHP project website, built with [Hugo](https://gohugo.io/) static site generator with multi-language support. The website showcases the vision, specifications, open-source ecosystem, research, and community around the Network-Infrastructure Hiding Protocol (NHP).

## Languages

| Language | URL | Status |
|----------|-----|--------|
| English | [opennhp.org](https://www.opennhp.org) | ✅ Complete |
| 简体中文 | [opennhp.org/zh-cn/](https://www.opennhp.org/zh-cn/) | ✅ Complete |
| 繁體中文 | [opennhp.org/zh-tw/](https://www.opennhp.org/zh-tw/) | ✅ Complete |
| 日本語 | [opennhp.org/ja/](https://www.opennhp.org/ja/) | ✅ Complete |

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
│   ├── en/                    # English content
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
│   └── ja/                    # Japanese
├── layouts/
│   ├── _default/
│   │   ├── baseof.html        # Base template (head, body, scripts)
│   │   └── single.html        # Single page layout
│   ├── blog/
│   │   ├── list.html          # Blog listing layout
│   │   └── single.html        # Blog post layout
│   ├── index.html             # Homepage layout
│   └── partials/
│       ├── head.html           # <head> meta, fonts, favicon
│       ├── nav.html            # Navigation bar
│       ├── footer.html         # Footer with language switcher
│       └── background.html     # Particle/grid background effects
├── i18n/
│   ├── en.yaml                # English UI strings
│   ├── zh-cn.yaml             # Simplified Chinese UI strings
│   ├── zh-tw.yaml             # Traditional Chinese UI strings
│   └── ja.yaml                # Japanese UI strings
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

1. Add the language config in `hugo.toml` under `[languages]`
2. Create a content directory: `content/<lang-code>/`
3. Copy English content files and translate them
4. Add UI strings in `i18n/<lang-code>.yaml`

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
