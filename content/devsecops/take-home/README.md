# Continue or recover in your own repository

| [Previous: closing](../8-wrap-up.md) | [Next: resume](0-resume.md) |
|:---|---:|

Labs 6 and 7 are required individual work in the 120-minute core workshop. These take-home pages are recovery and extended-validation companions; the canonical procedures are [Lab 6: merge policy](../6-merge-policy.md) and [Lab 7: delivery and response](../7-delivery-and-response.md). They do not define a second version of those procedures.

## Why it matters

Verify each rule by observing a safe failure, repairing it, and identifying the exact revision it allowed. If work is unfinished, resume from the actual repository state without discarding changes or mislabeling pending results.

Use the same public learner repository, eligible GitHub.com account, and existing codespace, subject to remaining usage or approved sponsorship. Reopen the existing space rather than creating one per lab. No Azure account, new payment method, second reviewer, laptop runtime, or PAT is required. Respect employer and organization policies.

## Choose a starting point

1. Read [Resume](0-resume.md) for fresh, partial, already-merged, and stopped-space recovery.
2. Follow [Lab 6](../6-merge-policy.md) for the canonical active ruleset, failed dependency-check block, same-branch repair, unmerged training PR, and safe merge.
3. Follow [Lab 7](../7-delivery-and-response.md) for the canonical environment policy, reviewed workflow PR, approval, receipt, and incident decision.
4. Use [Merge-policy recovery](1-enforce-merge-policy.md) and [Release recovery](2-approve-a-release.md) as concise state-specific references and optional extended validation.
5. Continue with [Lab 3: maintain dependencies](3-maintain-dependencies.md) or optional [Lab 4: workload identity](4-workload-identity.md) after the core workshop. The workload-identity lab tests GitHub API authorization only; OIDC/cloud setup is further reading.

[Troubleshooting](troubleshooting.md), [annotated solutions](../solutions/README.md), and the [evidence checklist](../evidence.md) are shared references. Examples and historical runs are not learner evidence. The [readiness register](../readiness.md) distinguishes local source validation from pending GitHub, Codespaces, and human checks.

If Codespaces is unavailable, use the documented [local Git](../0-setup.md#fallback-a-local-vs-code-and-git) or [file-editor fallback](../0-setup.md#fallback-b-github-file-editor) after preserving existing work. Record the route and the actual result separately. Before leaving any lab, save/push safe work and explicitly stop the codespace; stopped storage still counts.

## Checkpoint

Your evidence should show your own blocked merge, repaired eligibility, safe merge, and approved receipt where those steps were completed. A presenter's recording, saved example, or another repository does not count as your configuration or run.

## Resources

[Repository rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets) and [deployment environments](https://docs.github.com/en/actions/reference/workflows-and-actions/deployments-and-environments) describe the controls used in the core labs.

| [Previous: closing](../8-wrap-up.md) | [Next: resume](0-resume.md) |
|:---|---:|
