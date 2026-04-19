# Cutting a Release
Putting this here to remind myself of the new release convention I would like to use...

Releases use **calendar versioning**: `YYYY.MM` (first release that
month) or `YYYY.MM.N` (subsequent releases that month).

## Steps

```bash
# 1. Make sure you're on main and up to date
git checkout main && git pull

# 2. Tag with CalVer
git tag 2026.04          # first release this month
# or: git tag 2026.04.1  # second release this month

# 3. Push the tag — CI builds the PDF and creates the GitHub release
git push origin 2026.04
```

## When to tag

Tag when there's a meaningful content change worth publishing:
new section, new chapter, batch of errata fixes, etc.
Don't tag for cleanup, formatting, or refactoring commits.

## Checking existing tags

```bash
git tag --list           # all tags
git log --oneline $(git describe --tags --abbrev=0)..HEAD  # commits since last release
```
