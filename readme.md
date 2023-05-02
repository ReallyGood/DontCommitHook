# *Don’t Commit* Hook 🚫

A handy global pre-commit hook that keeps your Git repositories safe by catching temporary or potentially harmful changes marked with "NOCOMMIT" or "DONTCOMMIT" before they get committed.

Have you ever left a dangerous change like this in your code and forgot to remove it before committing?

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

No worries! DontCommitHook has your back and will stop the commit. 🛡️

## 🚀 Quick Setup Guide

**The one-liner:**
```bash
mkdir -p ~/git-hooks && curl -sL https://raw.githubusercontent.com/ReallyGood/DontCommitHook/main/pre-commit -o ~/git-hooks/pre-commit && chmod +x ~/git-hooks/pre-commit && git config --global core.hooksPath ~/git-hooks
```

This command performs all the following steps, so you don’t have to run them manually:
1. Download the `pre-commit` file from this repo.
2. Create a `git-hooks` directory in your home folder (skip if it already exists).
3. Move the `pre-commit` file to `~/git-hooks`.
4. Make the `pre-commit` file executable.
5. Set the global hooks path to yout new hooks folder.

That’s it! The global pre-commit hook is now active for all your Git repos. It will prevent commits containing temporary or dangerous changes based on the presence of "NOCOMMIT" or "DONTCOMMIT" strings in staged chunks (so keep them close to the changes you want to block).

What sets this hook apart is its effortless integration with all our repositories without any extra configuration. Plus, it plays nicely with other hooks, including the beloved Husky hook system.

## 🤔 Questions or Help

If you have any questions or need help, feel free to open an issue or submit a pull request. We’re here to help!

Happy coding! 😄
