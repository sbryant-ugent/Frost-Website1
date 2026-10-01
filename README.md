# FROST project website

The website of **FROST**, an ERC-funded project at Ghent University on hunter-gatherers and the Younger Dryas in Western Europe.

It is built with [HugoBlox](https://hugoblox.com/) and hosted free on GitHub Pages. You don't need to know how to code to update it: every page is a plain text file, and the site rebuilds itself a minute or two after you save a change on GitHub.

---

## 1. Before going live: checklist

Search all files for **`TODO`** to find every placeholder. The main ones:

- [ ] **Grant number:** `layouts/_partials/hooks/footer-start/funding.html`
- [ ] **EU and ERC logos:** download them from <https://erc.europa.eu/support/logos> and save them as `static/logos/eu-emblem.png` and `static/logos/erc-logo.png` (they replace the grey boxes in the footer automatically)
- [ ] **Project email and address:** `content/contact/index.md` and the files in `data/authors/`
- [ ] **Bios and photos:** each person checks their own file in `data/authors/`. Photos go in `assets/media/authors/` with the same name as the file (e.g. `stefan-bryant.jpg`, square, about 400×400 px). Delete the matching `.png` placeholder.
- [ ] **Placeholder team members** ("To be announced"): replace with real people, or delete their files in `data/authors/`, `assets/media/authors/` and `content/authors/`
- [ ] **Full project title:** confirm with Possum (`content/about/index.md`)
- [ ] **Advisory board:** check the members are happy to be listed (`content/team/index.md`)
- [ ] **Example news posts:** check, edit or delete the three posts in `content/news/`
- [ ] **Placeholder images:** replace `featured.jpg` files with real photos when you have them
- [ ] **Privacy page:** ask Ghent University's data protection office to check `content/privacy/index.md`

> **The Sites page is not included yet.** This repository will be public, so anything uploaded can be read on GitHub even if it is hidden on the website. The Sites page (map and site list) is supplied separately in the `add-later` folder. Add it once Possum has approved the list (see section 4).

---

## 2. Put the site online (once, about 20 minutes)

You need a free GitHub account. Ideally create a shared one for the project (or a GitHub "organisation", e.g. `frost-ugent`) so the site doesn't depend on one person.

**Easiest route: GitHub Desktop**

1. Install [GitHub Desktop](https://desktop.github.com/) and sign in with the project's GitHub account.
2. Unzip the download. In GitHub Desktop choose **File → Add local repository**, pick the `frost-website` folder, and click **create a repository** when it offers to.
3. Click **Publish repository**. Untick **"Keep this code private"**: GitHub Pages is only free for public repositories. Publish.
4. On github.com, open the new repository and go to **Settings → Pages**. Under **Build and deployment → Source**, choose **GitHub Actions**.
5. Go to **Settings → Actions → General**. Under **Workflow permissions**, choose **Read and write permissions** and tick **Allow GitHub Actions to create and approve pull requests**. Save. (This lets the automatic publication import work.)
6. Open the **Actions** tab and run the workflow named **"Deploy website to GitHub Pages"** (click it, then **Run workflow**). When it shows a green tick, your site is live at the address shown under **Settings → Pages**, for example `https://frost-ugent.github.io/frost-website/`.

From then on, every change you save on GitHub rebuilds the site automatically.

**Alternative: upload in the browser.** Create a new public repository on github.com, click **uploading an existing file**, and drag in the *contents* of the `frost-website` folder. On a Mac, press **Cmd + Shift + .** in Finder first so the hidden `.github` folder is visible and gets uploaded too. Then continue from step 4.

**Your own web address** (e.g. `frost-project.eu`): buy the domain, then follow GitHub's guide to [custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site). Ghent University's IT department may also be able to give you a `ugent.be` address that points to the site.

---

## 3. Everyday edits

You can do all of these directly on github.com: open a file, click the **pencil icon**, edit, then click **Commit changes**. The site updates within a couple of minutes (watch the **Actions** tab).

### Write a news post
1. Go to `content/news/`. Open an existing post folder and copy the text of its `index.md`.
2. Click **Add file → Create new file** and type a name like `content/news/2026-11-fieldwork-geldrop/index.md`. The folder is created automatically.
3. Paste the text, change the title, summary, date and authors, and write your post underneath.
4. To add a header image, open the new folder and use **Add file → Upload files** to add a photo named `featured.jpg`.

### Add a team member
1. In `data/authors/`, open an existing file and copy it.
2. Create a new file such as `data/authors/jane-doe.yaml`, paste, and edit the details. Set `user_groups` to one of: `Principal Investigator`, `PhD Researchers`, `Postdoctoral Researchers`, `Technical Staff`.
3. Upload a square photo to `assets/media/authors/jane-doe.jpg`.
4. Create their profile page: a new file `content/authors/jane-doe/_index.md` containing just these three lines:
   ```
   ---
   title: Jane Doe
   ---
   ```

### Add publications from Zotero
1. In Zotero, select the papers, right-click → **Export Items… → BibTeX**.
2. On GitHub, open `publications.bib`, click the pencil, replace its contents with your export and commit. (Or upload the file with the same name.)
3. A minute later, a **pull request** appears under the **Pull requests** tab. Open it and click **Merge**. The publications are now on the site.

### Change the menu
Edit `config/_default/menus.yaml`.

### Change the home page
Edit `content/_index.md`. It is made of blocks (banner, numbers, text, cards, news, contact box) stacked in order.

### Write text: Markdown basics
`**bold**` · `*italic*` · `## Heading` · `- bullet point` · `[link text](https://example.com)`

---

## 4. Adding the Sites page (after approval)

1. Check the site list and map positions in `add-later/sites/index.md` with Possum. Positions are deliberately approximate.
2. Change `draft: true` to `draft: false` near the top of the file.
3. Upload it to the repository as `content/sites/index.md`. The **Sites** link appears in the menu automatically.

---

## 5. Where things live

| What | Where |
|---|---|
| Page text | `content/` (one folder per page) |
| Home page | `content/_index.md` |
| Team profiles | `data/authors/` (photos in `assets/media/authors/`, profile pages in `content/authors/`) |
| News posts | `content/news/` |
| Publications | `publications.bib` → `content/publications/` |
| Menu | `config/_default/menus.yaml` |
| Site name, colours, fonts | `config/_default/params.yaml` |
| Funding footer (EU/ERC) | `layouts/_partials/hooks/footer-start/funding.html` |
| Logos for the footer | `static/logos/` |
| Site icon (browser tab) | `assets/media/icon.png` |

---

## 6. Getting help

- **Hugo Chat** (<https://hugo.chat/>) knows this toolkit and can write new pages or fix errors. Paste in the file you want to change.
- **Claude** can also edit files or write new pages and posts.
- If the **Actions** tab shows a red cross, open the failed run: the error message usually names the file and line with a typo (often a missing quote or wrong indentation).
- HugoBlox documentation: <https://docs.hugoblox.com/>

---

## Technical notes

- Built with Hugo 0.162 and the HugoBlox kit (Tailwind CSS v4). Deployment is defined in `.github/workflows/`.
- Two HugoBlox files are overridden locally in `layouts/_partials/`:
  - `functions/build_links.html`: a one-line fix for a bug in the current kit (links on publication pages). Delete it once HugoBlox fixes the bug upstream.
  - `page_author_card.html` and `hbx/blocks/team-showcase/block.html`: links to people's profile pages now include the site's base path, so they work on a GitHub Pages project address.
- Fonts (Source Serif 4 and Inter, SIL Open Font License, see `font-licenses/`) are stored in `assets/dist/font/` so visitors' browsers don't contact Google.
- The site has no analytics or cookies. Update the Privacy page before adding any.
- The "Upgrade HugoBlox" workflow only runs when started by hand from the Actions tab.
- To preview locally: install Hugo extended and Node.js, run `pnpm install`, then `hugo server`.
