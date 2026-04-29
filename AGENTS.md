# Repository Guidelines

## Project Structure & Module Organization
The site is a static build served via GitHub Pages. `index.html` contains the full layout and inlined animations. Global styles live in `css/main.css`, while brand assets reside in `img/`. The custom domain configured through GitHub Pages is tracked in `CNAME`; keep it intact so deployments stay mapped to based.at. Add new media under `img/` and reference them with relative paths from the page root.

## Build, Test, and Development Commands
No build pipeline is required. Preview changes locally with `python -m http.server 8000` (run from the project root, then open `http://localhost:8000`). If you prefer Node tooling, `npx serve .` achieves the same result. Always refresh after edits to confirm the inline CSS animations and fonts load as expected.

## Coding Style & Naming Conventions
HTML and CSS use two-space indentation and lowercase element/attribute names. Favor semantic tags (`section`, `header`, `footer`) and keep component classes descriptive, mirrored after the existing `hero`, `feature-grid`, and `trust` patterns. Place shared variables in the `:root` block within `main.css` and reuse them across new rules. Name assets with kebab-case (for example, `team-portrait.png`) and keep SVGs optimized before committing.

## Testing Guidelines
Automated tests are not configured. Run a manual sweep in the latest Chrome, Firefox, and Safari to confirm responsive layouts, sticky header behavior, and hover states. Validate HTML when making structural changes with `npx htmlhint index.html` if available locally, and ensure any new imagery is optimized to keep load under 200 KB per asset.

## Commit & Pull Request Guidelines
Follow short, imperative commit messages similar to the existing history (e.g., "Adjust hero spacing"). Squash small fixes before opening a PR. Include a concise summary of visual changes, link any related issues, and attach before/after screenshots or GIFs when updating layout or styles. Note any testing performed—browser versions, devices, or accessibility checks—in the PR description.

## Deployment Notes
Deployments occur automatically from the default branch via GitHub Pages. Verify that `CNAME` still points to `based.at` before pushing, and avoid force-pushing changes that could rewrite published history unless coordinated with the maintainer.
