# AGENTS.md — how to work in `helm-charts`

This repository is part of [Angelia](https://github.com/angelia-dev/angelia), built mostly by **AI coding agents** working with a human maintainer. It holds the Helm charts that deploy Angelia on Kubernetes.

The rules of the core repository apply here: read [angelia/AGENTS.md](https://github.com/angelia-dev/angelia/blob/main/AGENTS.md) (picking issues, when to stop and ask a human, Graft trailers, definition of done) and [docs/ESTIMATION.md](https://github.com/angelia-dev/angelia/blob/main/docs/ESTIMATION.md) (executor, complexity and model).

## Specific to this repository
- Charts are linted with `helm lint` and `ct lint`, and installed in a kind cluster in CI (`ct install`).
- Secure defaults: non-root, read-only root filesystem, no privilege escalation, resource requests set, NetworkPolicy available.
- Any change to defaults that affects security or data (persistence, secrets) is `Agent + human check` at least.
