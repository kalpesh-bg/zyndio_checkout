# Contributing

## Branches

`master` is the deploy branch. Work happens on a short-lived branch named
`type/short-description`, using `feat/`, `fix/`, `chore/` or `docs/`.

## Pull requests

1. Branch from current `master`.
2. Keep one concern per pull request. Visual changes and behaviour changes are
   separate pull requests.
3. Confirm the build succeeds locally:

   ```bash
   npm ci
   npm run build
   ```

4. Open the pull request against `master` with the template filled in.
5. Include before/after screenshots for anything visual, desktop and mobile.
6. A maintainer reviews and merges. Merged work is deployed by the maintainers.

## Review expectations

- No direct pushes to `master`.
- Order payloads, gateway and billing ids, pricing copy and SMS consent wording
  need a maintainer review and the relevant compliance sign-off. Do not change
  them in a visual or refactor pull request.
- Checkout behaviour and the WLMD API contract are owned by the maintainers.
