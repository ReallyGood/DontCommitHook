# DontCommitHook 🚫💥

A nifty global pre-commit hook that keeps your Git repos safe by catching temporary or dangerous changes marked with "NOCOMMIT" or "DONTCOMMIT" before they slip in. 🛡️

Ever left a dangerous change like this in your code and forgot to remove it before committing?

```javascript
// DONTCOMMIT: Bypassing the login for quick testing
if (username === "admin" || true) {
  grantAccess();
}
```

Or hardcoded secrets like this?

```javascript
const apiKey = "1234567890abcdef"; // nocommit
```

No worries! DontCommitHook has your back and will stop the commit. 🛑

## 🚀 Quick Setup Guide

1. Download the `pre-commit` file from this repo.
2. Run `mkdir ~/git-hooks` to create a `git-hooks` directory in your home folder (skip if it already exists).
3. Move the `pre-commit` file to `~/git-hooks`.
4. Run `chmod +x ~/git-hooks/pre-commit` to make it executable.
5. Set the global hooks path: `git config --global core.hooksPath ~/git-hooks`.

That’s it! The global pre-commit hook is now active for all your Git repos. It will prevent commits containing temporary or dangerous changes based on the presence of "NOCOMMIT" or "DONTCOMMIT" strings in staged chunks (so keep them close to the changes you want to keep out). 🎉

## 🤔 Questions or Help

If you have any questions or need help, feel free to open an issue or submit a pull request. We’re here to help!

Happy coding! 😄
