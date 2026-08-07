# Manthan Joshi Portfolio

A multi-page static portfolio site. No JavaScript, no build step, no dependencies. Edit an HTML file, commit, it's live.

**Live at:** https://manthan-joshi.github.io/my-portfolio
**Repo:** https://github.com/manthan-joshi/my-portfolio, branch `main`

---

## File structure

```
my-portfolio/
  index.html              Home (About + Direction + How I Work + Timeline)
  projects.html           Work index, finished projects
  ongoing.html            In-progress projects
  resume.html             Résumé page with embedded PDF
  contact.html            Contact
  styles.css              Shared stylesheet
  manthan.jpg             Headshot
  resume.pdf              Current résumé
  undergrad-thesis.pdf    M4 thesis (linked from the M4 page)
  projects/
    pd-report.html        Deviation
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

Each project has a short codename shown on cards and page heros.

| #  | Code      | Full title                                          |
|----|-----------|-----------------------------------------------------|
| 01 | HPRT1     | CRISPR/Cas9 in CHO cells                            |
| 02 | CurcuNano | Curcumin LNP pitch for MRSA                         |
| 03 | Atlas     | CGT regulation under MHRA and Health Canada         |
| 04 | M4        | Recombinant membrane protein thesis                 |
| 05 | Butterfly | Gene therapy for Epidermolysis Bullosa              |
| 06 | Alveolus  | Gene-edited MSCs for COPD                           |
| 07 | Satellite | AAV9 and IGF-1 for muscle regeneration              |
| 08 | Taxonomer | Taxon search engine                                 |
| 09 | Deviation | HPRT1 process development report                    |

Numbers are IDs, not rank. Assign the next one up when you add a project.

**In progress**, on `ongoing.html`, no number until they ship:

| Code    | Full title                                       |
|---------|--------------------------------------------------|
| Release | Analytical methods for CGT release testing       |
| Scale   | Autologous against allogeneic CAR-T manufacturing |

---

## How to update the site

The site is already hosted on GitHub Pages. Anything committed to `main` goes live in one to two minutes.

### Editing one file

1. Open the repo, click the file
2. Click the pencil icon, top right
3. Edit, scroll down, **Commit changes**, leave "Commit directly to the main branch" selected

### Editing several files at once

Open the repo and press the **`.`** key. That loads VS Code in the browser, no install. Edit in the left tree, then use the Source Control panel to commit and sync. Ctrl+Shift+F searches every file at once, which is how you make the same change across all nine project pages.

### Adding a new file

**Add file** > **Create new file**. Type the full path in the filename box. Typing `projects/new-thing.html` creates the folder path automatically.

### Uploading files

**Add file** > **Upload files**, then drag. Same filename means it replaces the old one.

**Two things that break this.** If a copy is already in your Downloads folder, the browser saves the new one as `name (1).html` and the link dies. And GitHub Pages is case-sensitive, so click into the existing lowercase `projects` folder rather than creating a new one.

### Checking it worked

**Actions** tab, wait for the green tick on `pages-build-deployment`. Then hard refresh the live site with Cmd+Shift+R or Ctrl+Shift+R.

### Undoing

**Commits** > click the bad one > `...` > **Revert**. Nothing is ever lost.

---

## How to add a new project

About 10 minutes.

### Step 1: Duplicate a project file

Copy any file in `projects/` and rename to a new slug. Lowercase, hyphens, no spaces, no special characters.

Copy `curcunano.html` for a straightforward narrative page. Copy `pd-report.html` if you want the comparison table. Copy `m4-membrane.html` if you want the bar chart.

### Step 2: Edit the new file

| What to change          | Where to find it                       |
|-------------------------|----------------------------------------|
| Page title              | `<title>` at the very top              |
| Kicker "§ Work / 10"    | Inside `<div class="kicker">`          |
| Codename                | Inside `<span class="stamp-name">`     |
| H1 headline             | Inside `<h1>` with `<span class="it">` |
| Subtitle                | Inside `<p class="subtitle">`          |
| Meta row (4 items)      | Inside `<div class="meta-row">`        |
| Lead paragraph          | Inside `<p class="lead">`              |
| Section headings + body | Under each `<h2>` tag                  |
| Tech tags               | Inside `<div class="tag-row">`         |

Leave the nav, footer and stylesheet link alone.

### Step 3: Add it to projects.html

Find the `<a href="projects/..." class="proj-card">` blocks. Copy one, paste it in position, then edit the `href`, the `code-name`, the `code-meta`, the `<h3>`, and the paragraph.

### Step 4: Update this README

Add the file to the structure block and the codename to the table.

**Note:** there is no work archive on the homepage. The `.archive` and `.work-row` styles exist in `styles.css` but nothing uses them. Projects are reached through `projects.html` only.

---

## How ongoing projects work

`ongoing.html` holds work that's underway but not finished. Cards there are `<div class="proj-card">` rather than `<a class="proj-card">`, because there's nowhere to link yet. The `foot` shows a drafting window instead of an arrow.

**To add one:** copy an existing card block on that page, change the `code-name`, `code-meta`, `<h3>`, paragraph, and the date in the `foot`.

**To promote one to finished:**

1. Build a page for it in `projects/` following the steps above
2. Add a `proj-card` for it on `projects.html`
3. Delete its card from `ongoing.html`
4. Move its codename from the in-progress table above into the numbered one

If `ongoing.html` ever empties out, take the link out of the nav rather than leaving an empty page up.

---

## The nav

Five items, in this order, on every page. Root pages:

```html
  <div class="nav-links">
    <a href="index.html">Index</a>
    <a href="projects.html">Work</a>
    <a href="ongoing.html">Ongoing</a>
    <a href="resume.html">Résumé</a>
    <a href="contact.html">Contact</a>
  </div>
```

Files inside `projects/` need `../` in front of every href. Whichever page you're on carries `class="current"` on its own link.

Every file has a second Résumé link down in the footer. When editing the nav, make sure you're in the block near the top inside `<div class="nav-links">`.

---

## How to add a new experience

Edit `index.html`, find `<div class="timeline">` near the bottom. Copy a `<div class="timeline-item">` block and paste it as the first one, most recent on top. Edit the `when`, the `<h3>`, the `where`, and the paragraph.

Also update the Roles column on `resume.html`, find `<h4>Roles</h4>`.

---

## How to update the résumé

Export as PDF, rename to `resume.pdf`, upload it over the existing one. The embedded viewer picks it up automatically.

---

## Accuracy rules

An audit in August 2026 found several claims on this site that the underlying data did not support. They were removed. These rules exist so it doesn't happen again.

- **Nothing goes on the site before it exists.** Ongoing projects live on `ongoing.html` with an honest status, not on the Work page with a finished framing.
- **Never publish a number you haven't checked against the source.** If a figure is uncertain, write around it. The `pd-report.html` copy is deliberately written to avoid a unit conversion that hasn't been verified against the protocol.
- **Watch the vocabulary.** "Qualification plan" and "screening design" describe documents that exist. "Assay qualification" and "DOE" are skill claims with formal meanings, and they stay off the site until the underlying work is done.
- **A page correcting itself is fine. A page contradicting another page is not.** If you change a claim on one page, search the whole repo for it. Ctrl+Shift+F in the browser editor.

Claims already retired, do not reintroduce them anywhere:

| Retired | Reality |
|---------|---------|
| 6-TG selection window at 100 µM, ~7% viability | The curve was flat, 96.2% to 103.1%. 3.3 µM was a guess |
| Confirmed editing by Sanger with ICE indel analysis | Sanger traces unreadable, ICE failed at the control file. No rate exists |
| Verified plasmid constructs by restriction digest | NotI cut, EcoRV did not. Identity unconfirmed |
| Puromycin selection optimized via CellTiter-Glo | That curve was flat too |
| Two years at Reagene | One year, Aug 2023 to Aug 2024 |

---

## Easy tweaks

**Accent colour.** `styles.css`, `--accent: #ff5b1f;` near the top. Deep blue `#2840d1`, forest green `#1a5234`, soft burgundy `#8b2e3f`.

**Background.** `--bg: #0f0f0e;` in the same block.

**Headshot.** Replace `manthan.jpg`, same filename. Square or near-square works best.

**About bio.** `index.html`, find `<!-- ================= ABOUT ================= -->`.

**Direction section.** `index.html`, find `<!-- ================= DIRECTION ================= -->`.

**Contact details.** `contact.html`, the contact-list section.

---

## Reusable components

All defined in `styles.css`. Copy the markup from the page listed.

| Component        | Class            | Example page       |
|------------------|------------------|--------------------|
| Callout quote    | `.callout`       | any project page   |
| Tag pills        | `.tag-row .tag`  | any project page   |
| 5-step flow      | `.workflow`      | crispr-thesis, pd-report |
| Comparison table | `.compare-sheet` | regulatory, pd-report |
| Bar chart        | `.chart-card`    | m4-membrane        |
| Pipeline stages  | `.pipeline`      | curcunano          |
| Highlighted box  | `.live-block`    | crispr-thesis, pd-report |

The comparison table and the workflow both collapse to one column below 900px. Nothing else needs responsive thought.

---

## Writing rules

- No em dashes. Use a comma, a full stop, or restructure
- No emojis
- No cleft constructions ("what keeps pulling me in is")
- Contractions are fine. Short sentences are better
- Primary contact is `manthan2001@gmail.com`. Phone is on the Contact page, remove it if you'd rather it wasn't public
- GitHub username `manthan-joshi` is linked in every footer. Update everywhere if it ever changes
- Fonts load from Google Fonts: DM Serif Display, Archivo, JetBrains Mono

---

## Open items

- `resume.html` and `contact.html` still need the Ongoing nav link added
- The Direction section on the homepage still names business development, product strategy, translational science, regulatory affairs and medical affairs. The résumé is now a process development and analytical development résumé. Rewrite it to lead with PD, AD and CMC, with commercial as where that leads
- `crispr-thesis.html` links out to `manthan-joshi.github.io/CRISPR-Project/`. That write-up predates the audit and may still report an ICE indel rate. Check it or drop the link
- "LNP Delivery" in the homepage scroller is doing more work than a class pitch and one drug delivery course can support
- The Graduate degree date says 2026. Update once it's conferred
- Roles on `resume.html` will need updating when the TA and VP roles end

---

## If you break something

Revert the commit. Repo > **Commits** > `...` > **Revert**. The full history is always there, so nothing you do here is permanent.

## If you want bigger changes

Open a chat with Claude and upload the actual files rather than describing them. It cannot read the repo, and guessed markup produces pages that load with no styling.
