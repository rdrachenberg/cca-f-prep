# CCA-F Prep

A tiny static site for Claude Certified Architect — Foundations exam prep. No build step, no dependencies — just static HTML.

## Contents

| File | Route | What it is |
|------|-------|-----------|
| `index.html` | `/` | Landing hub linking to the two tools |
| `exam.html` | `/exam` | 60-question self-scoring mock exam |
| `guide.html` | `/guide` | 2-week study guide (print-to-PDF ready) |
| `vercel.json` | — | Clean URLs (`/exam`, `/guide`) + no-cache headers |

`cleanUrls` is what lets `/exam` and `/guide` resolve without the `.html`.

## Deploy to Vercel — pick one

### 1. Drag & drop (fastest, no tools)
1. Go to https://vercel.com/new
2. Drag this whole folder onto the page.
3. Click **Deploy**. Done — you get a `*.vercel.app` URL.

### 2. Vercel CLI
```bash
npm i -g vercel     # once
cd cca-f-prep
vercel              # preview deploy; follow the prompts
vercel --prod       # promote to production
```

### 3. Git import (for ongoing edits)
1. Push this folder to a GitHub repo.
2. In Vercel: **Add New → Project → Import** the repo.
3. Framework preset: **Other** (it's plain static). Leave build/output settings empty.
4. **Deploy.** Every push to the repo auto-deploys.

No framework preset, build command, or output directory is needed — Vercel serves these files as-is.

## Preview locally
Just open `index.html` in a browser. Note: the `/exam` and `/guide` clean-URL links resolve on Vercel; opening files directly, use `exam.html` / `guide.html`. To mimic clean URLs locally:
```bash
npx serve .
```

## Editing
Each page is a single self-contained HTML file (styles and script inline). Edit the file, redeploy. All exam state is in-memory — nothing is stored, so a refresh resets the test.
