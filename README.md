# node_mandatory_2
Auth application for the mandatory 2 assignment in my Node.js course.

## Connect an existing local project to this repository

```bash
cd <path/to/your-project>
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/NikoZK/node_mandatory_2.git
# This repo already has commits, so allow unrelated histories on first pull.
git pull origin main --allow-unrelated-histories
git push -u origin main
```

If `git pull` reports conflicts, resolve them, then run `git add .` and `git commit` (or `git commit -m "Resolve merge conflicts"`) before `git push`.
