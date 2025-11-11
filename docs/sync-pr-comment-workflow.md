# Sync PR Comment to Linked Issue

Automatically syncs PR comments and descriptions to all linked issues, keeping discussions in one place.

## Features

- ✅ Syncs PR description on first edit (and subsequent edits)
- ✅ Syncs comments to **all** linked issues (keyword-based and manual)
- ✅ Updates synced content when edited
- ✅ Deletes synced comments when PR comment is deleted
- ✅ Skips bot comments automatically

## How to link issues

**Option 1: Keywords** - Add to PR description:
```
Fixes #1
Closes #2
Resolves #3
```
Supported: `close/closes/closed`, `fix/fixes/fixed`, `resolve/resolves/resolved`

**Option 2: Manual** - Use GitHub's "Development" sidebar to link issues

## Comment format

PR comment → Creates on linked issue:
```
↩️ Update from PR #10

> Your comment here

Comment by @username
```

## Limits & Exclusions

- Max 50 linked issues per PR
- Excluded bots: `github-actions[bot]`, `github-actions`, `copilot`

## Permissions

Required: `issues: write`, `pull-requests: read`
