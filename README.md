# ashkuhlmann.github.io

My **living offensive-security portfolio** — the roadmap I'm following, the certifications and
skills I'm building, the projects and writeups that prove them, and a running learning log. Built
with Jekyll + the [just-the-docs](https://just-the-docs.com/) theme, deployed via GitHub Pages.

---

## How the site is organized

| Nav | File | What it's for |
| --- | ---- | ------------- |
| Home | `index.md` | Dashboard: current focus, featured work, latest journal entries. |
| Roadmap | `roadmap.md` + `docs/` | The plan (full curriculum + Phase 1–2 schedule). |
| Progress Tracker | `progress.md` | Living checklist of where I am against the roadmap. |
| Certifications | `certs.md` | Cert milestones and status. |
| Projects | `projects/` | Hands-on builds, labs, tools. |
| Writeups | `writeups/` | CTF solves, vuln writeups, CVEs — employer-facing proof. |
| Journal | `journal/` | Weekly learning log. |
| About / Contact | `about.md`, `contact.md` | Who I am, how to reach me. |

## How I keep it updated (the routine)

**This is designed to be low-effort. The scaffolding does the remembering.**

- **Every week:** copy `journal/_TEMPLATE.md` → `journal/YYYY-MM-DD.md`, fill it in. It auto-appears
  on the Journal page and the home page.
- **When focus shifts:** edit the `🎯 Currently` block on `index.md` (three lines) and flip status
  emoji on `progress.md`.
- **New project:** copy `projects/_TEMPLATE.md` → `projects/<name>.md`. Auto-lists under Projects.
- **New writeup / CTF / CVE:** copy `writeups/_TEMPLATE.md` → `writeups/<name>.md`. Auto-lists,
  newest first.
- **Pass a cert:** update the row in `certs.md` (status emoji + date + a note/link).

**Conventions that make the auto-listing work:**

- Files starting with `_` (like `_TEMPLATE.md`) are **ignored by Jekyll** — they live in the repo
  for copy-paste but never publish.
- Index pages auto-list their children by matching front-matter `parent:` (e.g. `parent: Journal`)
  — so every new entry needs the right `parent:` and, for dated sections, a `date:`.
- `<!-- FILL IN ... -->` comments throughout are guidance for me; they don't render on the site.

## Run the site locally

Requires a recent Ruby (via Homebrew on macOS). If `ruby -v` shows the system Ruby, add Homebrew's
to your PATH first (`~/.zshrc` for zsh, `~/.bash_profile` for bash):

```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
# restart the terminal, then:
ruby -v            # should be 3.x
gem install bundler jekyll
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Deploy

Pushing to `main` triggers the GitHub Pages build automatically — no separate deploy step.
