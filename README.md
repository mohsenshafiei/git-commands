### Git-Commands
#### Useful commands that we can use in our project

##### Add a file to the next commit
```bash
git add <file>
```

##### Delete a file in the next commit
```bash
git rm <file>
```

##### Rename a file in the next commit
```bash
git mv <file>
```

##### Stage commits in hunks interactively
```bash
git add -p
```

##### Save un-commited work
```bash
git stash
```

##### List changes
```bash
git stash list
```

##### Show contents of stash
```bash
git stash show stash@{0}
```

##### Apply the last stash
```bash
git stash apply
```

##### Apply a specific stash
```bash
git stash apply stash@{0}
```

##### Keep untracked files
```bash
git stash --include-untracked
```

##### Keep all files (even ignored ones!)
```bash
git stash --all
```

##### Name stashes for easy reference
```bash
git stash save 'WIP: making progress in foo'
```

##### Start a new branch from a stash
```bash
git stash branch <optional stash name>
```

##### Grab a single file from a stash
```bash
git checkout <stash name> -- <file name>
```

##### Remove the last stash and applying changes
```bash
git stash pop
```

##### Remove the last stash
```bash
git stash drop
```

##### Remove the nth stash
```bash
git stash drop stash@{n}
```

##### Remove all stashes
```bash
git stash clear
```

##### Lightweight tag
```bash
git tag <tag-name>
```

##### Annotated tag
```bash
git tag -a <tag-name> -m 'your message for tag'
```

##### List all the tags in a repo
```bash
git tag
```

##### List all tags, and what commit they are pointing to
```bash
git show-ref --tags
```

##### List all the tags pointing to a commit
```bash
git tag --points-at <commit>
```

##### Looking at the tag, or tagged content
```bash
git show <tag-name>
```

##### No Fast-Forward Merging
```bash
git merge --no-ff
```

##### Enabling ReReRe (Reuse Recorded Resolution)
```bash
git config rerere.enabled true
```
 use `--global` flag to enable for all projects

##### What changes since yesterday
```bash
git log --since='yesterday'
git log --since='2 weeks ago'
```

##### Log files that have been moved or renamed
```bash
git log --name-status --follow -- <file>
```

##### Search for commit messages that match a regular expression
```bash
git log --grep <regexp>
```
can be mixed with other git flags

##### Show commit and contents
```bash
git show <commit>
```

##### Show file changed in commit
```bash
git show <commit> --stat
```

##### Look at a file from another commit
```bash
git show <commit>:<file>
```

##### un-staged changes
```bash
git diff
```

##### staged changes
```bash
git diff --staged
```

##### Which branches are merged with master, and can be cleaned up?
```bash
git	branch --merged	master
```

##### Which branches are not merged with master yet?
```bash
git	branch --no-merged master
```

##### Overwrite the working area file with the staging area version from the last commit
```bash
git checkout -- <file_path>
```

##### Checkout a file from a specific commit
```bash
git checkout <commit> -- <file-path>
```

##### Restored a deleted file
```bash
git checkout <deleting-commit>^ -- <file_path>
```

##### Clear your working area by deleting untracked files.
```bash
git clean
```

##### to see what would be deleted
```bash
git clean --dry-run
```

##### To see what files and directories be deleted
```bash
git clean -d --dry-run
```

##### To clean your working area by deleting untracked files and directories
```bash
git clean -d -f
```

##### Move head to the last commit in repository area
```bash
git reset --soft
```

##### Move head to the last commit in repository area and copy files to stage
```bash
git reset --mixed
```

##### Move head to the last commit in repository area and copy files to stage and Working area
```bash
git reset --hard
```

##### Undo a git reset with `ORIG_HEAD`
```bash
git reset ORIG_HEAD
```

##### The safe reset is revert
```bash
git revert <commit>
```

##### Make changes to the previous commit
```bash
git commit --amend
```

##### Interactive rebase with shortcut
```bash
git rebase -i <commit_to_fix>^
```

##### Rebase Options
- pick
  * keep	this	commit
- reword
  * keep	the	commit,	just	change	the	message
- edit
  * keep	the	commit,	but	stop	to	edit	more	than	the	message
- squash
  * combine	this	commit	with	the	previous	one.	stop	to	edit	the message
- fixup
  * combine	this	commit	with	the	previous	one.	keep	the	previous commit	message
- exec
  * run	the	command	on	this	line	after	picking	the	previous	commit
- drop
  * remove	the	commit	(tip:	if	you	remove	this	line,	the	commit will	be	dropped	too!)

##### If Rebasing goes wrong
```bash
git rebase --abort
```

##### Viewing Remotes
```bash
git remote -v
```

##### Add upstream remote
```bash
git remote add upstream <repository_path>
```

##### To checkout a remote branch, with tracking
```bash
git checkout -t origin/feature
```

##### Tell git which branch to track the first time your push
```bash
git push -u origin feature
```

##### pull down all changes but doesn't change your local
```bash
git fetch
```

##### pulling down changes and change local
```bash
git pull
```

##### Pull, Fetch Cheat
```bash
git pull = git fetch && git merge
```

##### To see commits which haven't been published upstream yet
```bash
git cherry -v
```

##### Push One Tag to the remote
```bash
git push <tag_name>
```

##### Push tags to remote
```bash
git push --tags
```

##### Danger Zone: Never use this
```bash
git push -f
```

##### use ORIG_HEAD to undo merges
```bash
git reset --merge ORIG_HEAD
```

#####  to find out about changes to a file
```bash
git blame <filename>
```

##### use the diff-filter flag on log to see all commits where the file was deleted:
```bash
git	log	—diff-filter=D -- <deleted_file>
```

##### git blame using the parent commit
```bash
git	blame	<commit>^	--	<deleted_file>
```

##### Git blame by lines
```bash
git	blame	-L1,5	-- <file>
```

##### To find which commit introduced a bug
```bash
git bisect start <BAD_SHA> <GOOD_SHA>
```

##### Local setting per repository
```bash
git config <setting> <value>
```

##### Global setting apply to all repository
```bash
git config --global <setting> <value>
```

##### PR commit messages template
This pull request closes issue `#number`

> You can add a .github/ folder for your project to specify
templates for pull requests, issues, and contributing guidelines.
  - contributing.md
  - issue-template.md
  - pull-request-template.md
