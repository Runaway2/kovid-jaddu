# Kovid Jaddu — Portfolio

Source for [kovid-jaddu-kovid3.vercel.app](https://kovid-jaddu-kovid3.vercel.app). Plain HTML/CSS/JS, no build tooling required to view it — open `index.html` directly or serve the folder.

## Adding a new project to the site

1. Open `projects.json` and add an entry:
   ```json
   {
     "id": "short-slug",
     "wide": false,
     "stack": ["Language", "Framework"],
     "title": "Project Name",
     "description": "One or two sentences on what it does.",
     "linkUrl": "https://github.com/Runaway2/repo-name",
     "linkLabel": "View repository"
   }
   ```
   - `wide: true` makes it the full-width flagship card (only one project should have this).
   - `invariant` is optional — use it for a callout like IronHouse's safety-invariant note.
   - Card color is assigned automatically by position; add `"colorClass": "c-3"` to pin a specific one (see `.c-1`–`.c-8` in `index.html`'s `<style>`).
2. Run `node build.js` — it rewrites the project cards in `index.html` between the `PROJECTS:START`/`PROJECTS:END` markers. Don't hand-edit that block; it gets overwritten.
3. Commit and push. Vercel is connected to this repo's `main` branch and deploys automatically on push — no manual deploy step needed.

## Everything else on the page

The hero, summary, skills, experience, education, and leadership sections are hand-written directly in `index.html` (outside the generated block) — edit them there.
