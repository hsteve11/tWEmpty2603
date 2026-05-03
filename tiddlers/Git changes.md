Here's the basic Git workflow for tracking changes to your file:

## 1. Make your initial commit

If you haven't already, commit the starting version of your HTML file:

```bash
git add index.html
git commit -m "Initial version of HTML file"
```

## 2. Edit the file normally

Open `index.html` in VS Code and make whatever changes you want — edit text, add elements, tweak styles, etc. Save the file.

## 3. See what changed

```bash
git diff
```

This shows you exactly which **lines** were added, removed, or modified — not a full rewrite. Git tracks changes at the line level.

## 4. Stage and commit the changes

```bash
git add index.html
git commit -m "Describe what you changed"
```

Each commit only stores the **diff** (the differences), not a full copy of the file. So you're never "rewriting" the whole thing — Git handles that for you.

## Key things to know

- **`git diff`** is your best friend. Run it before committing to review exactly what you changed.
- **`git log --oneline`** shows your commit history so you can see the evolution.
- **`git checkout -- index.html`** will undo all unsaved changes and revert to the last committed version (a safety net).
- **Commit messages matter.** Write something short but meaningful like `"add navigation bar"` or `"fix broken image link"` instead of just `"update"`.

That's really it — just edit, save, `git diff` to review, `git add`, `git commit`. Git does the heavy lifting of tracking what changed between versions.