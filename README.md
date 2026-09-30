# Om Bhalerao — Portfolio

A single-page portfolio, split into separate HTML/CSS/JS files by concern. No build step, no dependencies — open `index.html` directly, or serve it with any static server.

## Structure

```
portfolio/
├── index.html              # structure only — links every file below
├── css/
│   ├── base.css             # design tokens, dark-mode tokens, resets, page grid
│   ├── navigation.css       # top nav bar + left sidebar (profile card, section nav)
│   ├── hero.css              # name/tagline, flip ID card, phone-chat back face
│   ├── sections.css         # Work/About tabs, Skills & Tools grid, Experience list
│   └── footer.css           # closing CTA + contact icons
├── js/
│   ├── interactions.js      # flip card, tab switching, save-profile toggle
│   └── navigation.js        # scroll-to-section nav, footer date
├── assets/                  # put your photo, resume PDF, etc. here
├── public/                  # empty — build/deploy output target (see below)
└── README.md
```

## Run it locally

Just open `index.html` in a browser — everything is relative paths, no server required.

For a local dev server (useful to test on your phone over local wifi):
```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## The `assets/` folder

This is where you add:
- A real photo (to replace the avatar photo in `assets/ranjeet.png`)
- Your resume PDF (to wire up the "Resume" button in the top nav)

## The `public/` folder

Currently empty — this is the conventional static-output directory that Vercel/Netlify/GitHub Pages look for by default. Since this site has no build step, you have two options:
1. **Simplest:** deploy the project root directly (see Deploy section below) and ignore `public/`.
2. **If your host requires `public/`:** copy everything into it before deploying:
   ```bash
   cp -r index.html css js assets public/
   ```

## Deploy it

Your skills list already includes Vercel, Render, and Netlify — any of these work with zero config:

**Vercel**
```bash
npm i -g vercel
vercel
```

**Netlify** — drag-and-drop the whole folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or:
```bash
npm i -g netlify-cli
netlify deploy --prod
```

**GitHub Pages** — push this folder to a repo, then enable Pages on the `main` branch, root directory.

## Customizing

- **Colors/fonts** — CSS custom properties at the top of `css/base.css` (`--accent`, `--ink`, `--bg`, etc.). Everything else references these variables, so changing a token here updates the whole site.
- **Content** — each section lives in its own labeled block in `index.html`: `#hero`, `#work`/`#panel-about`, `#skills`, `#experiences`, `<footer>`.
- **Photo** — to swap in your photo: place it in `assets/` and update the `src` attribute in `index.html` and `js/interactions.js`.
- **Resume link** — the "Resume" button in `index.html`'s top nav currently opens an email request to your email. You can change this to your PDF path.
- **Interactivity** — `js/interactions.js` handles the flip card, tabs, and save button; `js/navigation.js` handles scroll-to-section links and the footer date. Both are plain vanilla JS, no framework.

## Featured Projects Showcased
1. **Freelance Portfolio Website** — Showcase of custom web development and client solutions ([webnova2618.github.io/Portfolio](https://webnova2618.github.io/Portfolio/))
2. **Personal Portfolio Website** — Personal web hub deployed on Vercel with CI/CD ([om-eight-amber.vercel.app](https://om-eight-amber.vercel.app/))
3. **College Canteen Platform (SaaS, Stealth Phase)** — End-to-end SaaS digitizing campus food ordering & kitchen operations
4. **PSVault** — Web app to track PlayStation and Xbox achievements in one place ([psvault.netlify.app](https://psvault.netlify.app/login.html))
5. **Mandala Pot** — Commissioned hotel website built for a client ([mandalapot.vercel.app](https://mandalapot.vercel.app/))
6. **SIH 26 Problem Statement Explorer** — Searchable browser for Smart India Hackathon 2026 problem statements ([sih26problemstatement.netlify.app](https://sih26problemstatement.netlify.app/))

## Contact links wired up
- Email: `ombhalerao118@gmail.com`
- GitHub: `github.com/tyranthOM`
- LinkedIn: `linkedin.com/in/om-bhalerao-107466288`
- Freelance Portfolio: `webnova2618.github.io/Portfolio/`
