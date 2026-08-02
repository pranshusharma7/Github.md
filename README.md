# Git & GitHub — Basic Commands Cheat Sheet

## 1. Setup (ek baar karna hota hai)
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list                # saari config check karne ke liye
```

## 2. Repository Banana / Lena
```bash
git init                         # naya local repo banao current folder mein
git clone <repo-url>             # existing GitHub repo ko clone karo
```

## 3. Basic Workflow (Daily Use)
```bash
git status                       # kaunse files change hui hain, dekho
git add <file>                   # ek specific file stage karo
git add .                        # saari changed files stage karo
git commit -m "message"          # staged changes ko commit karo
git log                          # commit history dekho
git log --oneline                # short history (ek line per commit)
```

## 4. Branching (Sabse Important for Teamwork)
```bash
git branch                       # saari branches list karo
git branch <branch-name>         # nayi branch banao
git checkout <branch-name>       # branch switch karo
git checkout -b <branch-name>    # naya branch banao aur switch bhi kar do (shortcut)
git switch <branch-name>         # newer command, checkout jaisa hi
git merge <branch-name>          # ek branch ko current branch mein merge karo
git branch -d <branch-name>      # branch delete karo
```

## 5. Remote Repository (GitHub se connect)
```bash
git remote add origin <repo-url> # local repo ko GitHub repo se link karo
git remote -v                    # connected remotes dekho
git push origin <branch-name>    # local commits ko GitHub par bhejo
git push -u origin main          # pehli baar push karte waqt (upstream set karta hai)
git pull origin <branch-name>    # GitHub se latest changes lao aur merge karo
git fetch                        # sirf changes dekho, merge mat karo
```

## 6. Undo / Fix Karna
```bash
git restore <file>               # working directory mein changes undo karo (unstaged)
git restore --staged <file>      # file ko unstage karo (commit ke liye ready nahi)
git reset --soft HEAD~1          # last commit undo karo, changes rakho
git reset --hard HEAD~1          # last commit + changes dono delete (⚠️ careful)
git revert <commit-hash>         # ek commit ko safely undo karo (naya commit banata hai)
```

## 7. Comparing & Inspecting
```bash
git diff                         # unstaged changes dekho
git diff --staged                # staged changes dekho
git show <commit-hash>           # ek specific commit ka detail dekho
```

## 8. Stashing (Temporarily changes side mein rakhna)
```bash
git stash                        # current changes save karke clean state mein aao
git stash list                   # saari stashes dekho
git stash pop                    # last stash wapas laao aur delete karo
git stash apply                  # stash wapas laao par list se delete mat karo
```

## 9. Tags (Releases ke liye)
```bash
git tag v1.0                     # tag banao
git tag                          # saari tags list karo
git push origin v1.0             # tag ko GitHub par push karo
```

## 10. GitHub-Specific Concepts (CLI se nahi, workflow se related)
- **Fork** — kisi aur ke repo ki apni copy GitHub par banana
- **Pull Request (PR)** — apni branch ke changes ko original/main repo mein merge karne ka request
- **Issues** — bugs, features, ya tasks track karne ka tool
- **Clone vs Fork** — clone = repo ko local machine par lana; fork = repo ki copy apne GitHub account mein banana

## 11. GitHub CLI (Optional, agar `gh` install hai)
```bash
gh repo create                   # naya repo banao GitHub par (terminal se hi)
gh repo clone <repo>              # clone karo
gh pr create                     # pull request banao
gh pr list                       # saari open PRs dekho
gh issue create                  # naya issue banao
```

## Quick Daily Flow (Yaad Rakhne Ke Liye)
```bash
git status
git add .
git commit -m "message"
git pull origin main
git push origin main
```

---
### Study Tips
- Pehle `init → add → commit` cycle achhe se practice karo.
- Phir `branch → merge` samjho — yeh real teamwork mein sabse zyada use hota hai.
- Last mein `remote → push/pull` aur GitHub PR workflow practice karo apne kisi practice repo par.
