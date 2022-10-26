# Bootcamp Study Material

## GIT
Open-source, distributed version control system

## Most common commands
### Create repository
- `git init`
- `git clone`

### Synchronizing
- `git merge`
- `git fetch`
- `git push`
- `git pull`

### Branching
- `git branch [ branch name ]`
- `git checkout [ branch name ]`
- `git merge [ branch ]`
- `git branch -d [ branch name ]`

### Make changes
- `git log`
- `git log --follow [ title ]`
- `git diff [ first branch ] [ second branch ]`
- `git show [ commit ]`
- `git show [ file ]`
- `git commit -m "[ descriptive message ]"`

### Redo commits
- `git reset [ commit ]`
- `git reset --hard [ commit ]`

## GIT branch
A pointer to changes made in a repository.
When a commit is made, Git stores a commit object* that contains a pointer to the snapshot of the content you staged.  A branch in Git is simply a lightweight movable pointer to one of these commits. The default branch name in Git is master. As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, the master branch pointer moves forward automatically.  

## GIT tags
A label used to indicate a specific point in a repository as being important. Checking out tags puts the repository in a “detached HEAD” state, in which if you make changes, then commit those changes, the tag won’t change and the new commit  won’t belong to any branch and will ONLY be readable by the commit hash.  
### Types of tags
- Lightweight: pointer to a specific commit, like a branch
- Annotated: objects that contain the tagger name, email, and date; they also have a tagging message
### Creating tags
- Lightweight: `git tag [ tag name ]-lw`
- Annotated: `git tag -a [ tag name ] -m [ message ]`
### Adding tags on past commits
- `git tag -a [ tag name ] [ complete or partial checksum of the commit ]`
### Pushing tags to remote
- Single tag: `git push origin [ tag name ]`
- Multiple tags: `git push origin ——tags`
### Deleting tags
- Local server: `git tag -d [ tag name ]-lw`
- Remote servers: `git push origin --delete [ tagname ]  `

## GIT commits
When you make a commit, Git stores a commit object that contains a pointer to the snapshot of the content you staged. This object also contains the author’s name and email address, the message that you typed, and pointers to the commit or commits that directly came before this commit (its parent or parents): zero parents for the initial commit, one parent for a normal commit, and multiple parents for a commit that results from a merge of two or more branches.  

## Stash command
It’s used when you want to record the current state of the working directory and the index without doing a commit, but want to go back to a clean working directory. Stashing takes the dirty state of your working directory — that is, your modified tracked files and staged changes — and saves it on a stack of unfinished changes that you can reapply at any time (even on a different branch).  

### Create a stash
- `git stash`
### Create a stash including the untracked files
- `git stash -u`
- `git stash --include-untracked`
### Create a stash with the `.ignored` files
- `git stash -a`
### Apply latest stashed work
- `git stash apply`
### Get stash list
- `git stash list`
### Apply specific version of the stash list
- `git stash@{ [ number ] }`
### Create a branch from stash
- `git stash branch [ new branchname ]`
### Control which changes will be stashed
- `git stash --patch`

## Hooks
Git hooks are scripts that get fired off when a certain action occurs, they are scoped to their given repository, hence, they are local and tehy’re stored in the `./git/hooks` directory. Git provides a template directory that allows the installation of hooks automatically with every git init or git clone.  

### Client-side hooks
Client-side hooks don’t get copied when a repository is cloned. They can be altered or uninstalled by the owner of a repository.  

#### Local hooks
The most useful and common local hooks are:
1. `pre-commit`
2. `prepare-commit-msg`
3. `commit-msg`
4. `post-commit`
5. `post-checkout`
6. `pre-rebase  `

Hooks 5 and 6 are useful to perform additional safety checks for git checkout and git rebase respectively. pre- hooks are used to alter the action that’s about to happen, whereas post- hooks are used for notifications.  

### Server-side hooks
They usually reside in central or remote repositories, and can be used as a way to enforce policies about commits when they’re attached to the ‘official’ repository. These hooks allow you to react to stages of the git push process.
#### Server-side hooks
* `pre-receive`
* `update`
* `post-receive`

The pre-receive hook runs before references are updates, and can therefore be used to prevent merges, checking the user for authorization, and reject commits that don’t meet a company’s standard, whether that is the commit message or the changes that the commit is trying to push. The update hook also runs before any updates are made to the repository and is called for every ref that got pushed. Meanwhile, post-receive is called after a successful push operation, which is why this hook is commonly used to send notifications.

## Bibliography
* [Atlassian - Git branches](https://www.atlassian.com/git/tutorials/using-branches#:~:text=In%20Git%2C%20branches%20are%20a,branch%20to%20encapsulate%20your%20changes)
* [Atlassian - Git hooks](https://www.atlassian.com/git/tutorials/git-hooks)
* [Git branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [Git tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
* [Git stashing](https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)
* [Git commands - Github cheatsheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf)