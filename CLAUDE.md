# CLAUDE.md

## Project Overview

BolesBook is a collection of 9 standalone, interactive educational web activities targeting reading/literacy, science, and life skills. Each activity is a self-contained HTML file with no build process, no backend, and no package manager. All dependencies are loaded via CDN.

The target audience is students with learning support needs (specifically a student named "AyBo").

## Architecture

**Zero-build static HTML site.** There is no `package.json`, no bundler, no compilation step. Every activity is a single `.html` file that runs directly in the browser.

### Technology Stack

- **Tailwind CSS** via CDN (`cdn.tailwindcss.com`) — used in all files
- **React 18 + Babel Standalone** via CDN — used in `lifetoScale.html` and `SavannaSquad.html` only
- **Vanilla JavaScript** — used in all other activity files
- **Chart.js** via CDN — used in `phonaware.html` for progress visualization
- **Canvas Confetti** via CDN — used in `spelling.html`, `SavannaSquad.html`
- **Font Awesome / Lucide / Phosphor Icons** via CDN — various files
- **Google Fonts** (Nunito, Inter, Fredoka, Lexend, Quicksand) — various files
- **Web Speech API** (browser native) — `readingcomp.html`, `spelling.html`

### File Map

```
bolesbook/
├── index.html            # Hub/landing page linking to all activities
├── BioLevels.html        # Taxonomy learning (vanilla JS)
├── IndyLiving.HTML       # Life skills assessment (vanilla JS) — note uppercase .HTML extension
├── Moodity.html          # Mood tracker (vanilla JS, largest file ~2500 lines)
├── SavannaSquad.html     # Self-regulation game (React 18)
├── phonaware.html        # Phonological awareness tracker (vanilla JS + Chart.js)
├── readingcomp.html      # Reading comprehension support (vanilla JS + Web Speech API)
├── decodingskills.html   # Phonics decoding assessment (vanilla JS)
├── spelling.html         # Spelling practice (vanilla JS + Web Speech API)
├── lifetoScale.html      # Hierarchy of life explorer (React 18)
├── README.md             # Project documentation
└── CLAUDE.md             # This file
```

## Key Conventions

### Code Style

- **All code is inline.** CSS lives in `<style>` tags, JS lives in `<script>` tags. There are no external `.css` or `.js` files.
- **React files use `<script type="text/babel">`** for JSX compilation via Babel Standalone.
- **Vanilla JS files use standard `<script>` tags** with `getElementById()` and inline event handlers.
- **Tailwind utility classes** are used extensively in HTML markup.
- **CSS variables** are used for theming in some files (dark mode in `spelling.html`, `Moodity.html`).
- No linter or formatter is configured. There are no `.eslintrc`, `.prettierrc`, or `.editorconfig` files.

### Design Patterns

- **Glassmorphism** — frosted glass effects with `backdrop-filter: blur()` and semi-transparent backgrounds
- **Responsive grid layouts** — mobile-first Tailwind grid classes
- **Dark mode** — supported in some activities via CSS variables and toggle buttons
- **Custom keyframe animations** — `float`, `shake`, `popIn`, `pulse` used across files
- **Confetti celebrations** — success feedback using `canvas-confetti` library

### File Naming

File naming is **inconsistent** — `IndyLiving.HTML` has an uppercase extension while all others use lowercase `.html`. Preserve existing names when editing; use lowercase `.html` for any new files.

## How to Run

Open `index.html` (or any individual `.html` file) directly in a modern browser. No server, build step, or installation required.

For local development with a server (helpful for avoiding CORS issues with some features):

```bash
python3 -m http.server 8000
# Then open http://localhost:8000
```

## Testing

There is no automated test suite. No test framework, no test files, no CI/CD pipeline. All testing is manual in-browser.

When making changes:
1. Open the modified `.html` file in a browser
2. Verify the activity loads without console errors
3. Test interactive features (buttons, inputs, navigation)
4. Check responsive behavior at mobile and desktop widths
5. If the file uses text-to-speech, test in Chrome (best support)

## Adding a New Activity

1. Create a new `.html` file in the root directory (lowercase extension)
2. Make it fully self-contained — all CSS in `<style>`, all JS in `<script>`
3. Load dependencies from CDN (Tailwind CSS at minimum)
4. Include a responsive, mobile-first layout
5. Add a link card to `index.html` in the activity grid
6. Update the README.md activities table

### Template structure for new activities:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Activity Name - BolesBook</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Additional CDN dependencies as needed -->
    <style>
        /* Embedded styles */
    </style>
</head>
<body>
    <!-- Activity content -->
    <script>
        // Embedded JavaScript
    </script>
</body>
</html>
```

## Common Pitfalls

- **Do not introduce a build system** (webpack, Vite, etc.) — this project is intentionally zero-build for simplicity
- **Do not create separate `.js` or `.css` files** — keep everything inline in the HTML
- **Do not install npm packages** — use CDN links for all dependencies
- **Do not rename `IndyLiving.HTML`** — the uppercase extension is part of the existing file and may be referenced elsewhere
- **React is only used in 2 files** (`lifetoScale.html`, `SavannaSquad.html`) — use vanilla JS for new activities unless React is specifically needed
- **CDN URLs should use versioned paths** where possible to avoid breaking changes

## Git Workflow

- Branch names follow the pattern `claude/<description>-<id>`
- Commit messages are descriptive and action-oriented (e.g., "Add Moodity mood tracker to index and README")
- PRs are merged into `main` via GitHub pull requests
