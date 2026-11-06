# Issue tracker: GitHub

Issues and specs for this repo live in GitHub Issues at `fnaufel/my-running`. Use the `gh` CLI with `--repo fnaufel/my-running` for issue operations.

## Conventions

- Create an issue: `gh issue create --repo fnaufel/my-running --title "..." --body "..."`
- Read an issue: `gh issue view <number> --repo fnaufel/my-running --json number,title,body,labels,comments`
- List issues: `gh issue list --repo fnaufel/my-running --state open --json number,title,body,labels,comments` with suitable label and state filters.
- Make an issue a sub-issue: `gh issue create --repo fnaufel/my-running --parent <parent> ...`, or `gh issue edit <parent> --repo fnaufel/my-running --add-sub-issue <child>`.
- Comment: `gh issue comment <number> --repo fnaufel/my-running --body "..."`
- Apply or remove labels: `gh issue edit <number> --repo fnaufel/my-running --add-label "..."` or `--remove-label "..."`
- Close: `gh issue close <number> --repo fnaufel/my-running --comment "..."`

## Pull requests as a triage surface

**PRs as a request surface: no.** Set this to `yes` if this repo later treats external PRs as feature requests.

## When a skill says "publish to the issue tracker"

Create a GitHub issue in `fnaufel/my-running`.

## When a skill says "fetch the relevant ticket"

Read the referenced GitHub issue.

## Wayfinding operations

Used by `/wayfinder`. The map is one issue with child issues as tickets.

- Map: an issue labelled `wayfinder:map`, holding Notes, Decisions-so-far, and Fog.
- Child ticket: a sub-issue of the map labelled `wayfinder:<type>`, where type is `research`, `prototype`, `grilling`, or `task`. If sub-issues are unavailable, link it from a task list in the map and put `Part of #<map>` at the top of its body.
- Blocking: use GitHub's issue dependencies. If unavailable, put `Blocked by: #<n>, #<n>` near the top of the child body. A ticket is unblocked when every blocker is closed.
- Frontier: choose the first open, unassigned child in map order with no open blocker.
- Claim: assign the ticket to the working developer before starting.
- Resolve: comment with the answer, close the child, and add a short context pointer to the map's Decisions-so-far.
