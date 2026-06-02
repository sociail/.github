# Claude Guidance

Read `AGENTS.md` first. It owns the repo-local operating rules, validation
commands, scratch/evidence policy, and commit/push expectations for this repo.

Fast context:

- this is the Sociail organization-level GitHub metadata/settings repo
- use `python3 -m json.tool .github/configs/settings.json >/dev/null` for JSON
  sanity when settings JSON is touched
- use `git diff --check -- <changed-paths>` for docs/template/workflow hygiene
- do not add tokens, private keys, or machine-local paths to settings or
  workflows
- keep deployment and environment authority in `~/dev/projects/iac`
