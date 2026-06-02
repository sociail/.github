`Sociail Team` [`Tasks ✅`](https://github.com/orgs/sociail/projects/2) [`Repos 🚀`](https://github.com/orgs/sociail/repositories) [`Localdev 🕹️`](https://github.com/sociail/localdev/blob/dev/README.md) [`Onboarding 🙌`](https://github.com/sociail/localdev/wiki) [`Docs 🔭`](https://github.com/sociail/docs)
<br>
<br>

# Sociail .github Repo
This repository serves as the central place for shared GitHub Actions workflows, issue templates, pull request templates, and more.
<br>
<br>


<hr>
© 2024 Sociail, Inc. All rights reserved.<br>
Unauthorized copying, modification, distribution, or use of this software is strictly prohibited.

## Sociail Operating Notes

- Repo authority: this repository owns organization-level GitHub profile,
  shared issue templates, repository settings configuration, and shared workflow
  examples.
- Platform authority: `~/dev/projects/iac` owns environment, cluster,
  deployment, and release-train policy.
- Normal branch: keep local work on `dev` tracking `origin/dev`.
- Fast validation: run `git diff --check -- <changed-paths>` and validate
  touched JSON with `python3 -m json.tool`.
- Full validation: review changed workflow permissions, repository target lists,
  and any settings sync behavior before applying organization-wide changes.
