# AI 440: Digital Twins and Physical AI · student site

The interactive lessons, hands-on guides, simulators and reference pages for **AI 440: Digital Twins and Physical AI** (City University of Seattle, School of Technology & Computing).

**Live site:** https://clarkngo.github.io/ai440/

Students reach these pages from Brightspace. Graded work is submitted in Brightspace, except the HOS: each HOS is graded straight from the student's GitHub Classroom repository. Every build runs in GitHub Codespaces, on CPU, using free tiers.

## What's where

| Path | Page |
|---|---|
| `index.html` | Course home |
| `start-here/accounts.html` | Account setup |
| `start-here/tools.html` | Tools you'll use all term |
| `start-here/ai-use.html` | AI Use Guide: the rule for each activity |
| `module-N/index.html` | Module N lesson (N = 1–4) |
| `module-N/hos-guide.html` | HOS N (Hands-On Skill) guide |
| `module-N/simulator.html` | Module N simulator |
| `module-N/application-challenge.html` | Application Challenge N |
| `module-5/index.html` | Term Project |
| `module-5/example-project.html` | Example Term Project (Packaging Cell Twin): interactive demo |
| `reference/` | Concept Companion, starter-code walkthrough, Concept Debate example |
| `assets/` | Shared `course.css`, `course.js` and `sim-tour.js` |
| `tools/check_site.py` | Pre-push checker |

Starter code will live in the template repositories `cityuseattle/AI440-HOS01`–`04` and `AI440-AC01`–`04` (planned: not yet published); students copy them through the GitHub Classroom invites linked from each lesson. Instructor material (teaching guide, answer keys, example answers) is not in this repository.

## Editing

Every page is a standalone HTML file. Edit it directly, then:

```bash
python3 tools/check_site.py            # links, anchors, accessibility basics, no instructor content
```

Push to `main` and GitHub Pages republishes in a few minutes.

**Brightspace links depend on these paths and `#section` ids.** Don't rename a page or a section `id` without updating the Brightspace links that point to it.

## Conventions

- **Layout:** every page uses the lesson layout: header, hero, sticky section nav, and `section.module.card` blocks. Shared styles are in `assets/course.css`.
- **Accessibility target: WCAG 2.2 AA.**
  - Links use `var(--link)`.
  - Week and module switchers are `role="group"` buttons with `aria-pressed`, not tabs.
  - Scrolling tables, diagrams and `<pre>` get `tabindex="0"`.
  - Inline SVG diagrams and charts need `role="img"` and an `aria-label`.
  - Live updates go through a `.sr-only` `aria-live` element.
  - Smooth scrolling is `html:focus-within` only, so `#section` links from Brightspace land correctly.
- **Simulators** are deterministic HTML models with a guided tour (`assets/sim-tour.js`); they make no network calls and don't run real models.
- **Videos:** "Watch first" videos must have human captions. Videos with only auto-generated captions are labelled "Optional video", and the notes cover the same material.
- **Codespaces, CPU, free tiers only:** every build runs in GitHub Codespaces on CPU. Gemini's free tier is the only key (HOS 4 and the Term Project). Anything that needs a paid key or a GPU is optional.

### Full accessibility audit (each term)

Run axe-core (WCAG 2.2 AA rules) on every page in light and dark mode with all week panels and `<details>` open. Check that nothing scrolls sideways at 320 px, and that the focus ring is visible when tabbing through a lesson and a simulator.

## License

Course materials: [CC BY 4.0](LICENSE.md), © 2026 Clark Ngo. Third-party videos, screenshots and the CityU name and logo are not covered. Starter code: MIT (in the template repositories).
