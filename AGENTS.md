# Repository Guidelines

## Authority

- This repo owns Sociail organization-level GitHub profile content, shared issue
  templates, repository-settings configuration, and shared workflow examples.
- `~/dev/projects/iac` owns platform, environment, deployment, cluster, and
  release-train authority.
- Component-repo operating policy is defined in
  `~/dev/projects/iac/docs/sociail/platform/cicd/component-repo-operating-contract.md`.
- Treat this as organization metadata and GitHub configuration, not an
  application or service repo.

## Working Rules

Rules:

1. Keep normal work on `dev` tracking `origin/dev`.
2. Before editing, check branch/upstream, stashes, worktrees, and the intended
   dirty slice.
3. Do not use stashes as handoff.
4. Do not hide useful edits in secondary worktrees.
5. Keep changes repo-local and slice-scoped; leave new unrelated drift for the
   next wave.
6. Do not copy IAC guarded-git or branch-protection relief into this repo.
7. Commit and push this repo independently from other component repos.

## Local Scratch And Evidence

- This repo normally should not need generated runtime output.
- If scratch is needed, use `_local/`, `_cache/`, or `_tmp/` and keep it
  untracked.
- Do not treat local generated output as source of truth.

## Sensitive And Local File Audit

Before changing ignore policy or moving local-looking files, run:

```sh
git ls-files | grep -Ei \
  '(^|/)(\.env|env|secret|token|key|cert|pem|crt|p12|kubeconfig|local|override)($|[./_-])'
git status --ignored --short
```

Organization settings and workflow files must not contain credentials, personal
access tokens, private keys, or machine-local paths.

## Validation Tiers

Use lightweight config validation. There is no application test suite in this
repo.

### `verify:fast`

Use for normal local commit confidence:

```sh
python3 -m json.tool .github/configs/settings.json >/dev/null
git diff --check -- <changed-paths>
```

For markdown-only slices, `git diff --check -- <changed-docs>` is usually the
relevant fast validation.

### `verify:full`

Use before repository-settings or workflow changes:

1. Validate changed JSON with `python3 -m json.tool`.
2. Validate changed YAML with an available YAML parser or GitHub workflow lint.
3. Review workflow permissions, tokens, and target repository lists.

### `proof:<domain>`

Use explicit proof lanes for configuration claims. Current examples:

1. `proof:settings` for repository settings sync behavior
2. `proof:workflow` for shared workflow behavior
3. `proof:profile` for organization profile/branding changes

Generated proof scratch belongs in `_cache/` unless intentionally promoted to
`_artifacts/`.

## Commit And Push

- Normal Git is acceptable after repo-native validation.
- Stage only the reviewed slice.
- Do not force-push unless explicitly approved for this repo.
- If additional unrelated changes arrive during validation, leave them for the
  next wave unless the user explicitly includes them.
