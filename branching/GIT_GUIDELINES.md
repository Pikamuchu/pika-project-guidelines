![Git](../images/branching.png)

## Git guidelines 

### Git branching model
The branching model is based on  [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow). 
These are the main rules to keep in mind:

* Perform work in a feature branch. 
    
    _Why:_
    >Because this way all work is done in isolation on a dedicated branch rather than the main branch. It allows you to submit multiple pull requests without confusion. You can iterate without polluting the master branch with potentially unstable, unfinished code. [read more...](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow)

* Branch out from `develop`. The branch name must follow the pattern `feature/[jira issue]` (example feature/HIPPOC-000).
    
    _Why:_
    >This way, you can make sure that code in master will almost always build without problems, and can be mostly used directly for releases. 

* Add messages on every commit. The commit message must have a subject following the pattern `[jira issue] What code changes summary.`
* Limit the subject line to 50 characters and Wrap the body at 72 characters.

    _why_
    > Commits should be as fine-grained and focused as possible, it is not the place to be verbose. [read more...](https://medium.com/@preslavrachev/what-s-with-the-50-72-rule-8a906f61f09c)

* Never push into `develop` or `master`. Make a Pull Request.
    
    _Why:_
    > It notifies team members that they have completed a feature. It also enables easy peer-review of the code and dedicates forum for discussing the proposed feature.

* Update your local `develop` branch and do a merge before pushing your feature. Resolve potential conflicts while merging and before making a Pull Request.

    _Why:_
    > Doing a merge before pushing your feature and making a Pull Request in the requested branch (`master` or `develop`) assures that the pull request won't have merge conflicts. [read more ...](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

* Delete local and remote feature branches after merging.
    
    _Why:_
    > It will clutter up your list of branches with dead branches. It ensures you only ever merge the branch back into (`master` or `develop`) once. Feature branches should only exist while the work is still in progress.

* Before making a Pull Request, make sure your feature branch builds successfully and passes all tests (including code style checks).
    
    _Why:_
    > You are about to add your code to a stable branch. If your feature-branch tests fail, there is a high chance that your destination branch build will fail too. Additionally, you need to apply code style check before making a Pull Request. It aids readability and reduces the chance of formatting fixes being mingled in with actual changes.

* Use [this](./.gitignore) `.gitignore` file.
    
    _Why:_
    > It already has a list of system files that should not be sent with your code into a remote repository. In addition, it excludes setting folders and files for most used editors, as well as most common dependency folders.


### Git workflow commands

The main git commands to follow the steps mentioned in above section are:

* Checkout a new feature/bugfix branch.

```sh
    git checkout -b feature/HIPPOC-000
```

* Make Changes.
```sh
    git add . 
    git commit -m "HIPPOC-000 What code changes summary." 
```

* Sync with remote to get changes you’ve missed.
```sh
    git checkout develop
    git pull
```
    
    _Why:_
    > This will give you a chance to deal with conflicts on your machine while rebasing (later) rather than creating a Pull Request that contains conflicts.
    
* Update your feature branch with latest changes from develop using merge. 
```sh
    git checkout feature/HIPPOC-000
    git merge develop
```
    
* If you don’t have conflicts, skip this step. If you have conflicts, [resolve them](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)  and commit merge. 
```sh
    git add . 
    git commit
```

* Push your branch. 
```sh
    git push origin feature/HIPPOC-000
```
    
* Make a Pull Request.
* Pull request will be accepted, merged and close by a reviewer.
* Remove your local feature branch if you're done.

```sh
  git branch -d HIPPOC-000
```
  to remove all branches which are no longer on remote
```sh
  git fetch -p && for branch in `git branch -vv --no-color | grep ': gone]' |   awk '{print $1}'`; do git branch -D $branch; done
```



