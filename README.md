# GTM Foundations — ICP Builder App

ThinkGrowth branded ICP template app for GTM Foundations, Week 1, Session 1.
Single HTML file. Zero dependencies. No build step required.

## Features

- 6 ICP components with guided fields and examples
- Auto-save to localStorage (answers persist on refresh)
- Progress tracking sidebar with per-section completion
- Export PDF via browser's native print-to-PDF (`window.print`)
- Copy all answers to clipboard
- Fully responsive — works on tablet and mobile
- Print stylesheet produces a clean, branded A4 PDF

## Deploy to Vercel (recommended)

### Option A — Vercel CLI (fastest)
```bash
npm i -g vercel
cd icp-app
vercel
```
Follow the prompts. Your app is live in ~30 seconds.

### Option B — Vercel Dashboard
1. Push this folder to a GitHub repository
2. Go to vercel.com → New Project
3. Import the repo
4. Framework Preset: **Other** (no build command needed)
5. Output Directory: leave blank (root)
6. Click Deploy

### Option C — Drag & Drop
1. Go to vercel.com → New Project → browse all templates
2. Drag the `icp-app` folder into the deploy area
3. Done — no config needed

## Deploy to Netlify

### Option A — Netlify CLI
```bash
npm i -g netlify-cli
cd icp-app
netlify deploy --prod --dir .
```

### Option B — Netlify Dashboard
1. Go to app.netlify.com → Add new site → Deploy manually
2. Drag and drop the `icp-app` folder
3. Live instantly

### Option C — Git integration
1. Push to GitHub
2. New site → Import from Git → select repo
3. Build command: leave blank
4. Publish directory: `.` (root)
5. Deploy

## PDF Export — How It Works

The app uses `window.print()` with a comprehensive `@media print` stylesheet.

What happens when a student clicks "Export PDF":
1. A ThinkGrowth-branded cover block appears (hidden on screen, shown on print)
2. The sidebar, topbar, and save bar are hidden
3. All input values render in a clean white A4 layout
4. ThinkGrowth brand colours, Poppins font, and section structure are preserved
5. The browser's print dialog opens — student selects "Save as PDF"

**Best results:** Chrome or Edge → "Save as PDF" destination.
**For guaranteed consistency:** Add Browserless/PDFBolt API call later (no other changes needed — the print HTML template already exists).

## Customising for Other Sessions

To adapt this for a different exercise:
- Replace section content in `index.html` (search for section-block IDs s1–s6)
- Update hero headline and description
- Update the course label in the sidebar-head and topbar breadcrumb
- Update the PDF cover company name default

## File Structure

```
icp-app/
├── index.html      ← entire app (HTML + CSS + JS, self-contained)
├── vercel.json     ← Vercel routing config
└── README.md       ← this file
```

No npm install. No build. One file.
