# Pets DevSecOps workshop template

**[Start the workshop](content/devsecops/0-setup.md)** | [Lessons and agenda](content/devsecops/README.md) | [Take-home labs](content/devsecops/take-home/README.md)

Use this repository to create your own public shelter application, with the complete workshop and its core checks already included.

1. Select **Use this template > Create a new repository** on [frye/pets-devsecops-workshop-template](https://github.com/frye/pets-devsecops-workshop-template). Choose your account, a public repository, and the default branch only.
2. In **your new copy**, select **Code > Codespaces > Create codespace on main**. Check Codespaces access, payer, and usage first.
3. Open `content/devsecops/0-setup.md` in the existing checkout. Verify Actions and your repository's security settings, then create the starter PR.

No companion fetch, second clone, or workflow-install step is needed. The app is in `app/`, the lessons are in `content/devsecops/`, and `.github/workflows` contains exactly the two core workflows. Builds and tests run in Actions; Codespaces provides the editor and Git terminal.

## Why it matters

The shelter's functional tests cannot answer every security question. This workshop adds code-scanning remediation, dependency review, and secret protection, then demonstrates merge policy and an approved release simulation.

The event design has a 75-minute core, eight minutes for startup, and seven for closing. Complete take-home labs and an optional job-token/OIDC learning path are bundled. Local Git and GitHub file editing are documented fallbacks; no cloud account or personal token is required.

> [!IMPORTANT]
> This is a training prerelease, not a production-ready application. The debug-startup finding is intentional exercise input; existing dependency alerts are not claimed resolved. Do not run or expose the app as a public service. Actual fresh template-copy, Codespaces, and human pacing checks remain distinct from automated tests; see [readiness](content/devsecops/readiness.md).

## Checkpoint

Your learner copy has the app, bundled guides, `ci.yml`, and `dependency-review.yml` before you create an exercise branch. Still verify dependency graph, CodeQL default setup, secret scanning, and push protection in that copy; repository settings are not assumed to transfer.

## Maintainers and sources

Changes to this template belong only in **frye/pets-devsecops-workshop-template**. Participants make lesson changes and PRs in their own copies. Do not send workshop PRs to the original Pets project or the earlier companion.

The [source manifest](template-source.json) records the pinned application and workshop sources. Their licenses and attribution are retained; these are read-only provenance, not participant setup destinations. [Maintainer instructions](content/devsecops/facilitator.md#maintain-and-publish-this-template) cover validation and packaging.

## Resources

[Creating from a template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template), [Codespaces creation](https://docs.github.com/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository), and [LICENSE](LICENSE).
