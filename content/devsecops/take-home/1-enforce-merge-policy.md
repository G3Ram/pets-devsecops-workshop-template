# 1. Merge-policy recovery and extended validation

| [Previous: resume](0-resume.md) | [Next: release recovery](2-approve-a-release.md) |
|:---|---:|

Use [core Lab 6](../6-merge-policy.md) as the only canonical merge-policy procedure. This page helps you recover an interrupted lab or extend the review; it does not repeat the ruleset instructions.

## Why it matters

Ruleset evidence is tied to the exact PR revision and check result. A missing branch or a green result from another SHA cannot prove the intended block or repair.

Use the same Codespaces editor/terminal or the labeled local Git/file-editor fallback as [core Lab 6](../6-merge-policy.md). GitHub settings and merge enforcement are always checked in your own repository.

## Resume safely

1. Read [Resume](0-resume.md) and inspect the safe application PR and dependency-training PR in your own repository. Confirm their branches, latest SHAs, file lists, and current checks before switching branches.
2. If the Lab 4 dependency PR is still open with PyJWT 2.3.0 and a completed high-severity failed `dependency-review`, leave it unchanged until the active `workshop-main` ruleset is ready. Then continue at Lab 6's blocked-merge step.
3. If the dependency PR or branch is closed/missing, recreate the isolated `exercise/dependency-policy` branch from current `main` and follow Lab 4 to observe the failure before running the Lab 6 policy proof.
4. If you repaired the fixture before proving the ruleset block, do not claim the block. Once the failed advisory result is preserved, restore only the isolated manifest to PyJWT 2.3.0 on that branch, observe the actual failed required check under the active ruleset, then repair it using Lab 6. Never install or merge the fixture.
5. If a required check or CodeQL result is pending, keep it pending. If the safe PR was already merged, verify its actual merge SHA, `main` checks, and alert status. If the merge predated the ruleset, it does not prove a ruleset-enforced safe merge; use a harmless safe PR through the active ruleset if appropriate, and label that recovery accurately.
6. If the dependency-training PR was accidentally merged, stop and remove the unused fixture through a separate safe PR. Do not claim the required unmerged closure or install the manifest.

## Extended validation

After recording the core outcome, inspect the actual CodeQL merge-protection result and the active `workshop-main` settings again. The expected state is `main` only, empty bypass list, a required PR with zero approvals, exact checks `api-tests`, `client-build`, `dependency-review`, up-to-date requirement, no merge queue, and CodeQL at High or higher.

Do not weaken organization rules or disable a requirement to obtain a green state. If CodeQL merge protection or a required check is unavailable under your account/policy, record the exact limitation and leave the outcome incomplete. Use [troubleshooting](troubleshooting.md) for pending checks and branch conflicts.

## Checkpoint

Keep the actual ruleset, failed-check block, repaired same-branch result, PR closure state, safe merge SHA, `main` checks, and alert status. Local tests, examples, and recordings do not establish GitHub enforcement.

## Resources

[Create branch rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/creating-rulesets-for-a-repository), [required status-check troubleshooting](https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/troubleshooting-required-status-checks), and [code-scanning merge protection](https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/set-merge-protection).

| [Previous: resume](0-resume.md) | [Next: release recovery](2-approve-a-release.md) |
|:---|---:|
