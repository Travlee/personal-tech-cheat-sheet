# Git

`git init` - Initializes git for the pwd; adds git files.

`git add [<file>, <file>, ...]` - Tracks new file(s).

`git rm --cached <file>` - Stops tracking file in repo, doesn't delete from filesystem.

`git status` - Shows state of current branch.

`git ls-files` - Show tracked files.

`git commit -[a=AllTracked, m=Message, ] --[ammend=Ammends previous commit, no-edit=Keeps commit message, reuse-message HEAD=Keeps commit msg from HEAD, ] <msg?>` - Makes a commit.

`git diff <file?>` - Shows changes.

`git log [--graph?]` - Shows log of commits.

`git log --all -- <filename>` - Searches through git history for file.

`git branch -[d=Delete, m=Rename] <branch> <newname>` - Shows branches.

`git checkout -[b=NewBranch] <branch>` - Changes current branch.

`git checkout -- <file>` - Resets a file to HEAD, ignoring local changes.

`git merge [--squash="Collaspe all commit in merging branch to single."] <branch>` - Merge branch into current.

`git mergetool` - See merge conflicts.

`git remote add origin <url>.git` - Adds remote origin to repo.

`git remote -v` - Shows your current remote origin/fetch urls.

`git reset [--hard="Ignores local changes", --soft="Keeps local changes"]` - Resets all files to last commit.

`git reset --soft HEAD~1` - Undo last commit and drop changes into working dir.

`git push -u origin <branch>` - Sets the origin as the default for push calls, then pushes branch.

`git push origin --delete <branch>` - Deletes remote branch.

`git stash -[u=Untracked Files, ]` - Stash working dir.

`git stash list` - Lists all stash objects.

`git stash pop` - Pops the top-most stash entry to working dir and removes entry from stash list.

`git stash apply` - Pops the top-most, keep changes in stash.

`git stash save "desc."` - Saves working dir with name/desc.

`git stash drop stash@{0}` - Drops stash at index 0.

`git stash push -[u untracked] -[m message] path/to/file` - Stash a single untracked file

`git show --pretty="" --name-only <commit hash>` - Shows new files in commit.

## Examples

### Merge Conflicts

```bash
# Checkout ours/theirs to solve merge conflicts
git checkout [--ours, --theirs] filename.c
git add filename.c
git pull origin master
```

### Rebase Git-flow

```bash
# update master first
git checkout master && git pull

# get on feature branch to rebase
git checkout feature-branch

# Add a tag to go back to, should something go wrong
git tag BACKUP

# rebase feature to master
git rebase master

# solve merge issues, if any
git mergetool

# continue rebase after fixing merge issues
git rebase --continue

# discard rebase if needed
# git rebase --abort
# git reset --hard BACKUP

# force-push to remote feature branch
git push -f
```

### Git Add Patch-mode

```bash
# enter patch-mode to select hunks of a file to be commited
git add -p

# HELP
# y - stage this hunk
# n - do not stage this hunk
# q - quit; do not stage this hunk nor any of the remaining ones
# a - stage this hunk and all that follow
# d - do not this hunk or any that follow
# s - split current hunk into more
# ? - help
```

### Replace local changes with Remote

```bash
# fetch changes from remote
git fetch

# reset your local to remote
git reset --hard origin/remote
```

### Git Tagging

#### Make Tags
You can make an annotated tag for a release version:
`git tag -a v0.0.1`

Adding a message to the tag:
`git tag -a v0.0.1 -m "Marking first usable version of our lovely software!"`

#### Display tags

`git tag`, `git tag -l 'v0.0.*'`, `git tag -l -n3` - Listing tags

`git show v0.0.1` - Shows all tag info

#### Push Tags

`git push origin <tag>` - Safest way to push tags; just push the one you for sure want at remote
