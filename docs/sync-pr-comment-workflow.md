# Sync PR Comment to Linked Issue

## What it does

Automatically copies comments from pull requests to **all** their linked issues, keeping discussions synchronized across your workflow.

## How it works

1. Someone comments on a pull request
2. The workflow discovers **all** linked issues using two methods:
   - Keyword-based links in PR title/body (`fixes`, `closes`, `resolves`)
   - Manually linked issues via GitHub's UI
3. The comment is synced to **all** linked issues with proper attribution
4. Bot comments are automatically skipped

## Trigger

Runs automatically when a comment is created on a pull request.

## Linking issues to PRs

### Method 1: Using keywords in PR description or title

The workflow recognizes these keywords (case-insensitive):

- `close`, `closes`, `closed`
- `fix`, `fixes`, `fixed`
- `resolve`, `resolves`, `resolved`

**Examples:**
```
Fixes #1
Closes #2
Resolves #3
Fixed #4 and closes #5
```

### Method 2: Manual linking via GitHub UI

You can also manually link issues to a PR using GitHub's "Development" sidebar. The workflow will detect these automatically.

## Limits

- **Maximum issues per PR:** Up to 50 linked issues
- The workflow syncs comments to ALL linked issues found (both keyword-based and manually linked)

## Comment format

When you comment on a PR, the workflow creates this comment on each linked issue:

```
↩️ **Update from [PR #10](link)**

> Your comment text here

_Comment by [@username](link)_
```

## Example workflow

**Scenario:** PR #10 has:
- "Fixes #5" in its description
- Issue #8 manually linked via GitHub UI

**Action:** You comment on PR #10:
> "Updated the implementation based on feedback"

**Result:** Both issue #5 and issue #8 receive the synced comment with attribution.

## Excluded accounts

The following bot accounts are automatically excluded from syncing:
- `github-actions[bot]`
- `github-actions`
- `copilot`

## Permissions required

The workflow requires:
- `issues: write` - To create comments on linked issues
- `pull-requests: read` - To read PR details and linked issues

## Troubleshooting

**No comments syncing?**
- Check that issues are properly linked using keywords or manual linking
- Verify the commenter is not in the excluded bots list
- Review the workflow run logs for detailed information
