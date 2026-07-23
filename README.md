# domotion-ci-images

**Disposable, machine-managed repo.** Domotion's CI visual-test runs force-push
their expected/actual/diff PNGs here (one orphan branch per suite × OS, e.g.
`unicode-macos`, `html-linux`) so the local review tool
(`npm run demos:review` in the domotion repo) can fetch individual images over
`raw.githubusercontent.com` instead of downloading multi-hundred-MB Actions
artifacts.

- Only the **latest** run per branch is kept (single-commit orphan branches,
  force-pushed by `.github/workflows/visual-tests.yml`'s aggregate job).
- Partial (`--only`) debug runs never push here.
- If the repo ever bloats from accumulated unreachable objects, delete and
  recreate it — nothing here is a source of truth.
