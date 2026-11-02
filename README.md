# Model Exam Question 1: Repair Conflicting Runbook Updates

**Total: 30 marks | Submit one PDF**

## Problem statement

Your team has two proposed updates to a support runbook. Both contributors edited the same escalation line differently. Combine their work on an integration branch, resolve the real merge conflict using the policy below, then review and merge your pull request.

This is a text-only Git task. No application programming required. Starter main is valid; fault is incompatible edits on two prepared branches. Conflict appears when you merge both, not when cloning.

## Before starting

Use Git Bash or Bash with Git on macOS/Linux, free GitHub account and a text editor. Sign in, configure Git author name/email and test push authentication before tasks. Do not expose tokens/passwords. No partner, paid tools or cloud services required. GitHub website is sufficient; GitHub CLI output is an accepted optional equivalent for real PR evidence.

Create your own repository using the fork instructions below, then clone YOUR repository and enter its folder. Wait until starter files appear on GitHub before cloning. Do not push to shared instructor starter. Resolve authentication/setup problems before starting. Preparation is not graded. Instructor private reference repositories are not student forks or peer-reviewed production projects.

## Starter and setup

https://github.com/kalviumcommunity/model-runbook-conflict

Select **Fork > Create a new fork**, choose your own account, and UNCHECK **Copy the main branch only**. Use a fork, not Use this template: fork preserves shared branch history needed for this conflict. Forking is guided preparation, not an assessed new command. Starter has `main`, `contributor/checks` and `contributor/escalation`. After cloning your fork, run `git branch -r` and confirm `origin/contributor/checks` and `origin/contributor/escalation` are present. If either is missing, ask instructor to fix preparation before tasks. Start on main with clean working tree. Do not change starter branch contents before merging.

Files: `runbook.txt`, `POLICY.md` and this README. No installations or other project files needed. Do not edit POLICY.md or README.md.

## Required final runbook

Policy: escalate to the support lead, preserve both contributors' useful additions, keep lines in this order:

```text
Support runbook
Escalation: contact support lead.
Before escalation: record the error message.
After escalation: record the ticket number.
```

## Task 1: Inspect the proposed updates

1. On main, run `git status`, `git branch -a` and `git log --oneline --graph --all`.
2. Read `POLICY.md` using `cat POLICY.md`.
3. Display both contributor files:
   ```bash
   git show origin/contributor/checks:runbook.txt
   git show origin/contributor/escalation:runbook.txt
   ```
4. In PDF write two short points: which line differs, and which final escalation wording policy requires. Both useful additions must survive resolution.

Evidence: initial clean main, branches/history, policy, both proposed files and your two points.

## Task 2: Resolve the conflict

1. Create integration branch: `git switch -c integrate/runbook`.
2. Merge first update: `git merge origin/contributor/checks`.
3. Merge second update: `git merge origin/contributor/escalation`. A conflict is expected, not a setup failure. Capture conflict message, `git status` and `cat runbook.txt` BEFORE editing.
4. Edit only `runbook.txt` to match the four required lines above exactly. Remove all conflict markers. Do not choose one entire branch and lose the other contributor's addition.
5. Run `git add runbook.txt`, then `git commit -m "Resolve runbook conflict using team policy"`. Show `cat runbook.txt`, `git log --oneline --graph --all` and clean `git status`.

Evidence: integration branch, merges, actual conflict and marker content, corrected file, completed merge commit/history and clean status. No rebase, force push, reset or unrelated edits.

## Task 3: Open the pull request

1. Run `git push -u origin integrate/runbook` and capture successful push.
2. Open PR in YOUR repository from `integrate/runbook` into `main`.
3. Use a useful title. In description include: conflicting escalation line, policy-based resolution, both preserved additions and checks performed (final file matches policy; conflict markers removed; working tree clean).
4. Capture PR title, description, branch direction and OPEN state before merging.

Evidence: push and open PR with requested details. GitHub may suggest instructor repository as PR base because this is a fork. Change base repository to YOUR fork and base branch to main. Do not open PR against instructor repository.

## Task 4: Review and finish

1. Leave one ordinary self-review PR comment confirming that you checked all four final lines against policy and both additions remain. No approval or partner needed. Capture actual comment.
2. Merge PR on GitHub. Use **Create a merge commit** to preserve the branch merge history. Capture MERGED state and target main.
3. Run `git switch main`, `git pull origin main`, `cat runbook.txt` and `git status`. Show updated local main with correct four lines and clean tree.
4. In PDF write one sentence explaining why removing conflict markers alone does not prove correct resolution.

Evidence: comment, merged PR, successful pull, final main/content/status and explanation. Do not delete branches until evidence is complete.

## Submission

Submit one PDF for this question, with four task headings and labelled genuine screenshots plus requested short answers. Multiple readable screenshots allowed. Capture intermediate states before continuing. No separate URL submission, video, code archive, specific PDF filename or layout required. Evidence must show actual commands/results or actual GitHub states. Never fabricate output. Do not include personal credentials.

Only explicit task work is graded. Give partial credit within criteria, with no duplicate deductions or automatic whole-question zero. No presentation, identity, repository-name, metadata or screenshot-count marks. Equivalent correct commands and ordinary OS/path/hash differences accepted. Exact required file content and branch direction remain technical requirements. No second reviewer or self-approval required.

## Rubric

| Task | Explicit criteria | Marks |
|---|---|---:|
| 1 | Clean main plus branch/history inspection (2); both contributor contents and policy shown (2); differing line and correct policy outcome identified (2) | 6 |
| 2 | Integration branch and both merge attempts (2); actual conflict/status/markers captured (2); correct escalation and both additions preserved, no markers (4); completed merge/history and clean tree (2) | 10 |
| 3 | Successful integration push (2); open PR into main with useful title/direction (2); description covers conflict, policy, preserved additions and actual checks (3) | 7 |
| 4 | Actual policy-based self-review comment (2); PR merged into main using merge commit (2); local main pulled with correct content/clean tree (2); correct explanation (1) | 7 |
| **Total** | | **30** |
