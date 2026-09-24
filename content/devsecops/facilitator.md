# Facilitator guide

| [Overview](README.md) | [Readiness register](readiness.md) |
|:---|---:|

## Why it matters

With up to 90 participant-owned laptops and one presenter plus 1-2 helpers, there is little room for live account repair. Require prework and keep to one narrated route.

## Before announcing the event

1. Direct learners only to [frye/pets-devsecops-workshop-template](https://github.com/frye/pets-devsecops-workshop-template). Their copies already contain the app, lessons, and two core workflows.
2. Complete every mandatory [readiness gate](readiness.md). Distinguish source inspection and local tests from live GitHub results. Treat the prerelease as review material; it does not establish event readiness.
3. Confirm the published template version before the event. Update source pins only through reviewed changes in this new repository, and do not silently change its default branch during a cohort.
4. Rehearse creating an actual template copy, checking security settings, starting Codespaces, running preinstalled CI, making a harmless commit/push, and stopping and resuming the space. Test local Git and file-editor fallbacks separately. Earlier native Linux tests do not establish that Codespaces authentication works.
5. Rehearse with representative prepared learners and managed/personal laptops on the venue network. Record wall-clock editing, Actions latency, help requests, and every outcome. The equation `8 + 75 + 7 = 90` only confirms the minutes add up; rehearsal must show that the schedule fits.

## Prework and staffing

Collect learner repository, starter-PR, and CI run URLs, plus the bundled template version, through existing communications. Ask if Codespaces opened, a harmless push succeeded, and the learner can stop/resume the space. Record fallback use. Do not collect tokens or private connection details or require another signup.

Narrate **Codespaces**, using the browser-based VS Code editor and integrated terminal. Keep the local Git and file-editor fallback references available for helpers rather than repeating every route. Assign the 1-2 helpers to tables or zones, prioritizing access/startup, Git problems, and the three individual exercises. At maximum capacity, a helper may cover 45-90 learners; revisit capacity if advance readiness is insufficient.

Confirm power, Wi-Fi, GitHub sign-in, the Codespaces editor/terminal and reconnection, and Actions access on representative personal/company-managed laptops. Check allowed quota or sponsorship before startup; do not change billing or machine size to force access. Use one smallest suitable codespace per learner repo, normally two cores, and no required custom devcontainer or app install. Neither a partner's run nor the presenter's repo completes another attendee's checkpoint.

## Prepare the two demonstrations

Use a separate, explicitly authorized facilitator repository. Never change participant settings for them.

1. Complete Step 0 and the code/dependency exercises there.
2. Use [take-home Lab 1](take-home/1-enforce-merge-policy.md) to configure rules, confirm neutral CODEOWNERS, and prepare a separate dependency PR with real failure and repair evidence.
3. Configure `workshop-demo` before installing [release-simulation.yml](starter/release-simulation.yml). Follow [Lab 2](take-home/2-approve-a-release.md), including main-only policy, solo approval, exact-SHA checks, negative test, and receipt inspection.
4. Keep separate safe application and dependency-training PRs. During the demonstration, merge only the safe one; close the fixture PR without merging.
5. Save labeled recordings/transcripts only from actual runs, with source URLs, revision, date, and kit version. If no recording exists, say so. [Expected-result examples](fixtures/evidence-examples.md) are not recordings.

## Run the room

| Event minute | Action |
|---:|---|
| 00-08 | Verify prework and resume the existing codespace; triage small remaining issues |
| 08-15 | Baseline and functional blind spots |
| 15-21 | Three-row threat model |
| 21-38 | Individual code fix/test; start scans |
| 38-53 | Callback to code results; dependency failure then repair |
| 53-65 | Individual secret-protection attempt and clean retry |
| 65-75 | Merge-policy demonstration; helpers revisit pending individual results |
| 75-83 | Release demonstration and incident card |
| 83-90 | Closing, honest evidence, take-home resume point |

After a four-minute wait, continue with the next independent activity and revisit the result at its callback. This is a facilitation threshold, not an Actions service promise. Do not repair a dependency before its initial failure is observed and then count the cycle as complete.

At minute 80, stop starting new troubleshooting/edit cycles. At minute 83, begin closing regardless of queues. Keep missing outcomes pending/incomplete. Never bypass secret protection, required checks, code-scanning policy, or approval to finish on time.

At closing, have learners save and push intended safe work and explicitly stop their own codespace. Closing a tab does not stop compute; stopped storage still counts. Keep forwarded ports private. Preserve needed work and evidence before deletion, and reopen the same space for take-home.

## Optional identity practice

During lesson 1's existing seven minutes, identify the job's GitHub App installation identity and read-only scope alongside the CI commands. Point to [the self-service workload-identity lab](take-home/4-workload-identity.md) for later practice. Offer its two-job permission exercise as optional take-home or a separately scheduled follow-along. Do not add a fourth required individual outcome to the 75-minute core; keep the secret exercise and all timeboxes unchanged.

Learners copy the bundled optional workflow in Codespaces and install it through a reviewed PR. Its jobs execute only in Actions. Do not run the proof with the developer `GITHUB_TOKEN` or print either credential. OIDC remains reading only; no cloud account, PAT, or new app is required.

## Maintain and publish this template

Work only in a checkout of `frye/pets-devsecops-workshop-template`. From its root:

```bash
python3 -m unittest discover -s content/devsecops/tests -v
python3 content/devsecops/scripts/validate-kit.py
bash -n content/devsecops/scripts/prepare-devsecops.sh
actionlint content/devsecops/starter/ci.yml content/devsecops/starter/dependency-review.yml content/devsecops/starter/release-simulation.yml content/devsecops/starter/token-permissions.yml
python3 content/devsecops/scripts/build-kit.py --refresh-manifest --output-dir /path/to/template-output
python3 content/devsecops/scripts/build-kit.py --output-dir /path/to/second-output
```

Use an isolated validation environment with Flask dependencies and PyYAML. Tests use the bundled baseline and independent-history temporary repositories, not the original source's Git objects. These are author tools, not learner prerequisites.

For the author test suite on Windows, select the Git Bash executable explicitly before invoking Python. This avoids Python selecting the unrelated Windows Subsystem for Linux launcher:

```bash
export WORKSHOP_BASH="$(cygpath -w "$BASH")"
```

Run that command in Git Bash only. The learner's helper invocation already runs in their chosen Bash terminal.

The builder verifies baseline fingerprints, source metadata, and payload inventories, then creates a deterministic complete-template ZIP and SHA-256 sidecar. Refresh manifests only after reviewing changes; it does not download or bless a different application baseline. Compare two archive hashes. Output must be outside the checkout.

Publish the whole repository layout, including `app/`, bundled `content/devsecops`, and exactly the two active core workflows. Keep optional starters inactive. Use an unused immutable version in this repository; do not modify previous companion releases.

All maintainer commits, PRs, releases, and setting changes target this new template only. Source repositories in `template-source.json` are read-only inputs. Update them deliberately through a reviewed PR here, with provenance and renewed exercise checks. Never push to the original Pets or earlier companion repository.

## Checkpoint

The application and complete lessons ship together, bundled paths work without another fetch, and readiness separates automated checks from fresh-copy and human/Codespaces checks. Preserve that distinction in event invitations.

## Resources

[GitHub template repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template), [Git archive](https://git-scm.com/docs/git-archive), and [Actions usage](https://docs.github.com/en/billing/concepts/product-billing/github-actions).

[Codespaces creation](https://docs.github.com/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository), [billing](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces), and [stop/start](https://docs.github.com/en/codespaces/developing-in-a-codespace/stopping-and-starting-a-codespace) support the primary route.
