# 6. Demonstrate an enforced merge policy

| [Previous: secrets](5-secrets.md) | [Next: delivery and response](7-delivery-and-response.md) |
|:---|---:|

Budget: 10 minutes. The facilitator demonstrates the policy in a separate repository. Keep your working PR open; you will not configure a ruleset during this segment.

Keep your existing codespace available for unfinished edits. Inspect results on GitHub.com. In [take-home Lab 1](take-home/1-enforce-merge-policy.md), use the same codespace for file changes and configure the ruleset on GitHub.com.

## Why it matters

A failed check provides feedback. A ruleset can require that check to pass before merging. A successful CodeQL analysis confirms the scanner ran. The ruleset controls how its findings affect a merge.

## Explore together

1. Inspect the presenter's ruleset targeting `main`: active enforcement, no bypass actors, a required PR, zero required peer approvals, and required checks `api-tests`, `client-build`, and `dependency-review`.
2. Inspect **Require code scanning results**, select **CodeQL**, and require **High or higher** security findings to be resolved. The presenter uses the exact settings in [take-home Lab 1](take-home/1-enforce-merge-policy.md).
3. Open the presenter's separate failing dependency-training PR. Confirm the merge control is blocked by the required failed check. A missing check also blocks a merge, but does not demonstrate the intended failure-and-repair cycle.
4. Inspect the repaired revision and its passing check. Confirm eligibility, then close that PR without merging the fixture.
5. Merge only the presenter's safe application PR once its own results pass. This starts the prepared release simulation for lesson 7.

If a current result is delayed, the presenter can show a prior, labeled recording with its real PR/run links. A made-up screen or this guide's expected-result table is not recorded evidence.

Code-scanning merge protection has limits: pre-existing findings outside the PR diff and some Dependabot/default-setup cases do not block as you might expect. Keep an owned backlog for existing alerts. This template's `CODEOWNERS` has no inherited reviewers; solo learners do not enable required owner review or need a second reviewer.

## Checkpoint

Explain which rule blocks the demonstrated merge and why "CodeQL ran successfully" does not mean "there are no security findings." Return to any pending code/dependency results and record their actual state. Individual ruleset configuration belongs to take-home Lab 1.

## Resources

[Configure code-scanning merge protection](https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/set-merge-protection) and [its behavior and limitations](https://docs.github.com/en/code-security/concepts/code-scanning/merge-protection).

| [Previous: secrets](5-secrets.md) | [Next: delivery and response](7-delivery-and-response.md) |
|:---|---:|
