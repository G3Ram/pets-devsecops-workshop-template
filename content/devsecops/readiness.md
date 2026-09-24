# Template readiness

## Why it matters

A bundled template removes file-installation steps, but it does not prove that a new learner's account, security settings, or codespace works. Record those results separately.

Template 0.1.0 is a prerelease in **frye/pets-devsecops-workshop-template**. Participants copy only this repository. The original app and previous companion are read-only provenance, recorded in [the source manifest](../../template-source.json).

## This template's checks

The app and complete workshop are bundled. Exactly two root workflows, `ci.yml` and `dependency-review.yml`, match the bundled starters. The release and job-token starters remain inactive. Neutral CODEOWNERS has no inherited reviewer, and the intentional debug-startup finding is preserved.

Local validation covers template inventory, repository-relative guide links, independent Git history, missing/mismatched installed workflows, safe recovery, the startup fix/test, release guards, and token error/cleanup behavior. Published results are recorded in [template validation evidence](fixtures/template-validation.json); pending values are not successes.

No second live learner repository is created by this implementation. Tests inside this template repository and disposable local copies cannot prove the complete GitHub **Use this template** experience. That remains a separate human/authorized validation step.

## Historical source-kit evidence

The bundled [secret provenance](fixtures/secret-validation.md), [recorded release receipt](fixtures/recorded-release/metadata.json), and [job-token evidence](fixtures/token-permissions-evidence.json) come from earlier explicitly identified author runs in `frye/pets-devsecops-rehearsal`. They support the source exercise design. They are not runs performed by this template or by a new participant.

The underlying application has known dependency alerts. Successful functional tests or dependency review of a harmless PR do not clear the existing backlog or make this sample suitable for production.

## Remaining manual checks

| Check | Evidence still needed |
|---|---|
| Fresh GitHub template copy | Own public repository created through the new template, all bundled files present, core checks operating on the initial/main and starter-PR revisions |
| Repository security | Dependency graph, CodeQL default setup, secret scanning, and push protection verified in that new copy; settings are not assumed inherited |
| Codespaces | Actual creation with known payer/usage, existing checkout, harmless push, secret block/repair, stop/resume and persistence |
| Independent learner completion | Written live/take-home instructions followed from fresh, partial, and resumed states without hidden setup |
| File-editor fallback | Actual blocked commit and clean retry, distinct from terminal history repair |
| Pacing and venue | Representative learners, planned staffing/network, and measured core duration without bypasses |
| Event-date review | Template version, dependency advisories, action pins, and inactive fixture behavior rechecked |

The earlier authoring environment lacked Codespaces OAuth scope and an authenticated browser page handle. No further authentication or billing change is made to force that check. [The inherited access record](fixtures/codespaces-rehearsal.json) is historical context, not a new access test.

## Checkpoint

Publish the template as a prerelease with observed results and pending manual checks labeled accurately. Do not borrow a recorded run, successful source lookup, or local Linux test as a participant's completed result.

## Resources

[Template behavior](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template), [Codespaces](https://docs.github.com/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository), and [CodeQL setup](https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configure-code-scanning).
