# GIT merge  
* Non-destructive operation
* Existing branches are not changed
* Can pollute the master branch
* Existing branches are joined  

# GIT rebase  
* Context is lost, rewrites project history. (Never use it on public branches)
* Rewrites history on top of a branch
* Provides linear history
* May have to force push changes  

# GIT squash + merge  
Allows a developer to squash an extensive amount of commits into a single commit before merging it with the master branch. Helps maintain a cleaner commit history.  

## Biliography  
* [Squash, merge or rebase?](https://matt-rickard.com/squash-merge-or-rebase)  
* [When to use squash, merge, and rebase?](https://medium.com/@shubhpaliwal98/when-to-use-squash-merge-and-rebase-43da3571dcbe)  
* [Atlassian - Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)