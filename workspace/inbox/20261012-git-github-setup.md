# Task note / 任務紙條 — Set up Git + GitHub for this folder

- **Date / 日期**: 2026-10-12
- **From / 發自**: Wailan 洄瀾 (Leader)
- **To / 給**: Taroko 太魯閣 (Member)
- **Requested by / 小隊長需求**: put this folder under git and publish it to GitHub, using GitHub CLI (`gh`) to handle everything.

---

## 1. What to do / 做什麼

Turn the project folder into a git repository and push it to GitHub.

**Captain's explicit decisions (already confirmed):**
- Repo name: **`my-team`**
- Visibility: **public** — the captain chose this knowingly; everything in the folder will be visible to the whole internet. Do not re-ask, but repeat the fact in your handoff.
- Tool: **GitHub CLI (`gh`)** — already installed and logged in as account `411230072-arch`. Do **not** run `gh auth login`, do **not** create tokens.

**Steps, in this order:**

1. `git init` in `C:\Users\Hans Davilmar\Documents\my-team` (use default branch `main`).
2. Create `.gitignore` in the folder root containing at least:
   ```
   .Rhistory
   .DS_Store
   Thumbs.db
   desktop.ini
   ```
   (That `.Rhistory` in `workspace/inbox/` is auto-generated editor junk — it must NOT go to GitHub. The empty one is still ignored for cleanliness.)
3. Double-check no secrets are about to be committed: no tokens, no passwords, no `.env` files anywhere in the folder. If you find any, STOP and hand it back to the leader.
4. First commit, e.g. message: `init: team workspace + BMI calculator app (zh-TW)`
5. Create the public repo and push in one flow:
   `gh repo create my-team --public --source=. --remote=origin --push`
6. Verify (see "done" below), then write your report.

## 2. Format / 什麼格式

- Work happens directly in the project folder — **never delete any file**, never modify `workspace/shared/`, never touch the other AI's files except `.gitignore` (new) which you create.
- Everything already in the folder gets committed (AGENTS.md, leader/member files, opencode.json, workspace tree) — that is intended.
- Report saved as a **new file** in `workspace/outbox/`: `20261012-git-github-setup.md`, plus a one-line handoff at the very top.
- Report language: 繁體中文（台灣用語）.

## 3. Done looks like / 怎樣算做完

1. `git status` reports a clean tree (nothing untracked / nothing to commit).
2. `git log` shows the initial commit.
3. `gh repo view` shows repo **`411230072-arch/my-team`**, visibility **public**, and the files are visible on github.com.
4. The repo tree contains the whole workspace (`AGENTS.md`, `workspace/inbox/...`, `workspace/outbox/...`, `workspace/shared/...`).
5. `.Rhistory` is **not** in the repo (check the file list on GitHub or `git ls-files`).
6. Report file in outbox includes:
   - the exact repo URL,
   - a copy-paste daily-use command cheat sheet for the captain:
     `git add .` → `git commit -m "..."` → `git push`
     (and `gh repo view --web` to open the repo in a browser),
   - the one-line handoff at top: what you did, anything to watch, ready or not.

When finished, STOP and tell the captain: "Done. Please go back to the leader for a check." 🚫 Do not call the leader directly.
