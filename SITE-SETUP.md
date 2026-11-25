# zacharyeyde.github.io — setup and content guide

Zachary Eyde's research website, built with the [as-folio](https://github.com/dadangnh/as-folio)
Astro theme and published with GitHub Pages from the **ZacharyEyde** organization.

---

## 1. Publish it (one time)

### a. Create an empty repo

In the **ZacharyEyde** organization: **Repositories → New repository**.

- Owner: **ZacharyEyde**
- Name: **zacharyeyde.github.io**
- Visibility: **Public**
- Leave **Add a README**, **.gitignore**, and **license** off, so the repo starts empty.

### b. Push this folder (on your computer)

```bash
unzip zacharyeyde-site.zip
cd zacharyeyde-site
git init -b main
git add .
git commit -m "Initial site"
git remote add origin https://github.com/ZacharyEyde/zacharyeyde.github.io.git
git push -u origin main
```

If git asks for a password, run `gh auth login` first (or use a personal access token).
GitHub doesn't accept your account password for pushes.

### c. Turn on GitHub Pages

In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions.**

### d. Run the deploy

Open the **Actions** tab (enable workflows if GitHub asks). The run started by your push
probably failed at the **Deploy** step because Pages wasn't on yet. Open it and click
**Re-run all jobs**, or go to **Deploy to GitHub Pages → Run workflow**.

It takes about 2 minutes. When it's green, the site is live at
**https://zacharyeyde.github.io**.

No repository variables are needed. The site URL is already set in
`.github/workflows/deploy.yml`.

---

## 2. Where your content goes

| Content | File | Notes |
|---|---|---|
| Conference papers, journal articles, preprints | `src/data/papers.bib` | BibTeX. `selected = {true}` puts a paper on the home page. `pdf = {file.pdf}` links a PDF in `public/assets/pdf/`. |
| Talks and poster sessions | `src/data/talks.yml` | Shown on the **talks** page. `type: poster` puts an entry under "poster sessions". Slides and poster PDFs go in `public/assets/pdf/`. |
| CV page | `src/data/cv.yml` | RenderCV format. Sections shown: education, experience, publications, awards, skills, interests. |
| CV PDF download | `public/assets/pdf/Zachary_Eyde_CV.pdf` | Linked from the CV page and the social icons. Replace the file to update it. |
| Bio on the home page | `src/data/about.mdx` | Markdown. |
| News on the home page | `src/content/announcements/*.md` | One file per item, with a `date:` at the top. |
| Research projects | `src/content/projects/*.md` | `related_publications` lists BibTeX keys to cite at the bottom. |
| Headshot | `public/assets/img/prof_pic.jpg` | Replace the file (keep the name) to change your photo. |
| Name, links, menu | `src/config/site.ts` | Title, subtitle, social links, navigation. |

Every push to `main` rebuilds and republishes the site.

---

## 3. Still to add (optional)

- [ ] Google Scholar and ORCID IDs: `scholar_userid` and `orcid_id` under `socials` in `src/config/site.ts`.
- [ ] WSC 2026 slides: add the PDF to `public/assets/pdf/` and a `slides:` line to the ERGminer entry in `src/data/talks.yml`.
- [ ] ERGminer code link: add `code = {https://github.com/...}` to its entry in `src/data/papers.bib` once the repo is public.
- [ ] ASU Semiconductor Week date: it is listed as October 2026. Change `date:` in `talks.yml` if you want the exact day.

The site shows your name as "Zachary Eyde". To change it, edit `title`, `author.name`,
and `blog.name` in `src/config/site.ts`, plus `name` in `src/data/cv.yml`.

The CV PDF is a trimmed public version of your CV: no phone number, and no internal
project names or dollar and quality figures.

---

## 4. Preview locally (optional)

Requires Node 24.

```bash
corepack enable
yarn install
yarn dev        # http://localhost:4321
```

---

## What was changed from the as-folio template

- Site URL set to `https://zacharyeyde.github.io` (deploy workflow fallbacks)
- Name, subtitle, bio, social links, and navigation set for Zachary Eyde; papers, talks, posters, CV, and headshot added
- New **talks** page (`src/pages/talks.astro`, data in `src/data/talks.yml`)
- All demo content removed (Einstein publications, blog posts, books, people, teaching, demo projects, news, portraits)
- Release-please and CI workflows removed, along with the commit-message hooks, so plain commits work.
  The deploy and weekly citation-update workflows stay.
