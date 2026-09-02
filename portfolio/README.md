# Meqdad Muhana — Portfolio

A single-file personal site for a FinTech specialist and data scientist. No build step, no
frameworks, no external requests: one HTML file with embedded CSS and about 80 lines of vanilla
JavaScript, plus two files in `assets/`.

```
portfolio/
├── index.html      the whole site
├── README.md
├── .gitignore
└── assets/
    ├── profile.jpg  profile photo (750 × 1000)
    └── resume.pdf   CV, linked from the Download CV button
```

## Before you publish

Open `index.html` and replace three placeholders. Find-and-replace handles all of them:

| Find | Replace with |
| --- | --- |
| `your-username` | your GitHub username |
| `https://www.linkedin.com/in/your-profile/` | your LinkedIn URL |
| `https://github.com/your-username/bank-churn-prediction` etc. | the real repo URL for each of the four projects |

`your-username` appears in the GitHub buttons, the canonical URL, the structured data block, and
the four project links, so replacing it first clears most of the work. If a project has no public
repo yet, delete that project's `<p class="repo">…</p>` line rather than leaving a dead link.

## Publish on GitHub Pages

1. Create a repository named `your-username.github.io` (this gives you `https://your-username.github.io`;
   any other name works too and gives you `https://your-username.github.io/repo-name`).
2. Upload `index.html`, `README.md`, `.gitignore`, and the `assets/` folder — either through
   **Add file → Upload files** on github.com, or from the terminal:

   ```bash
   git init
   git add .
   git commit -m "Portfolio site"
   git branch -M main
   git remote add origin https://github.com/your-username/your-username.github.io.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**, set **Source** to `Deploy from a branch`, pick
   branch `main` and folder `/ (root)`, and save.
4. Wait a minute, then load your URL. Later pushes redeploy automatically.

To preview locally before pushing, open `index.html` in a browser, or run
`python3 -m http.server` in this folder and visit `http://localhost:8000`.

## Editing the content

Everything lives in `index.html`, in the order it appears on the page. The sections are marked with
HTML comments (`<!-- PROJECTS -->` and so on).

**Add a project** — copy an existing `<article class="project">` block and edit it. The left column
is the project type, `metrics` holds the headline numbers, `stack` lists the tools. A project with
no numbers to report can simply drop the `<ul class="metrics">` block, as Track Your Plant does.

**Add a skill** — add an `<li>` inside the relevant `<ul class="tags">`.

**Change the colours** — the palette is defined once at the top of the `<style>` block, in
`:root` for light mode and `[data-theme="dark"]` for dark. Change a hex value there and it updates
everywhere. Cyan (`--spark`) is deliberately used only for edges — rules, focus rings, active nav
underline — never for text, so it stays legible.

**Replace the photo** — overwrite `assets/profile.jpg`. A 3:4 portrait around 750 × 1000 is right.
If the file is ever missing, the page falls back to an initials block automatically.

**Update the CV** — overwrite `assets/resume.pdf` with the same filename.

## What's built in

- Responsive from 320px up; the nav scrolls sideways on phones
- Light and dark themes, following the system setting on first visit and remembering a manual choice
- Print stylesheet, so **Ctrl/Cmd + P** produces a clean text-only resume
- SEO meta tags, Open Graph tags, and Schema.org `Person` structured data
- Keyboard focus outlines, a skip link, semantic landmarks, and `prefers-reduced-motion` support
- Full content visible with JavaScript disabled

## Licence

Code is free to reuse. The photo, CV, and written content are Meqdad Muhana's.
