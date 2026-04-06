# Veronorte Website

## Overview
Bilingual (EN/ES) static website for Veronorte, a Latin American venture capital fund-of-funds firm. Hosted on SiteGround at veronorte.com. GitHub repo: pedrocastano1996/veronorte_site (master branch).

## Site Structure
- Pages follow `page.html` (EN) / `page_es.html` (ES) naming pattern
- Shared `style.css` for all pages
- No build step — pure HTML/CSS, edit and deploy directly

### Pages
| EN | ES | Purpose |
|----|-----|---------|
| index.html | index_es.html | Homepage |
| portfolio.html | portfolio_es.html | Portfolio (funds + co-investments) |
| vision.html | vision_es.html | Vision & investment thesis |
| team.html | team_es.html | Team profiles |
| contact.html | contact_es.html | Contact form (FormSubmit.co → info@veronorte.com) |
| privacy.html | privacy_es.html | Privacy policy |
| terms.html | terms_es.html | Terms of service |
| ethics.html | ethics_es.html | Ethics/whistleblower line |

## Brand
- **Colors**: Ink #1D1F29, Verde Aurora #95D600, Amarillo Sol #FFCE00, Azul Noche #003B71, Verde Noche #003B4C
- **Font**: Open Sans (300, 400, 600 weights + italic 300) via Google Fonts
- **Logo**: images/logo.png

## Typography Rules
- **English pages**: No italics anywhere
- **Spanish pages**: Only use `<em>` for English loanwords (venture capital, software, hardware, startup, fintech, healthtech, vintage, deep tech, SaaS, etc.)
- Color accents in hero headings use `<span class="accent">` (not `<em>`)
- The word "optimismo"/"optimism" on vision page uses inline `style="color:#95D600;"`

## Key Components

### Logo Grid (Portfolio)
- `.logo-grid` with `.logo-tile` items — hover/tap reveals description overlay
- `onclick="this.classList.toggle('active')"` for mobile tap support
- Dark logos on transparent SVGs need `class="fund-logo-invert"` (applies `filter:brightness(0) invert(1)`)
- Text-only logos use `<span class="tile-text-logo">`

### Adding a New Fund
1. Add logo SVG/PNG to `images/funds/`
2. Add a `.logo-tile` block inside `.logo-grid` in both portfolio.html and portfolio_es.html
3. Include: tile-face (logo + link), tile-info (tile-type, tile-desc, tile-link)
4. If logo is dark/colored on transparent bg, add `class="fund-logo-invert"` to the img

### Adding a Co-Investment
Same as funds, but add to the `.coinvest-section` instead of `.funds-section`

### Contact Form
- Uses FormSubmit.co (free, no backend needed)
- Sends to info@veronorte.com
- `_next` redirect URL should match the live domain

## Deployment
- **SiteGround**: Upload files to `public_html` via File Manager
- **GitHub**: `git push origin master` to keep repo in sync
- Always update BOTH EN and ES versions of any page you change
- Sync to Documents: `cp file /mnt/c/Users/pedro/Documents/veronorte_site/` for local preview

## Local Preview
```bash
cd /home/pedrocastano/veronorte-web/veronorte_site
python3 -m http.server 8000
```
Then open http://localhost:8000

## Team
All team members use Claude Code for edits. Open terminal in the project folder and run `claude`.
