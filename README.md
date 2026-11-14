# jhcho-53.github.io

Personal academic homepage of **Jaehyeon Cho**, built with [al-folio](https://github.com/alshedivat/al-folio) v1.x (Jekyll).

## Where to edit

| What                                    | File                                                         |
| --------------------------------------- | ------------------------------------------------------------ |
| Bio, profile box                        | `_pages/about.md`                                            |
| Profile photo                           | `assets/img/prof_pic.jpg`                                    |
| News                                    | `_news/*.md` (one file per item)                             |
| Publications                            | `_bibliography/papers.bib` (`category` = international / journal / domestic, `selected = {true}` shows it on the main page, `preview` = image in `assets/img/publication_preview/`) |
| Venue badge colors                      | `_data/venues.yml`                                           |
| CV page                                 | `_data/cv.yml`                                               |
| Social links (email, GitHub, Scholar …) | `_data/socials.yml`                                          |
| Site-wide settings                      | `_config.yml`                                                |

## CV PDF

`main.tex` is the CV source. The phone number lives in `cv_private.tex` (git-ignored); `main.tex` includes it only if the file exists.

- **Full CV (with phone, for applications)**: `pdflatex main.tex` in this folder.
- **Public CV (website)**: compile `main.tex` in a folder *without* `cv_private.tex`, then copy the PDF to `assets/pdf/CV_Jaehyeon_Cho.pdf`:

```bash
mkdir -p /tmp/cv_public && cp main.tex /tmp/cv_public/ && (cd /tmp/cv_public && pdflatex main.tex && pdflatex main.tex)
cp /tmp/cv_public/main.pdf assets/pdf/CV_Jaehyeon_Cho.pdf
```

## Local preview

Requires Ruby 3.3 (`brew install ruby@3.3 imagemagick`). The path contains Korean characters, so a UTF-8 locale is required.

```bash
export LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
export BUNDLE_PATH="$HOME/.cache/homepage-bundle"   # keep gems out of OneDrive
bundle install
bundle exec jekyll serve -d /tmp/homepage-site      # http://localhost:4000
```

## Deploy

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site into the `gh-pages` branch.
In the GitHub repo settings: **Actions → General → Workflow permissions → Read and write**, and **Pages → Deploy from a branch → `gh-pages`**.
