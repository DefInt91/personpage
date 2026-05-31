# Tool Hub Basic Requirements Spec

## 1. Project Overview

- Project name: `Tool Hub`
- Repository: `DefInt91/personpage`
- Deployment target: GitHub Pages
- Current version: `0.1.0`
- Spec date: `2026-05-31`
- Scope: Minimum viable static launcher page for personal static tools.

`Tool Hub` is a lightweight static web page used as a central launcher for separate static tools hosted on GitHub Pages. The first version focuses on a clean, memorable interface and simple link navigation only.

## 2. Goals

- Provide one entry page that links to multiple static tool pages.
- Keep the page fully static and deployable through GitHub Pages.
- Avoid personal names, profile content, login flows, APIs, or backend services.
- Make future tool additions simple by editing one JavaScript data array.
- Keep the first release small enough to maintain without a framework or build step.

## 3. Non-Goals

- No search, filtering, sorting, or category navigation in this version.
- No admin UI for editing tools.
- No authentication or user accounts.
- No GitHub API integration.
- No tool uptime or status checks.
- No analytics, tracking, or external scripts.

## 4. Functional Requirements

| ID | Requirement | Status |
| --- | --- | --- |
| FR-001 | Render a static landing page from `index.html`. | Done |
| FR-002 | Display the page title `Tool Hub`. | Done |
| FR-003 | Display the subtitle `Static tools collection`. | Done |
| FR-004 | Store tool data in a JavaScript `tools` array. | Done |
| FR-005 | Render one card per tool entry. | Done |
| FR-006 | Each card displays `title`, `description`, and `category`. | Done |
| FR-007 | Each card provides an `Open` link to the tool URL. | Done |
| FR-008 | External links open in a new tab with safe link attributes. | Done |
| FR-009 | Display a tool count based on the `tools` array length. | Done |
| FR-010 | Work directly as a static file without a build step. | Done |

## 5. Tool Data Model

Tool entries must use English property names.

```js
{
  title: "Stock Tracker",
  description: "Track stock data from a static dashboard.",
  category: "Finance",
  url: "https://defint91.github.io/Stocktracker/"
}
```

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `title` | String | Yes | Tool display name. |
| `description` | String | Yes | Short purpose statement. |
| `category` | String | Yes | Short category label shown on the card. |
| `url` | String | Yes | GitHub Pages or static tool URL. |

## 6. Interface Requirements

- Use a distinctive static index layout rather than a generic card grid.
- Include a left-side index rail on desktop showing the number of tools.
- Use responsive layout so mobile screens collapse into a single-column flow.
- Keep cards stable in size and avoid text overlap on small screens.
- Use visible focus states for keyboard navigation.
- Use hover treatment on tool cards and action buttons.
- Do not show any personal name, profile photo, biography, or social profile.

## 7. Visual Direction

- Style direction: bold static index / launcher board.
- Primary traits:
  - strong black outlines
  - high-contrast card shadows
  - restrained warm background
  - bright signal accent for the index rail and category tags
  - condensed display typography for headings
- Avoid:
  - purple gradient landing-page styling
  - oversized marketing hero sections
  - decorative profile content
  - one-note monochrome palettes

## 8. Accessibility Requirements

- Main content must use semantic HTML.
- Tool list section must have an accessible label.
- External action links must be keyboard focusable.
- Focus indicators must be visible.
- Motion must respect `prefers-reduced-motion`.
- Text must remain readable on mobile and desktop widths.

## 9. Deployment Requirements

- Main file: `index.html`
- Hosting: GitHub Pages
- Published URL: `https://defint91.github.io/personpage/`
- Repository URL: `https://github.com/DefInt91/personpage`
- Current published branches:
  - `main`
  - `gh-pages`

## 10. Verification Checklist

- `index.html` loads without a build step.
- Page contains `Tool Hub`.
- Page contains `Static tools collection`.
- Page renders three configured tools:
  - `Stock Tracker`
  - `Task Dashboard`
  - `Trade Records`
- Tool count displays `03`.
- `Open` links use `target="_blank"`.
- `Open` links use `rel="noopener noreferrer"`.
- No personal names are shown in the page content.
- No Chinese characters are used for code identifiers.
- Published page returns HTTP `200 OK`.

## 11. Known Constraints

- The local project directory was initialized as a Git repository inside `Personpage`.
- The parent workspace is not a Git repository.
- Git commands may require `safe.directory` because the sandbox user and Windows user differ.
- Browser screenshot verification may fail in the current sandbox if the in-app browser runtime cannot start.

## 12. Version History

- `0.1.1`: Replace placeholder tools with three configured GitHub Pages links.
- `0.1.0`: Initial static Tool Hub page with two placeholder tools and GitHub Pages deployment.
