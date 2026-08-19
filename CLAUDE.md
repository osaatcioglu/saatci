# Saatci Project Guidelines

## What this repo is

The publishing surface for the letter series: Kadikoy'den Mektuplar (Turkish) and Letters from Kadikoy (English). Each letter is one self-contained interactive HTML page. This repo serves the finished pages via GitHub Pages; research and drafting happen elsewhere.

## Structure rules

- `tr/mektup-N.html` and `en/letter-N.html`, numbered, one file per letter per language.
- `index.html` is the cover. When a new letter lands, add its row to the cover shelf and to the README table in the same commit.
- Every page is standalone: no external fonts, scripts, stylesheets, or images. Inline everything. A file must work opened directly from disk.
- A letter's Turkish and English editions are siblings, not translations line by line. Each edition reads natively; the mathematics and claims must match exactly between them.

## Page conventions

- Palette and type are shared across letters: warm paper (`--ink:#f7f2e4`), brass (`#8c6a22`), Didot/Baskerville serif stack, SF Mono for labels. Reuse the CSS variable names from letter 1.
- Turkish pages: proper Turkish characters always (either raw UTF-8 or HTML entities, but be consistent within a file; new text is raw UTF-8).
- No em dashes, en dashes, smart quotes, unicode ellipsis, or unicode bullets in any content.
- No pronouns for the divine: "the Almighty" in English prose, "Cenab-i Hak" in Turkish prose.

## Content integrity

- Every mathematical or astronomical claim in a letter must be verifiable by computation. Claims were sworn on honor after re-verification; never edit a number, precision statement, or claim without re-running the check.
- Never rewrite existing letter content without explicit permission from Omer. Published letters are frozen; fixes need his sign-off per change.

## Shipping checklist

1. Verify the page in headless Chrome (CDP screenshot + zero JS errors) before committing.
2. Commit with a plain descriptive message. Never amend; always new commits.
3. Push to main immediately, every time. GitHub Pages serves from the root; the live URL (https://osaatcioglu.github.io/saatci/) is the single reading surface. Never leave an edit unpushed, and never point Omer at a local file; after pushing, verify the live URL serves the change (curl with a cache-buster) and remind him to hard refresh if his tab is stale.

## Model policy

Always use the latest Claude model for interactive work. Never hardcode a specific model in scripts or automations; unattended `claude -p` automations pin `--model opus` (the alias, not a fixed ID).
