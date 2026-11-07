# CLAUDE.md

Guidance for AI assistants (Claude Code and similar) working in this repository.

## What this repository is

This is the **GitHub organization profile repository** for `MataiPacific`. Because the
repository shares its name with the organization (`MataiPacific/MataiPacific`), GitHub
renders its `README.md` on the organization's public profile page.

It is **not a software project**. There is no application code, no build system, no
package manager, no test suite, and no CI. Do not look for, or try to add, `package.json`,
`pyproject.toml`, `Makefile`, lint configs, or similar unless the user explicitly asks to
turn this into a code repository.

## Repository layout

```
.
├── CLAUDE.md          # This file
├── README.md          # Profile page content rendered on github.com/MataiPacific
└── brain_render.png   # Image embedded in README (1192 x 953 PNG, RGBA, ~560 KB)
```

- `README.md` contains a single section, "Brain connectivity gradients", an embedded image,
  and a caption. The image shows the Human Connectome Project (HCP) principal functional
  gradient rendered on a pial cortical surface using the
  [Cerebro-Viewer](https://pypi.org/project/Cerebro-Viewer/) Python package.
- `brain_render.png` is referenced by a relative path (`brain_render.png`) from the README.
  The rendering script that produced it is **not** in this repository.

There is no `.gitignore`, no `.github/` directory, and no other configuration.

## Git workflow

- Default branch: `main`.
- Remote: `https://github.com/MataiPacific/MataiPacific`.
- History is minimal (a single commit as of this writing). Keep it that way: small, clearly
  described commits.
- Work on a feature branch and push with `git push -u origin <branch>`. Do not push directly
  to `main` unless told to.
- Do not create a pull request unless explicitly asked.

## Conventions for edits

Because everything here is public-facing profile content, treat changes with care:

1. **Keep the README short and visual.** It is a profile banner, not documentation. Prefer
   one heading, one image, and a one-line caption over long prose.
2. **Preserve the image reference.** If you rename or replace `brain_render.png`, update the
   Markdown image link in `README.md` in the same commit so the profile never shows a broken
   image.
3. **Images must be committed, not linked externally.** GitHub profile READMEs render
   relative-path images from this repository; external hosts can break or be blocked. Keep
   image files reasonably sized (well under a few MB) so the profile loads quickly.
4. **Match the existing tone.** Scientific, understated, with attribution to the tools used
   (for example, the Cerebro-Viewer link in the caption). Keep attribution links when editing
   captions.
5. **Use standard GitHub-flavored Markdown.** Raw HTML is allowed in profile READMEs but
   limited (no scripts, no CSS); prefer Markdown unless layout genuinely requires HTML.
6. **Do not add generated noise.** No build artifacts, editor configs, lockfiles, or
   placeholder files. The repository should remain a README plus the assets it embeds.

## When asked to add code or tooling

If the user asks to add something substantive (for example, the rendering script, a data
pipeline, or a website), confirm whether it belongs here or in a separate repository. The
organization profile repository is normally kept to profile content only. If the user
confirms it belongs here, update this file to document the new structure, commands, and
conventions.

## Quick checks before committing

There are no automated checks. Before committing, verify manually:

- `README.md` renders correctly (valid Markdown, image path matches a committed file).
- Any new image is actually in the commit (`git status` shows it staged).
- No secrets, personal data, or large unrelated files were added.
