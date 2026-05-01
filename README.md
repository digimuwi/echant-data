# echant-data

Annotation corpus for the [neumes-playground](https://github.com/digimuwi/neumes-playground)
project. Each contribution is a directory under `contributions/<uuid>/`
containing:

- `image.{jpg,png}` — manuscript page image
- `annotations.mei` — annotations in MEI 5.0 format (see the
  [MEI profile spec](https://github.com/digimuwi/neumes-playground/blob/main/spec/mei-profile.md))

## How this repo is updated

The `htr-service` backend writes contributions to a clone of this repo
(via `DATA_REPO_ROOT`) and pushes after each successful contribute,
update, or relabel. Commit messages name the contributing user.

Manual edits via `git push` are also fine — the backend will pick them
up on its next read, and concurrent writes are guarded by ETag-based
optimistic concurrency at the API layer.

## History

This repo's history was extracted from `neumes-playground` via
`git filter-repo` on 2026-05-01, preserving authorship of all
contribution edits.
