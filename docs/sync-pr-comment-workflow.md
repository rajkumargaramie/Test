# Sync PR Comment to Linked Issue

## What it does

Automatically copies comments from pull requests to their linked issues, keeping discussions synchronized.

## How it works

1. Someone comments on a pull request
2. The workflow finds any linked issue (referenced with `fixes #123`, `closes #456`, etc.)
3. The comment is copied to the linked issue with attribution
4. Bot comments are automatically skipped

## Trigger

Runs automatically when a comment is created on a pull request.

## Usage

**In your pull request description or title, reference an issue:**

```
Fixes #1
Closes #2
Resolves #3
```

**Then comment on the PR:**

Any comment you add will be automatically synced to the linked issue.

## Example

If PR #10 has "Fixes #5" in its description, and you comment:

> "Updated the implementation based on feedback"

The workflow will create this comment on issue #5:

> ↩️ **Update from [PR #10](link)**
> 
> > Updated the implementation based on feedback
> 
> _Comment by [@username](link)_

## Excluded bots

- github-actions[bot]
- github-actions
- copilot
