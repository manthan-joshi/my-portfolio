# Manthan Joshi Portfolio

A multi-page static portfolio site. Evergreen by design, easy to extend over time.

---

## File structure

```
manthan-portfolio/
  index.html              Home (About + Direction + How I Work + Timeline)
  projects.html           Projects index
  resume.html             Résumé page with embedded PDF
  contact.html            Contact
  styles.css              Shared stylesheet
  manthan.jpg             Your headshot
  resume.pdf              Your current résumé
  undergrad-thesis.pdf    Your M4 thesis (linked from M4 page)
  projects/
    crispr-thesis.html    HPRT1
    curcunano.html        CurcuNano
    regulatory.html       Atlas
    m4-membrane.html      M4
    eb-gene-therapy.html  Butterfly
    copd-msc.html         Alveolus
    aav9-igf1.html        Satellite
    taxon-search.html     Taxonomer
```

---

## Project codenames

Each project has a short, memorable codename shown on cards and page heros:

| # | Code       | Full title                                 |
|---|------------|--------------------------------------------|
| 01| HPRT1      | CRISPR/Cas9 in CHO cells                   |
| 02| CurcuNano  | Curcumin LNP pitch for MRSA                |
| 03| Atlas      | CGT regulation under MHRA and Health Canada|
| 04| M4         | Recombinant membrane protein thesis        |
| 05| Butterfly  | Gene therapy for Epidermolysis Bullosa     |
| 06| Alveolus   | Gene-edited MSCs for COPD                  |
| 07| Satellite  | AAV9 and IGF-1 for muscle regeneration     |
| 08| Taxonomer  | Taxon search engine                        |

---

## How to host (pick one)

**GitHub Pages** (free, good for a permanent URL)
1. Create a repo on GitHub, name it `manthanjoshi.github.io` or similar
2. Upload all files in this folder
3. Settings > Pages > Deploy from branch `main`, folder `/`
4. Live in about 2 minutes

**Netlify** (free, easiest drag-and-drop)
1. Go to netlify.com, sign in
2. Drag the whole `manthan-portfolio` folder onto the deploy zone
3. Get a random URL, rename to `manthanjoshi.netlify.app` in settings

**Custom domain** (optional, around $12/year)
Buy at Namecheap or Porkbun. Both hosts support custom domain pointing.

---

## How to add a new project

You'll do this probably once or twice a semester. About 10 minutes per project.

### Step 1: Duplicate an existing project file

1. Open the `projects/` folder
2. Copy any existing file (e.g. `curcunano.html`) and rename to your new project slug (e.g. `aav-retina.html`)
3. Use lowercase, hyphens, no spaces, no special characters in the filename

### Step 2: Edit the new file

Open it in VS Code (free, code.visualstudio.com) and change these things. The rest of the file should stay untouched:

| What to change          | Where to find it                          |
|-------------------------|-------------------------------------------|
| Page title              | `<title>` at the very top                 |
| Kicker "§ Work / 09"    | Inside `<div class="kicker">`             |
| Codename                | Inside `<span class="stamp-name">`        |
| H1 headline             | Inside `<h1>` with `<span class="it">`    |
| Subtitle                | Inside `<p class="subtitle">`             |
| Meta row (4 items)      | Inside `<div class="meta-row">`           |
| Lead paragraph          | Inside `<p class="lead">`                 |
| Section headings + body | Under each `<h2>` tag                     |
| Tech tags               | Inside `<div class="tag-row">`            |

### Step 3: Add the project to the homepage

Open `index.html`, find the section with `<a href="projects/...` rows (the work archive). Copy any one row and paste it as a new row, then edit:
- The `href` to point to your new file
- The number (w-num)
- The codename and category (w-code)
- The title (w-title)
- The year (w-year)

### Step 4: Add it to the projects index page

Open `projects.html`, find the section with `<a href="projects/..." class="proj-card">` blocks. Copy any one and paste it as a new card. Edit:
- The `href`
- The code-name and code-meta
- The h3 title
- The paragraph description

### Step 5: Save, test, push

Open `index.html` in your browser to make sure everything looks right and the links work. Then push to GitHub (if using Pages) or drag the folder to Netlify.

---

## How to add a new experience (job, internship, co-op, etc.)

Edit `index.html`. Find the `<div class="timeline">` section near the bottom.

Copy any existing `<div class="timeline-item">` block and paste it as the first one (most recent on top). Edit:
- `<div class="when">` with your date range (e.g. "Jan 2027 to Jun 2027")
- `<h3>` with the role title
- `<div class="where">` with the company and location
- `<p>` with a one or two sentence description

You might also want to update the Roles column on the resume page (`resume.html`, find `<h4>Roles</h4>`) and the "Experience" section of your actual résumé PDF.

---

## How to update the résumé

1. Export your latest résumé as PDF
2. Rename the file to `resume.pdf`
3. Replace the existing `resume.pdf` in the folder
4. That's it. The embedded viewer on the résumé page will auto-update.

---

## Easy tweaks

**Change the accent color (orange)**
Open `styles.css`, find `--accent: #ff5b1f;` near the top. Replace with any hex code. Examples:
- Deep blue: `#2840d1`
- Forest green: `#1a5234`
- Soft burgundy: `#8b2e3f`

**Change the background (near-black)**
In `styles.css`, change `--bg: #0f0f0e;` to another hex code.

**Change your headshot**
Replace `manthan.jpg` with a new file using the same filename. Square or near-square photos work best.

**Change your About bio**
Open `index.html`, find the section marked `<!-- ================= ABOUT ================= -->`, edit the paragraphs inside `<div class="body">`.

**Change your Direction section**
Open `index.html`, find the section marked `<!-- ================= DIRECTION ================= -->`, edit the paragraphs.

**Change your Contact details**
Open `contact.html`, find the contact-list section, edit the items. Email is currently `manthan2001@gmail.com`.

---

## What's evergreen vs what you might update

**Evergreen (won't need updating):**
- Your identity statement on homepage and About
- Your educational history (past facts)
- All project pages (dated records of work you did)
- Your skills list
- Your contact info

**Will need occasional updates:**
- The Graduate degree date (update 2026 to show it's conferred once you graduate)
- Roles section on resume page (when TA/VP ends)
- Adding new projects and experiences as they happen
- The résumé PDF itself

---

## Reminders

- No em dashes anywhere in the copy
- No emojis
- The gmail address `manthan2001@gmail.com` is used as the primary contact. Phone number is currently on the Contact page, remove if you don't want it public.
- The GitHub username `manthan-joshi` is linked throughout. Update in all HTML files if you ever change it.
- All fonts loaded from Google Fonts (DM Serif Display, Archivo, JetBrains Mono)
- No JavaScript, no tracking, no analytics

---

## If you break something

You still have the zip. Re-download, start over.

## If you want bigger changes

Open a chat with Claude, paste the HTML you want to change, and describe what you want. Easier than editing by hand.
