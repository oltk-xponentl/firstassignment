## First assignment, step by step

1. Initialized the repository and created `project.txt`.
2. Made multiple commits, adding some text and a llokuma recipe to project.txt, with the last commit having a wrongly formatted message.
3. Rewrote history using `git rebase -i --root`, squashing 2 commits and changing the third commit message for the cleaned-up history.
4. Committed a temporary change, then ran `git reset --hard HEAD~1` to remove the commit from the branch tip.
5. Investigated the lost commit by running `git reflog` to find the lost commit hash, which was `3e2f653`.
6. Created a branch from that hash by running: `git checkout -b remove-ingredients 3e2f653`.
7. Tagged the cleaned-up commit with `v1.0`: `git tag -a v1.0 -m "Version 1.0 release"`.
8. Pushed branches and tags to GitHub.
9. Created new branch `add-readme` to add README.md file.
10. Commited the new README.md file with additional info.
11. Pushed the `add-readme` branch to GitHub and opened PR to merge into main.
12. Merged the `add-readme` branch into main. 

## Git alias (not visible in commit history)

I created a global git alias called `lg`. The alias command used is:

`git config --global alias.lg "log --graph --pretty=format:'%h %ad | %s %d [%an]' --date=short --all --decorate"`

What does `lg` do?
- Shows commit history as a graph
- Prints short commit hash and date
- Shows the commit subject, decoration (branch/tag), and author
- Works across all refs, so it helps to see branches and tags