# Contributing to omamori lab

Every omamori lab repository commits and merges the same way. A repository's
own `CONTRIBUTING.md` adds its setup and its gates.

## Commits

- One focused change per pull request, on a branch off an up-to-date `main`:
  `feat/...` for a feature, `fix/...` for a bug, `docs/...` for documentation,
  `infra/...` for tooling and CI.
- A commit message's subject states the change's effect in the imperative
  mood. Its body gives the reason, and the net line change per file with the
  reason for each addition.
- In a repository with `scripts/check.sh`, the script passes before every
  commit.
- A change of behaviour starts with its tests. One commit adds them, marked
  `pytest.mark.xfail(strict=True)` so the suite still passes, and seen failing
  on their assertions under `pytest --runxfail`; the commit with the code
  removes the marks.

## Pull requests

- A pull request names its issue with `Closes #N` in its description.
- It merges by rebase only, so each of its commits lands on `main` in order,
  the failing tests before their code included, and the history stays linear.
  Its branch is deleted on merge. The repositories' settings allow no other
  merge.
- CodeRabbit reviews a pull request as an advisor. Each finding is reproduced
  before anyone acts on it.
