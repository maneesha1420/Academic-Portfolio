# Maneesha Lingala — Academic Portfolio

A portable React + Vite website with Three.js / React Three Fiber, Framer Motion, Lucide icons, and responsive CSS. No backend, API key, paid API, or subscription is required.

## Run locally

Install Node.js 22.12 or newer (includes npm), then open this project folder in a terminal:

```sh
npm install
npm run dev
```

Use the local URL printed by Vite. For an optimized production build:

```sh
npm run build
npm run preview
```

The deployable website is in `dist/`. Opening `index.html` directly using a file URL is not supported; use the development or preview command.

## Update your content

Edit the plain JavaScript records in `src/data/`:

- `publications.js`: titles, authors, years, journal, details, DOI and filter category.
- `patents.js`: titles, patent numbers and country where supplied.
- `education.js`, `experience.js`, `awards.js`, `memberships.js`: academic information.
- `profiles.js`: academic profile URLs and IDs.

To add a publication, append a record like the existing ones. Omit unknown properties rather than inserting a guess. Available filter categories are All, AI / ML, Healthcare AI, Cybersecurity, Emerging Technologies, and Other.

The photograph is `public/maneesha.webp`. The Download CV button serves `public/maneesha-lingala-cv.pdf`, an unchanged copy of the supplied CV. The PDF contains the original contact information, including the phone number; the website itself does not display the phone number. Replace the PDF with a redacted version if you do not want it accessible through the download.

## Content provenance and editorial notes

All academic records were transcribed from the supplied five-page CV generated 25 September 2026. The separately uploaded portrait was used and optimized to WebP.

- The 12 publication records include both versions of the composite-materials paper because the CV lists them separately with distinct DOIs. They are not described as 12 unique peer-reviewed papers.
- Missing publishers and authors are omitted. The generative mechanical-design entry preserves the title and author exactly as listed, including the trailing word “Authors”; the CV does not list Maneesha in that entry's author field. Please review this source entry before public release if it needs correction.
- The PhD record shows 2021 and “LAKKIREDDY BALIREDDY COLLEGE OF ENGINEERING. REVA UNIVERSITY” as printed in the CV. The site does not label the degree completed, awarded, or ongoing because the CV does not specify status.
- Patent numbers are copied verbatim; no legal status or unlisted jurisdiction is inferred. The UK skin-cancer classification record has no number in the CV.
- Six distinct named professional organizations are shown. The final CV committee-membership line repeats abbreviations and is truncated; it is not expanded into invented memberships or terms.
- The Google Scholar button uses the exact URL requested by the user. That URL is a Scholar library/search URL rather than the public author-profile URL. The CV's author ID is displayed separately and the supplied link is preserved.
- “Research Universe” descriptions are summaries of the listed publication and patent topics, not additional qualifications or projects.
- No citations, h-index, i10-index, publication metrics, or patent statuses have been invented.

## Hosting

This is a static site. Deploy the `dist/` folder on any static host. Relative asset paths support GitHub Pages project subdirectories.

### Cloudflare Pages or Vercel

Import the source repository, select Vite where prompted, set build command to `npm run build`, and output directory to `dist`. No environment variables or server are needed. Select the provider's free plan and check its current usage limits.

### GitHub Pages

Use the included `.github/workflows/deploy.yml`, push this project to your GitHub repository's `main` branch, then choose GitHub Actions as the repository's Pages source. The workflow builds and uploads `dist`.

No public hosting account is configured or deployment claimed by this package. A local preview and ready-to-upload production build are provided.

### Final domain metadata

Once a public domain is assigned, add its absolute canonical URL and `og:url` to `index.html`. These are deliberately omitted until a real deployment URL is known. Open Graph, X, description, title, favicon, and Person structured data are included.

## Performance and accessibility

- 900px WebP portrait, reused with native lazy loading in About.
- Dynamically imported Three.js scene and secondary section bundles.
- Reduced particle density and device pixel ratio on smaller screens.
- Reduced-motion preferences disable decorative CSS motion and scene rotation.
- Keyboard controls, visible focus, semantic headings, a skip link, labeled navigation and research controls, and external-link safety attributes.
- Theme preference is stored locally on the visitor's device.
- The 3D bundle is the largest optional asset; WebGL failure falls back to a decorative gradient while all content stays available.
- Google Fonts is a free optional external font request. System sans-serif fallbacks keep the website usable if fonts are blocked.

## Project structure

`src/components/` contains reusable navbar, hero, 3D scene, shared animation/links, About, profile cards, research map, publications, patents, career, and contact components. `src/styles.css` contains the theme, responsive breakpoints, and reduced-motion overrides.
