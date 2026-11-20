# AGENTS.md

Notes for coding agents working in this repository. [README.md](README.md) covers what it
does and how to use it.

## Versioning

SemVer with BitlBee's version as build metadata: `vX.Y.Z+up<BITLBEE_VERSION>`, e.g.
`v5.2.0+up3.6`, published as image `X.Y.Z`, `X.Y` and `latest`, per the
[versioning standard](https://github.com/mbologna/.github/blob/main/VERSIONING.md).

- Never create, move or delete tags, and never edit a version to cut a release:
  auto-release tags from the commit types (`feat` minor; `fix`, `perf`, `revert` patch;
  `!` or a `BREAKING CHANGE:` footer major) and adds the metadata from
  `ARG BITLBEE_VERSION` in the `Dockerfile`.
- Component versions belong in the image labels, not in the tag.
- Renovate doesn't track BitlBee, so `ARG BITLBEE_VERSION` is bumped by hand. Commit an
  upstream patch as `chore(deps):`, a minor as `feat(deps):` and a major (or anything that
  breaks users) as `feat(deps)!:`, so the release bumps by the upstream's impact.
