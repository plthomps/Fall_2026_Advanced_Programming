# CIS 3400 — Setting Up Your GitHub Repo: README + Colab Links

**Goal:** By the end of this guide your repo will have a `README.md` that describes your work and gives anyone a one-click "Open in Colab" button for each notebook.

---

## Part 1 — Add a README.md to your repo

### If your repo does NOT have a README yet

1. Go to your repository on **github.com**.
2. If you see a green banner that says **"Add a README"**, click it and skip to step 6.
3. Otherwise, click the **Add file** button (top right of the file list) → **Create new file**.
4. In the filename box, type: `README.md`
   - GitHub is not picky about the capitalization here — `readme.md` and `Readme.md`
     work exactly the same. All caps is just the long-standing convention, so we'll
     use `README.md`.
   - The `.md` extension is the part that matters. It tells GitHub to render the
     file as formatted text instead of showing it as plain characters.
5. Paste the template from Part 3 below into the editing box.
6. Edit the template so it describes *your* project (name, course, notebooks).
7. Scroll to the bottom, type a short commit message such as `Add README`.
8. Click **Commit changes**.

Your README now appears automatically on the repo's front page.

### If your repo ALREADY has a README

1. Open `README.md` in the file list.
2. Click the **pencil icon** (Edit this file) in the upper right.
3. Add the sections you're missing — especially the **Notebooks** table from the template.
4. Commit changes at the bottom.

> **Tip:** While editing, click the **Preview** tab to see how your Markdown will render before you commit.

---

## Part 2 — Learn Markdown

Markdown is the simple formatting language used in `README.md` files, Colab text cells, and Jupyter notebooks.

- **GitHub's official syntax guide:** https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
- **Interactive hands-on tutorial (recommended, ~15 min):** https://github.com/skills/communicate-using-markdown
- **One-page cheat sheet:** https://www.markdownguide.org/cheat-sheet/

The five things you'll use 90% of the time:

| What you type | What you get |
|---|---|
| `# Heading` | Large heading (use `##` and `###` for smaller) |
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `- item` | A bulleted list |
| `[text](https://url)` | A clickable link |

---

## Part 3 — README template (copy this)

Copy everything inside the box below into your `README.md`, then replace anything in `ALL CAPS` or angle brackets.

```markdown
# YOUR PROJECT OR REPO NAME

**Course:** CIS 3400 — Advanced Programming
**Author:** YOUR NAME
**Semester:** Fall 2026

## About This Repository

One or two sentences describing what this repository contains and what you are
learning or building. Example: "This repository holds my weekly notebooks and
assignments for CIS 3400, including data exploration, visualization, and
machine learning projects in Python."

## Notebooks

| Notebook | Description | Open in Colab |
|---|---|---|
| `week01_penguins_colab_quickstart.ipynb` | Colab quick start using the Palmer Penguins dataset: pandas, plotting, and a simple classifier. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/USERNAME/REPO/blob/main/week01_penguins_colab_quickstart.ipynb) |

## Data

- **Palmer Penguins** — measurements of three penguin species from Antarctica,
  loaded directly from a URL inside the notebook. No download required.
  Source: https://github.com/mwaskom/seaborn-data

## Tools and Libraries

- Python 3
- Google Colab
- pandas, matplotlib, seaborn, scikit-learn

## How to Run

Click the **Open in Colab** badge next to any notebook above. The notebook opens
in your browser — no installation needed. To save your own edits, choose
**File → Save a copy in Drive**.

## Notes

Anything you want the reader to know: what you found interesting, what you
struggled with, what you'd do next.
```

---

## Part 4 — Upload a notebook and make its Colab link

### Step 1: Upload the `.ipynb` file

1. On your repo's main page, click **Add file** → **Upload files**.
2. Drag your `.ipynb` file into the box (or click **choose your files**).
3. Add a commit message and click **Commit changes**.

> **Rename before you upload.** Avoid spaces, parentheses, and long auto-generated
> names — they break links or force ugly `%20` codes in URLs. Good names look like
> `week01_penguins_colab_quickstart.ipynb`. Use lowercase letters, numbers,
> underscores, and hyphens only.

### Step 2: Build the Colab link

Take your GitHub URL and swap the front of it. The pattern:

```
GitHub:  https://github.com/USERNAME/REPO/blob/main/NOTEBOOK.ipynb
Colab:   https://colab.research.google.com/github/USERNAME/REPO/blob/main/NOTEBOOK.ipynb
```

You are replacing `https://github.com/` with `https://colab.research.google.com/github/`. Everything after that stays exactly the same.

**Worked example.** If your username is `jsmith` and your repo is `cis3400`:

```
https://colab.research.google.com/github/jsmith/cis3400/blob/main/week01_penguins_colab_quickstart.ipynb
```

> If your default branch is `master` instead of `main`, use `master` in the URL. Check the branch name in the dropdown on your repo's file list.

### Step 3: Turn it into a badge

A plain link works, but a badge looks better and is what you'll see in professional repos. The Markdown is a link wrapped around an image:

```markdown
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](PASTE_YOUR_COLAB_URL_HERE)
```

### Step 4: Test it

1. Commit your README.
2. Open the repo's front page and click your badge.
3. It should open the notebook in Colab. If you get a 404:
   - Check the branch name (`main` vs `master`).
   - Check spelling and capitalization of the repo name and filename — both are case-sensitive.
   - Make sure the repository is **public** (Settings → General → scroll to Danger Zone → Change visibility). Colab cannot open notebooks in a private repo.

---

## Shortcut: let Colab do the work

If a notebook is already open in Colab, you can push it to GitHub and get the badge automatically:

1. In Colab: **File → Save a copy in GitHub**.
2. Choose your repository and branch, and set the file path/name.
3. **Check the box "Include a link to Colaboratory"** — Colab inserts the Open in Colab badge into the top of the notebook for you.
4. Click **OK**.

You still need to add the notebook to the table in your README so it's easy to find.

---

## Checklist before you submit

- [ ] Repo is **public**
- [ ] `README.md` exists and renders on the repo front page
- [ ] README includes your name and the course
- [ ] Every notebook is listed in the Notebooks table with a short description
- [ ] Every Colab badge has been clicked once and actually opens the notebook
- [ ] Notebook filenames have no spaces or parentheses
