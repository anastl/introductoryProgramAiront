# GIT branching strategies
1. Use feature branches for all new features and bug fixes.
2. Merge feature branches into the main branch using pull requests.
3. Keep a high quality, up-to-date main branch.

## Use feature branches for your work
Develop your features and fix bugs in feature branches based off your main branch. These branches are also known as topic branches. Feature branches isolate work in progress from the completed work in the main branch.  

## Name your feature branches by convention
Use a consistent naming convention for your feature branches to identify the work done in the branch. You can also include other information in the branch name, such as who created the branch.  

**Some suggestions for naming feature branches:**  
* users/username/description
* users/username/workitem
* bugfix/description
* feature/feature-name
* feature/feature-area/feature-name
* hotfix/description  

[Microsoft - Git branching strategies](https://learn.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops)


# GIT workflow  
## GIT feature branch workflow  
All feature development should take place in a dedicated branch instead of the main branch. This encapsulation makes it easy for multiple developers to work on a particular feature without disturbing the main codebase. It also means the main branch will never contain broken code and it makes it possible to make it pull requests. Developers create a new branch every time they start work on a new feature.  

[Atlassian feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)  

## GITflow workflow  
Giflow is an alternative Git branching model that involves the use of feature branches and multiple primary branches. Giflow has numerous, longer-lived branches and larger commits. Under this model, developers create a feature branch and delay merging it to the main trunk branch until the feature is complete. In addition to feature branches, it uses individual branches for preparing, maintaining, and recording releases. **These long-lived feature branches require more collaboration to merge** and **have a higher risk of deviating from the trunk branch.** They can also **introduce conflicting updates.**  

[Atlassian GITflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow#:~:text=Gitflow%20is%20a%20legacy%20Git,software%20development%20and%20DevOps%20practices.)